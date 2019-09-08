---
title: 通过 Docker 使应用程序容器化的教程
description: 在本教程中，你将了解如何使用 Docker 容器化 .NET Core 应用。
ms.date: 06/26/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: ec1c6eb5c1a78a631b8205da5d082e44884cde7a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253951"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="658fc-103">教程：使 .NET Core 应用程序容器化</span><span class="sxs-lookup"><span data-stu-id="658fc-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="658fc-104">本教程介绍如何生成包含 .NET Core 应用程序的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="658fc-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="658fc-105">此映像可用于为本地开发环境、私有云或公有云创建容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="658fc-106">你将了解如何：</span><span class="sxs-lookup"><span data-stu-id="658fc-106">You'll learn to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="658fc-107">创建并发布简单的 .NET Core 应用</span><span class="sxs-lookup"><span data-stu-id="658fc-107">Create and publish a simple .NET Core app</span></span>
> * <span data-ttu-id="658fc-108">创建并配置用于 .NET Core 的 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="658fc-108">Create and configure a Dockerfile for .NET Core</span></span>
> * <span data-ttu-id="658fc-109">生成 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="658fc-109">Build a Docker image</span></span>
> * <span data-ttu-id="658fc-110">创建并运行 Docker 容器</span><span class="sxs-lookup"><span data-stu-id="658fc-110">Create and run a Docker container</span></span>

<span data-ttu-id="658fc-111">你将了解用于 .NET Core 应用的 Docker 容器生成和部署任务。</span><span class="sxs-lookup"><span data-stu-id="658fc-111">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="658fc-112">Docker 平台  使用 Docker 引擎  快速生成应用，并将应用打包为 Docker 映像  。</span><span class="sxs-lookup"><span data-stu-id="658fc-112">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="658fc-113">这些映像采用 Dockerfile  格式编写，以供在分层容器中部署和运行。</span><span class="sxs-lookup"><span data-stu-id="658fc-113">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="658fc-114">系统必备</span><span class="sxs-lookup"><span data-stu-id="658fc-114">Prerequisites</span></span>

<span data-ttu-id="658fc-115">安装以下必备组件：</span><span class="sxs-lookup"><span data-stu-id="658fc-115">Install the following prerequisites:</span></span>

* <span data-ttu-id="658fc-116">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="658fc-116">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)</span></span>\
<span data-ttu-id="658fc-117">如果已安装 .NET Core，请使用 `dotnet --info` 命令来确定使用的是哪个 SDK。</span><span class="sxs-lookup"><span data-stu-id="658fc-117">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>

* [<span data-ttu-id="658fc-118">Docker 社区版</span><span class="sxs-lookup"><span data-stu-id="658fc-118">Docker Community Edition</span></span>](https://www.docker.com/products/docker-desktop)

* <span data-ttu-id="658fc-119">Dockerfile 和 .NET Core 示例应用的临时工作文件夹  。</span><span class="sxs-lookup"><span data-stu-id="658fc-119">A temporary working folder for the *Dockerfile* and .NET Core example app.</span></span> <span data-ttu-id="658fc-120">在本教程中，`docker-working` 用作工作文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="658fc-120">In this tutorial, the name `docker-working` is used as the working folder.</span></span>

### <a name="use-sdk-version-22"></a><span data-ttu-id="658fc-121">使用 SDK 版本 2.2</span><span class="sxs-lookup"><span data-stu-id="658fc-121">Use SDK version 2.2</span></span>

<span data-ttu-id="658fc-122">如果使用的是更高版本 SDK（如 3.0），请务必强制应用使用 SDK 2.2。</span><span class="sxs-lookup"><span data-stu-id="658fc-122">If you're using an SDK that is newer, like 3.0, make sure that your app is forced to use the 2.2 SDK.</span></span> <span data-ttu-id="658fc-123">在工作文件夹中创建名为 `global.json` 的文件，并粘贴以下 json 代码：</span><span class="sxs-lookup"><span data-stu-id="658fc-123">Create a file named `global.json` in your working folder and paste in the following json code:</span></span>

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

<span data-ttu-id="658fc-124">保存此文件。</span><span class="sxs-lookup"><span data-stu-id="658fc-124">Save this file.</span></span> <span data-ttu-id="658fc-125">如果存在此文件，则强制 .NET Core 对从此文件夹及其子级调用的任何 `dotnet` 命令使用版本 2.2。</span><span class="sxs-lookup"><span data-stu-id="658fc-125">The presence of file will force .NET Core to use version 2.2 for any `dotnet` command called from this folder and below.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="658fc-126">创建 .Net Core 应用</span><span class="sxs-lookup"><span data-stu-id="658fc-126">Create .NET Core app</span></span>

<span data-ttu-id="658fc-127">需要有可供 Docker 容器运行的 .NET Core 应用。</span><span class="sxs-lookup"><span data-stu-id="658fc-127">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="658fc-128">打开终端、创建工作文件夹（如果尚没有），然后进入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="658fc-128">Open your terminal, create a working folder if you haven't already, and enter it.</span></span> <span data-ttu-id="658fc-129">在工作文件夹中，运行下面的命令，在名为“应用”的子目录中新建一个项目：</span><span class="sxs-lookup"><span data-stu-id="658fc-129">In the working folder, run the following command to create a new project in a subdirectory named app:</span></span>

```console
dotnet new console -o app -n myapp
```

<span data-ttu-id="658fc-130">文件夹树将如下所示：</span><span class="sxs-lookup"><span data-stu-id="658fc-130">Your folder tree will look like the following:</span></span>

```
docker-working
│   global.json
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    └───obj
            myapp.csproj.nuget.cache
            myapp.csproj.nuget.g.props
            myapp.csproj.nuget.g.targets
            project.assets.json
```

<span data-ttu-id="658fc-131">`dotnet new` 命令会新建一个名为“应用”的文件夹，并生成一个“Hello World”应用  。</span><span class="sxs-lookup"><span data-stu-id="658fc-131">The `dotnet new` command creates a new folder named *app* and generates a "Hello World" app.</span></span> <span data-ttu-id="658fc-132">进入“应用”文件夹并运行命令 `dotnet run`  。</span><span class="sxs-lookup"><span data-stu-id="658fc-132">Enter the *app* folder and run the command `dotnet run`.</span></span> <span data-ttu-id="658fc-133">输出如下：</span><span class="sxs-lookup"><span data-stu-id="658fc-133">You'll see the following output:</span></span>

```console
> dotnet run
Hello World!
```

<span data-ttu-id="658fc-134">默认模板创建应用，此应用先打印输出到终端，再退出。</span><span class="sxs-lookup"><span data-stu-id="658fc-134">The default template creates an app that prints to the terminal and then exits.</span></span> <span data-ttu-id="658fc-135">本教程将使用无限循环的应用。</span><span class="sxs-lookup"><span data-stu-id="658fc-135">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="658fc-136">在文本编辑器中，打开“Program.cs”  文件。</span><span class="sxs-lookup"><span data-stu-id="658fc-136">Open the **Program.cs** file in a text editor.</span></span> <span data-ttu-id="658fc-137">它应如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="658fc-137">It should currently look like the following code:</span></span>

```csharp
using System;

namespace myapp
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="658fc-138">将此文件替换为以下每秒计数一次的代码：</span><span class="sxs-lookup"><span data-stu-id="658fc-138">Replace the file with the following code that counts numbers every second:</span></span>

```csharp
using System;

namespace myapp
{
    class Program
    {
        static void Main(string[] args)
        {
            var counter = 0;
            var max = args.Length != 0 ? Convert.ToInt32(args[0]) : -1;
            while(max == -1 || counter < max)
            {
                counter++;
                Console.WriteLine($"Counter: {counter}");
                System.Threading.Tasks.Task.Delay(1000).Wait();
            }
        }
    }
}
```

<span data-ttu-id="658fc-139">保存此文件，并使用 `dotnet run` 再次测试程序。</span><span class="sxs-lookup"><span data-stu-id="658fc-139">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="658fc-140">请注意，此应用无限期运行。</span><span class="sxs-lookup"><span data-stu-id="658fc-140">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="658fc-141">使用取消命令 <kbd>CTRL + C</kbd> 可以停止运行。</span><span class="sxs-lookup"><span data-stu-id="658fc-141">Use the cancel command <kbd>CTRL + C</kbd> to stop it.</span></span> <span data-ttu-id="658fc-142">输出如下：</span><span class="sxs-lookup"><span data-stu-id="658fc-142">You'll see the following output:</span></span>

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="658fc-143">如果你在命令行中向应用传递一个数字，它就只会计数到这个数字，然后退出。</span><span class="sxs-lookup"><span data-stu-id="658fc-143">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="658fc-144">试一试用 `dotnet run -- 5` 计数到 5。</span><span class="sxs-lookup"><span data-stu-id="658fc-144">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!NOTE]
> <span data-ttu-id="658fc-145">`--` 之后的参数都不传递到 `dotnet run` 命令，而是传递到你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="658fc-145">Any parameters after `--` are not passed to the `dotnet run` command and instead are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="658fc-146">发布 .Net Core 应用</span><span class="sxs-lookup"><span data-stu-id="658fc-146">Publish .NET Core app</span></span>

<span data-ttu-id="658fc-147">请先发布 .NET Core 应用，再将它添加到 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="658fc-147">Before you add your .NET Core app to the Docker image, publish it.</span></span> <span data-ttu-id="658fc-148">需确保容器在启动时运行应用的发布版本。</span><span class="sxs-lookup"><span data-stu-id="658fc-148">You want to make sure that the container runs the published version of the app when it's started.</span></span>

<span data-ttu-id="658fc-149">在工作文件夹中，进入包含示例源代码的“应用”文件夹，并运行以下命令  ：</span><span class="sxs-lookup"><span data-stu-id="658fc-149">From the working folder, enter the **app** folder with the example source code and run the following command:</span></span>

```console
dotnet publish -c Release
```

<span data-ttu-id="658fc-150">此命令将应用编译到“发布”文件夹中  。</span><span class="sxs-lookup"><span data-stu-id="658fc-150">This command compiles your app to the **publish** folder.</span></span> <span data-ttu-id="658fc-151">从工作文件夹到“发布”文件夹的路径应为 `.\app\bin\Release\netcoreapp2.2\publish\` </span><span class="sxs-lookup"><span data-stu-id="658fc-151">The path to the **publish** folder from the working folder should be `.\app\bin\Release\netcoreapp2.2\publish\`</span></span>

<span data-ttu-id="658fc-152">获取“发布”文件夹的目录清单，以验证 myapp.dll  是否已创建。</span><span class="sxs-lookup"><span data-stu-id="658fc-152">Get a directory listing of the publish folder to verify that the **myapp.dll** was created.</span></span> <span data-ttu-id="658fc-153">在“应用”文件夹中，运行下列命令之一  ：</span><span class="sxs-lookup"><span data-stu-id="658fc-153">From the **app** folder, run one of the following commands:</span></span>

```console
> dir bin\Release\netcoreapp2.2\publish
 Directory of C:\docker-working\app\bin\Release\netcoreapp2.2\publish

04/05/2019  11:00 AM    <DIR>          .
04/05/2019  11:00 AM    <DIR>          ..
04/05/2019  11:00 AM               447 myapp.deps.json
04/05/2019  11:00 AM             4,608 myapp.dll
04/05/2019  11:00 AM               448 myapp.pdb
04/05/2019  11:00 AM               154 myapp.runtimeconfig.json
```

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp2.2/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

## <a name="create-the-dockerfile"></a><span data-ttu-id="658fc-154">创建 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="658fc-154">Create the Dockerfile</span></span>

<span data-ttu-id="658fc-155">`docker build` 命令使用 Dockerfile  文件来创建容器映像。</span><span class="sxs-lookup"><span data-stu-id="658fc-155">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="658fc-156">此文件是名为“Dockerfile”  的纯文本文件，它没有扩展名。</span><span class="sxs-lookup"><span data-stu-id="658fc-156">This file is a plaintext file named *Dockerfile* that does not have an extension.</span></span>

<span data-ttu-id="658fc-157">在终端中，导航到你在启动时创建的工作文件夹的目录。</span><span class="sxs-lookup"><span data-stu-id="658fc-157">In your terminal, navigate up a directory to the working folder you created at the start.</span></span> <span data-ttu-id="658fc-158">在工作文件夹中创建名为“Dockerfile”的文件，在文本编辑器中打开它  。</span><span class="sxs-lookup"><span data-stu-id="658fc-158">Create a file named *Dockerfile* in your working folder and open it in a text editor.</span></span> <span data-ttu-id="658fc-159">将以下命令添加为此文件的首行：</span><span class="sxs-lookup"><span data-stu-id="658fc-159">Add the following command as the first line of the file:</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/core/runtime:2.2
```

<span data-ttu-id="658fc-160">`FROM` 命令指示 Docker 从 mcr.microsoft.com/dotnet/core/runtime  存储库拉取标记为“2.2”  的映像。</span><span class="sxs-lookup"><span data-stu-id="658fc-160">The `FROM` command tells Docker to pull down the image tagged **2.2** from the **mcr.microsoft.com/dotnet/core/runtime** repository.</span></span> <span data-ttu-id="658fc-161">请确保拉取的 .NET Core 运行时与 SDK 定目标到的运行时一致。</span><span class="sxs-lookup"><span data-stu-id="658fc-161">Make sure that you pull the .NET Core runtime that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="658fc-162">例如，上一部分中创建的应用定目标到 .Net Core 2.2，且使用 .Net Core 2.2 SDK。</span><span class="sxs-lookup"><span data-stu-id="658fc-162">For example, the app created in the previous section used the .NET Core 2.2 SDK and created an app that targeted .NET Core 2.2.</span></span> <span data-ttu-id="658fc-163">因此，Dockerfile  中引用的基础映像被标记为“2.2”  。</span><span class="sxs-lookup"><span data-stu-id="658fc-163">So the base image referred to in the *Dockerfile* is tagged with **2.2**.</span></span>

<span data-ttu-id="658fc-164">保存 Dockerfile 文件  。</span><span class="sxs-lookup"><span data-stu-id="658fc-164">Save the *Dockerfile* file.</span></span> <span data-ttu-id="658fc-165">工作文件夹的目录结果应如下所示。</span><span class="sxs-lookup"><span data-stu-id="658fc-165">The directory structure of the working folder should look like the following.</span></span> <span data-ttu-id="658fc-166">为节省本文的空间，删掉了一些更深级别的文件和文件夹：</span><span class="sxs-lookup"><span data-stu-id="658fc-166">Some of the deeper-level files and folders have been cut to save space in the article:</span></span>

```
docker-working
│   Dockerfile
│   global.json
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    ├───bin
    │   └───Release
    │       └───netcoreapp2.2
    │           └───publish
    │                   myapp.deps.json
    │                   myapp.dll
    │                   myapp.pdb
    │                   myapp.runtimeconfig.json
    │
    └───obj
```

<span data-ttu-id="658fc-167">在终端中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="658fc-167">From your terminal, run the following command:</span></span>

```console
docker build -t myimage -f Dockerfile .
```

<span data-ttu-id="658fc-168">Docker 会处理 Dockerfile  中的每一行。</span><span class="sxs-lookup"><span data-stu-id="658fc-168">Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="658fc-169">`docker build` 命令中的 `.` 指示 Docker 在当前文件夹中查找 Dockerfile  。</span><span class="sxs-lookup"><span data-stu-id="658fc-169">The `.` in the `docker build` command tells Docker to use the current folder to find a *Dockerfile*.</span></span> <span data-ttu-id="658fc-170">此命令生成映像，并创建指向相应映像的本地存储库“myimage”  。</span><span class="sxs-lookup"><span data-stu-id="658fc-170">This command builds the image and creates a local repository named **myimage** that points to that image.</span></span> <span data-ttu-id="658fc-171">在此命令完成后，运行 `docker images` 以列出已安装的映像：</span><span class="sxs-lookup"><span data-stu-id="658fc-171">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
myimage                                 latest              d51bb4452469        2 days ago          314MB
```

<span data-ttu-id="658fc-172">请注意，两个映像共用相同的“IMAGE ID”  值。</span><span class="sxs-lookup"><span data-stu-id="658fc-172">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="658fc-173">两个映像使用的 ID 值相同是因为，Dockerfile  中的唯一命令是在现有映像的基础之上生成新映像。</span><span class="sxs-lookup"><span data-stu-id="658fc-173">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="658fc-174">接下来，在 Dockerfile  中添加两个命令。</span><span class="sxs-lookup"><span data-stu-id="658fc-174">Let's add two commands to the *Dockerfile*.</span></span> <span data-ttu-id="658fc-175">两个命令都新建映像层，最后一个命令表示 myimage  存储库将指向的映像。</span><span class="sxs-lookup"><span data-stu-id="658fc-175">Each command creates a new image layer with the final command representing the image the **myimage** repository will point to.</span></span>

```dockerfile
COPY app/bin/Release/netcoreapp2.2/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

<span data-ttu-id="658fc-176">`COPY` 命令指示 Docker 将计算机上的指定文件夹复制到容器中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="658fc-176">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="658fc-177">在此示例中，“发布”  文件夹被复制到容器中的“应用”  文件夹。</span><span class="sxs-lookup"><span data-stu-id="658fc-177">In this example, the **publish** folder is copied to a folder named **app** in the container.</span></span>

<span data-ttu-id="658fc-178">下一个命令 `ENTRYPOINT` 指示 Docker 将容器配置为可执行文件运行。</span><span class="sxs-lookup"><span data-stu-id="658fc-178">The next command, `ENTRYPOINT`, tells Docker to configure the container to run as an executable.</span></span> <span data-ttu-id="658fc-179">在容器启动时，`ENTRYPOINT` 命令运行。</span><span class="sxs-lookup"><span data-stu-id="658fc-179">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="658fc-180">当此命令结束时，容器也会自动停止。</span><span class="sxs-lookup"><span data-stu-id="658fc-180">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="658fc-181">在终端中，运行 `docker build -t myimage -f Dockerfile .`；在此命令完成后，运行 `docker images`。</span><span class="sxs-lookup"><span data-stu-id="658fc-181">From your terminal, run `docker build -t myimage -f Dockerfile .` and when that command finishes, run `docker images`.</span></span>

```console
> docker build -t myimage -f Dockerfile .
Sending build context to Docker daemon  819.7kB
Step 1/3 : FROM mcr.microsoft.com/dotnet/core/runtime:2.2
 ---> d51bb4452469
Step 2/3 : COPY app/bin/Release/netcoreapp2.2/publish/ app/
 ---> a1e98ac62017
Step 3/3 : ENTRYPOINT ["dotnet", "app/myapp.dll"]
 ---> Running in f34da5c18e7c
Removing intermediate container f34da5c18e7c
 ---> ddcc6646461b
Successfully built ddcc6646461b
Successfully tagged myimage:latest

> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              ddcc6646461b        10 seconds ago      314MB
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
```

<span data-ttu-id="658fc-182">Dockerfile  中的每个命令生成了一个层，并创建了“IMAGE ID”  。</span><span class="sxs-lookup"><span data-stu-id="658fc-182">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="658fc-183">最终“IMAGE ID”  是“ddcc6646461b”  （你的 ID 会有所不同），接下来在此映像的基础之上创建容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-183">The final **IMAGE ID** (yours will be different) is **ddcc6646461b** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="658fc-184">创建容器</span><span class="sxs-lookup"><span data-stu-id="658fc-184">Create a container</span></span>

<span data-ttu-id="658fc-185">至此，已有包含应用的映像，可以创建容器了。</span><span class="sxs-lookup"><span data-stu-id="658fc-185">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="658fc-186">可以通过两种方式来创建容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-186">You can create a container in two ways.</span></span> <span data-ttu-id="658fc-187">首先，新建已停止的容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-187">First, create a new container that is stopped.</span></span>

```console
> docker create myimage
0e8f3c2ca32ce773712a5cca38750f41259a4e54e04bdf0946087e230ad7066c
```

<span data-ttu-id="658fc-188">上面的 `docker create` 命令在 myimage  映像的基础之上创建容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-188">The `docker create` command from above will create a container based on the **myimage** image.</span></span> <span data-ttu-id="658fc-189">此命令的输出显示已创建容器的“CONTAINER ID”  （你的 ID 会有所不同）。</span><span class="sxs-lookup"><span data-stu-id="658fc-189">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="658fc-190">若要查看所有  容器的列表，请使用 `docker ps -a` 命令：</span><span class="sxs-lookup"><span data-stu-id="658fc-190">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               boring_matsumoto
```

### <a name="manage-the-container"></a><span data-ttu-id="658fc-191">管理容器</span><span class="sxs-lookup"><span data-stu-id="658fc-191">Manage the container</span></span>

<span data-ttu-id="658fc-192">每个容器都分配有随机名称，可用来引用相应容器实例。</span><span class="sxs-lookup"><span data-stu-id="658fc-192">Each container is assigned a random name that you can use to refer to that container instance.</span></span> <span data-ttu-id="658fc-193">例如，自动创建的容器选择了名称“boring_matsumoto”  （你的名称会有所不同），此名称可用于启动容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-193">For example, the container that was created automatically chose the name **boring_matsumoto** (yours will be different) and that name can be used to start the container.</span></span> <span data-ttu-id="658fc-194">可以使用 `docker create --name` 参数将自动名称替代为特定名称。</span><span class="sxs-lookup"><span data-stu-id="658fc-194">You override the automatic name with a specific one by using the `docker create --name` parameter.</span></span>

<span data-ttu-id="658fc-195">下面的示例使用 `docker start` 命令来启动容器，然后使用 `docker ps` 命令仅显示正在运行的容器：</span><span class="sxs-lookup"><span data-stu-id="658fc-195">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```console
> docker start boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           boring_matsumoto
```

<span data-ttu-id="658fc-196">同样，`docker stop` 命令会停止容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-196">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="658fc-197">下面的示例使用 `docker stop` 命令来停止容器，然后使用 `docker ps` 命令来显示没有正在运行的容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-197">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running.</span></span>

```console
> docker stop boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="658fc-198">连接到容器</span><span class="sxs-lookup"><span data-stu-id="658fc-198">Connect to a container</span></span>

<span data-ttu-id="658fc-199">在容器运行后，可以连接到它来查看输出。</span><span class="sxs-lookup"><span data-stu-id="658fc-199">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="658fc-200">使用 `docker start` 和 `docker attach` 命令，启动容器并查看输出流。</span><span class="sxs-lookup"><span data-stu-id="658fc-200">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="658fc-201">在此示例中，<kbd>CTRL + C</kbd> 命令用于从正在运行的容器中分离出来。</span><span class="sxs-lookup"><span data-stu-id="658fc-201">In this example, the <kbd>CTRL + C</kbd> command is used to detach from the running container.</span></span> <span data-ttu-id="658fc-202">这其实是结束容器中的进程，进而停止容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-202">This may actually end the process in the container, which will stop the container.</span></span> <span data-ttu-id="658fc-203">`--sig-proxy=false` 参数可确保 <kbd>Ctrl + C</kbd> 不停止容器中的进程。</span><span class="sxs-lookup"><span data-stu-id="658fc-203">The `--sig-proxy=false` parameter ensures that <kbd>CTRL + C</kbd> won't stop the process in the container.</span></span>

<span data-ttu-id="658fc-204">从容器中分离出来后重新连接，以验证它是否仍在运行和计数。</span><span class="sxs-lookup"><span data-stu-id="658fc-204">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

```console
> docker start boring_matsumoto
boring_matsumoto

> docker attach --sig-proxy=false boring_matsumoto
Counter: 7
Counter: 8
Counter: 9
^C

> docker attach --sig-proxy=false boring_matsumoto
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a><span data-ttu-id="658fc-205">删除容器</span><span class="sxs-lookup"><span data-stu-id="658fc-205">Delete a container</span></span>

<span data-ttu-id="658fc-206">就本文而言，你不希望存在不执行任何操作的容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-206">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="658fc-207">删除前面创建的容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-207">Delete the container you previously created.</span></span> <span data-ttu-id="658fc-208">如果容器正在运行，停止容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-208">If the container is running, stop it.</span></span>

```console
> docker stop boring_matsumoto
```

<span data-ttu-id="658fc-209">下面的示例列出了所有容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-209">The following example lists all containers.</span></span> <span data-ttu-id="658fc-210">然后，它使用 `docker rm` 命令来删除容器，并再次检查是否有任何正在运行的容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-210">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             boring_matsumoto

> docker rm boring_matsumoto
boring_matsumoto

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="658fc-211">单次运行</span><span class="sxs-lookup"><span data-stu-id="658fc-211">Single run</span></span>

<span data-ttu-id="658fc-212">Docker 提供了 `docker run` 命令，用于将容器作为单一命令进行创建和运行。</span><span class="sxs-lookup"><span data-stu-id="658fc-212">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="658fc-213">使用此命令，无需依次运行 `docker create` 和 `docker start`。</span><span class="sxs-lookup"><span data-stu-id="658fc-213">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="658fc-214">另外，还可以将此命令设置为，在容器停止时自动删除容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-214">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="658fc-215">例如，使用 `docker run -it --rm` 可以执行两项操作，先自动使用当前终端连接到容器，再在容器完成时删除容器：</span><span class="sxs-lookup"><span data-stu-id="658fc-215">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```console
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="658fc-216">使用 `docker run -it`，<kbd>CTRL + C</kbd> 命令会停止在容器中运行的进程，进而停止容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-216">With `docker run -it`, the <kbd>CTRL + C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="658fc-217">由于提供了 `--rm` 参数，因此在进程停止时自动删除容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-217">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="658fc-218">验证它是否不存在：</span><span class="sxs-lookup"><span data-stu-id="658fc-218">Verify that it does not exist:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="658fc-219">更改 ENTRYPOINT</span><span class="sxs-lookup"><span data-stu-id="658fc-219">Change the ENTRYPOINT</span></span>

<span data-ttu-id="658fc-220">使用 `docker run` 命令，还可以修改 Dockerfile  中的 `ENTRYPOINT` 命令，并运行其他内容，但只能针对相应容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-220">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="658fc-221">例如，使用以下命令来运行 `bash` 或 `cmd.exe`。</span><span class="sxs-lookup"><span data-stu-id="658fc-221">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="658fc-222">根据需要，编辑此命令。</span><span class="sxs-lookup"><span data-stu-id="658fc-222">Edit the command as necessary.</span></span>

#### <a name="windows"></a><span data-ttu-id="658fc-223">Windows</span><span class="sxs-lookup"><span data-stu-id="658fc-223">Windows</span></span>
<span data-ttu-id="658fc-224">在本例中，`ENTRYPOINT` 更改为 `cmd.exe`。</span><span class="sxs-lookup"><span data-stu-id="658fc-224">In this example, `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="658fc-225">通过按下 <kbd>CTRL + C</kbd> 来结束进程并停止容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-225"><kbd>CTRL + C</kbd> is pressed to end the process and stop the container.</span></span>

```console
> docker run -it --rm --entrypoint "cmd.exe" myimage

Microsoft Windows [Version 10.0.17763.379]
(c) 2018 Microsoft Corporation. All rights reserved.

C:\>dir
 Volume in drive C has no label.
 Volume Serial Number is 3005-1E84

 Directory of C:\

04/09/2019  08:46 AM    <DIR>          app
03/07/2019  10:25 AM             5,510 License.txt
04/02/2019  01:35 PM    <DIR>          Program Files
04/09/2019  01:06 PM    <DIR>          Users
04/02/2019  01:35 PM    <DIR>          Windows
               1 File(s)          5,510 bytes
               4 Dir(s)  21,246,517,248 bytes free

C:\>^C
```

#### <a name="linux"></a><span data-ttu-id="658fc-226">Linux</span><span class="sxs-lookup"><span data-stu-id="658fc-226">Linux</span></span>

<span data-ttu-id="658fc-227">在本例中，`ENTRYPOINT` 更改为 `bash`。</span><span class="sxs-lookup"><span data-stu-id="658fc-227">In this example, `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="658fc-228">通过运行 `quit` 命令来结束进程并停止容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-228">The `quit` command is run which ends the process and stop the container.</span></span>

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a><span data-ttu-id="658fc-229">重要命令</span><span class="sxs-lookup"><span data-stu-id="658fc-229">Essential commands</span></span>

<span data-ttu-id="658fc-230">Docker 有许多不同的命令，可用于执行你要对容器和映像执行的操作。</span><span class="sxs-lookup"><span data-stu-id="658fc-230">Docker has many different commands that cover what you want to do with your container and images.</span></span> <span data-ttu-id="658fc-231">下面这些 Docker 命令对于管理容器来说至关重要：</span><span class="sxs-lookup"><span data-stu-id="658fc-231">These Docker commands are essential to managing your containers:</span></span>

* [<span data-ttu-id="658fc-232">docker build</span><span class="sxs-lookup"><span data-stu-id="658fc-232">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="658fc-233">docker run</span><span class="sxs-lookup"><span data-stu-id="658fc-233">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="658fc-234">docker ps</span><span class="sxs-lookup"><span data-stu-id="658fc-234">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="658fc-235">docker stop</span><span class="sxs-lookup"><span data-stu-id="658fc-235">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="658fc-236">docker rm</span><span class="sxs-lookup"><span data-stu-id="658fc-236">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="658fc-237">docker rmi</span><span class="sxs-lookup"><span data-stu-id="658fc-237">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="658fc-238">docker image</span><span class="sxs-lookup"><span data-stu-id="658fc-238">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="658fc-239">清理资源</span><span class="sxs-lookup"><span data-stu-id="658fc-239">Clean up resources</span></span>

<span data-ttu-id="658fc-240">在本教程中，你创建了容器和映像。</span><span class="sxs-lookup"><span data-stu-id="658fc-240">During this tutorial you created containers and images.</span></span> <span data-ttu-id="658fc-241">如果需要，请删除这些资源。</span><span class="sxs-lookup"><span data-stu-id="658fc-241">If you want, delete these resources.</span></span> <span data-ttu-id="658fc-242">以下命令可用于</span><span class="sxs-lookup"><span data-stu-id="658fc-242">Use the following commands to</span></span>

01. <span data-ttu-id="658fc-243">列出所有容器</span><span class="sxs-lookup"><span data-stu-id="658fc-243">List all containers</span></span>

    ```console
    > docker ps -a
    ```

02. <span data-ttu-id="658fc-244">停止正在运行的容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-244">Stop containers that are running.</span></span> <span data-ttu-id="658fc-245">`CONTAINER_NAME` 表示自动分配给容器的名称。</span><span class="sxs-lookup"><span data-stu-id="658fc-245">The `CONTAINER_NAME` represents the name automatically assigned to the container.</span></span>

    ```console
    > docker stop CONTAINER_NAME
    ```

03. <span data-ttu-id="658fc-246">删除容器</span><span class="sxs-lookup"><span data-stu-id="658fc-246">Delete the container</span></span>

    ```console
    > docker rm CONTAINER_NAME
    ```

<span data-ttu-id="658fc-247">接下来，删除计算机上不再需要的任何映像。</span><span class="sxs-lookup"><span data-stu-id="658fc-247">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="658fc-248">依次删除 Dockerfile  创建的映像，以及 Dockerfile  所依据的 .NET Core 映像。</span><span class="sxs-lookup"><span data-stu-id="658fc-248">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="658fc-249">可以使用 IMAGE ID  或 REPOSITORY:TAG  格式字符串。</span><span class="sxs-lookup"><span data-stu-id="658fc-249">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/runtime:2.2
```

<span data-ttu-id="658fc-250">使用 `docker images` 命令来列出已安装的映像。</span><span class="sxs-lookup"><span data-stu-id="658fc-250">Use the `docker images` command to see a list of images installed.</span></span>

> [!NOTE]
> <span data-ttu-id="658fc-251">映像文件可能很大。</span><span class="sxs-lookup"><span data-stu-id="658fc-251">Image files can be large.</span></span> <span data-ttu-id="658fc-252">通常情况下，需要删除在测试和开发应用期间创建的临时容器。</span><span class="sxs-lookup"><span data-stu-id="658fc-252">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="658fc-253">如果计划在相应运行时的基础之上生成其他映像，通常会将基础映像与运行时一同安装。</span><span class="sxs-lookup"><span data-stu-id="658fc-253">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="658fc-254">后续步骤</span><span class="sxs-lookup"><span data-stu-id="658fc-254">Next steps</span></span>

* [<span data-ttu-id="658fc-255">试学“ASP.NET Core 微服务”教程。</span><span class="sxs-lookup"><span data-stu-id="658fc-255">Try the ASP.NET Core Microservice Tutorial.</span></span>](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
* [<span data-ttu-id="658fc-256">查看支持容器的 Azure 服务。</span><span class="sxs-lookup"><span data-stu-id="658fc-256">Review the Azure services that support containers.</span></span>](https://azure.microsoft.com/overview/containers/)
* [<span data-ttu-id="658fc-257">了解 Dockerfile 命令。</span><span class="sxs-lookup"><span data-stu-id="658fc-257">Read about Dockerfile commands.</span></span>](https://docs.docker.com/engine/reference/builder/)
* [<span data-ttu-id="658fc-258">了解用于 Visual Studio 的容器工具</span><span class="sxs-lookup"><span data-stu-id="658fc-258">Explore the Container Tools for Visual Studio</span></span>](/visualstudio/containers/overview)
