---
title: 通过 Docker 使应用程序容器化的教程
description: 在本教程中，你将了解如何使用 Docker 容器化 .NET Core 应用。
ms.date: 01/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 8be12792e4a9e8511dba87e657f700cc4ec97a16
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546570"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="faad8-103">教程：使 .NET Core 应用程序容器化</span><span class="sxs-lookup"><span data-stu-id="faad8-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="faad8-104">本教程介绍如何生成包含 .NET Core 应用程序的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="faad8-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="faad8-105">此映像可用于为本地开发环境、私有云或公有云创建容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="faad8-106">你将了解如何：</span><span class="sxs-lookup"><span data-stu-id="faad8-106">You'll learn to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="faad8-107">创建并发布简单的 .NET Core 应用</span><span class="sxs-lookup"><span data-stu-id="faad8-107">Create and publish a simple .NET Core app</span></span>
> - <span data-ttu-id="faad8-108">创建并配置用于 .NET Core 的 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="faad8-108">Create and configure a Dockerfile for .NET Core</span></span>
> - <span data-ttu-id="faad8-109">生成 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="faad8-109">Build a Docker image</span></span>
> - <span data-ttu-id="faad8-110">创建并运行 Docker 容器</span><span class="sxs-lookup"><span data-stu-id="faad8-110">Create and run a Docker container</span></span>

<span data-ttu-id="faad8-111">你将了解用于 .NET Core 应用的 Docker 容器生成和部署任务。</span><span class="sxs-lookup"><span data-stu-id="faad8-111">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="faad8-112">Docker 平台  使用 Docker 引擎  快速生成应用，并将应用打包为 Docker 映像  。</span><span class="sxs-lookup"><span data-stu-id="faad8-112">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="faad8-113">这些映像采用 Dockerfile  格式编写，以供在分层容器中部署和运行。</span><span class="sxs-lookup"><span data-stu-id="faad8-113">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

> [!WARNING]
> <span data-ttu-id="faad8-114">**本教程不适用于 ASP.NET Core 应用。**</span><span class="sxs-lookup"><span data-stu-id="faad8-114">**This tutorial isn't for ASP.NET Core apps.**</span></span> <span data-ttu-id="faad8-115">如果使用的是 ASP.NET Core，请参阅教程[了解如何容器化 ASP.NET Core 应用程序](/aspnet/core/host-and-deploy/docker/building-net-docker-images)。</span><span class="sxs-lookup"><span data-stu-id="faad8-115">If you're using ASP.NET Core, read the [Learn how to containerize an ASP.NET Core application](/aspnet/core/host-and-deploy/docker/building-net-docker-images) tutorial.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="faad8-116">先决条件</span><span class="sxs-lookup"><span data-stu-id="faad8-116">Prerequisites</span></span>

<span data-ttu-id="faad8-117">安装以下必备组件：</span><span class="sxs-lookup"><span data-stu-id="faad8-117">Install the following prerequisites:</span></span>

- <span data-ttu-id="faad8-118">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="faad8-118">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download)</span></span>\
<span data-ttu-id="faad8-119">如果已安装 .NET Core，请使用 `dotnet --info` 命令来确定使用的是哪个 SDK。</span><span class="sxs-lookup"><span data-stu-id="faad8-119">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>

- [<span data-ttu-id="faad8-120">Docker 社区版</span><span class="sxs-lookup"><span data-stu-id="faad8-120">Docker Community Edition</span></span>](https://www.docker.com/products/docker-desktop)

- <span data-ttu-id="faad8-121">Dockerfile 和 .NET Core 示例应用的临时工作文件夹  。</span><span class="sxs-lookup"><span data-stu-id="faad8-121">A temporary working folder for the *Dockerfile* and .NET Core example app.</span></span> <span data-ttu-id="faad8-122">在本教程中，docker-working  用作工作文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="faad8-122">In this tutorial, the name *docker-working* is used as the working folder.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="faad8-123">创建 .Net Core 应用</span><span class="sxs-lookup"><span data-stu-id="faad8-123">Create .NET Core app</span></span>

<span data-ttu-id="faad8-124">需要有可供 Docker 容器运行的 .NET Core 应用。</span><span class="sxs-lookup"><span data-stu-id="faad8-124">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="faad8-125">打开终端、创建工作文件夹（如果尚没有），然后进入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="faad8-125">Open your terminal, create a working folder if you haven't already, and enter it.</span></span> <span data-ttu-id="faad8-126">在工作文件夹中，运行下面的命令，在名为“app”的子目录中新建一个项目  ：</span><span class="sxs-lookup"><span data-stu-id="faad8-126">In the working folder, run the following command to create a new project in a subdirectory named *app*:</span></span>

```dotnetcli
dotnet new console -o app -n myapp
```

<span data-ttu-id="faad8-127">文件夹树将如下所示：</span><span class="sxs-lookup"><span data-stu-id="faad8-127">Your folder tree will look like the following:</span></span>

```
docker-working
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    └───obj
            myapp.csproj.nuget.cache
            myapp.csproj.nuget.dgspec.json
            myapp.csproj.nuget.g.props
            myapp.csproj.nuget.g.targets
            project.assets.json
```

<span data-ttu-id="faad8-128">`dotnet new` 命令会新建一个名为“应用”的文件夹，并生成一个“Hello World”应用  。</span><span class="sxs-lookup"><span data-stu-id="faad8-128">The `dotnet new` command creates a new folder named *app* and generates a "Hello World" app.</span></span> <span data-ttu-id="faad8-129">进入“应用”文件夹并运行命令 `dotnet run`  。</span><span class="sxs-lookup"><span data-stu-id="faad8-129">Enter the *app* folder and run the command `dotnet run`.</span></span> <span data-ttu-id="faad8-130">输出如下：</span><span class="sxs-lookup"><span data-stu-id="faad8-130">You'll see the following output:</span></span>

```console
> dotnet run
Hello World!
```

<span data-ttu-id="faad8-131">默认模板创建应用，此应用先打印输出到终端，再退出。</span><span class="sxs-lookup"><span data-stu-id="faad8-131">The default template creates an app that prints to the terminal and then exits.</span></span> <span data-ttu-id="faad8-132">本教程将使用无限循环的应用。</span><span class="sxs-lookup"><span data-stu-id="faad8-132">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="faad8-133">在文本编辑器中，打开“Program.cs”  文件。</span><span class="sxs-lookup"><span data-stu-id="faad8-133">Open the *Program.cs* file in a text editor.</span></span> <span data-ttu-id="faad8-134">它应如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="faad8-134">It should currently look like the following code:</span></span>

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

<span data-ttu-id="faad8-135">将此文件替换为以下每秒计数一次的代码：</span><span class="sxs-lookup"><span data-stu-id="faad8-135">Replace the file with the following code that counts numbers every second:</span></span>

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
            while (max == -1 || counter < max)
            {
                counter++;
                Console.WriteLine($"Counter: {counter}");
                System.Threading.Tasks.Task.Delay(1000).Wait();
            }
        }
    }
}
```

<span data-ttu-id="faad8-136">保存此文件，并使用 `dotnet run` 再次测试程序。</span><span class="sxs-lookup"><span data-stu-id="faad8-136">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="faad8-137">请注意，此应用无限期运行。</span><span class="sxs-lookup"><span data-stu-id="faad8-137">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="faad8-138">使用取消命令 <kbd>CTRL</kbd>+<kbd>C</kbd> 可以停止运行。</span><span class="sxs-lookup"><span data-stu-id="faad8-138">Use the cancel command <kbd>CTRL</kbd>+<kbd>C</kbd> to stop it.</span></span> <span data-ttu-id="faad8-139">输出如下：</span><span class="sxs-lookup"><span data-stu-id="faad8-139">You'll see the following output:</span></span>

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="faad8-140">如果你在命令行中向应用传递一个数字，它就只会计数到这个数字，然后退出。</span><span class="sxs-lookup"><span data-stu-id="faad8-140">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="faad8-141">试一试用 `dotnet run -- 5` 计数到 5。</span><span class="sxs-lookup"><span data-stu-id="faad8-141">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!NOTE]
> <span data-ttu-id="faad8-142">`--` 之后的参数都不传递到 `dotnet run` 命令，而是传递到你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="faad8-142">Any parameters after `--` are not passed to the `dotnet run` command and instead are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="faad8-143">发布 .Net Core 应用</span><span class="sxs-lookup"><span data-stu-id="faad8-143">Publish .NET Core app</span></span>

<span data-ttu-id="faad8-144">请先发布 .NET Core 应用，再将它添加到 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="faad8-144">Before you add your .NET Core app to the Docker image, publish it.</span></span> <span data-ttu-id="faad8-145">需确保容器在启动时运行应用的发布版本。</span><span class="sxs-lookup"><span data-stu-id="faad8-145">You want to make sure that the container runs the published version of the app when it's started.</span></span>

<span data-ttu-id="faad8-146">在工作文件夹中，进入包含示例源代码的“应用”文件夹，并运行以下命令  ：</span><span class="sxs-lookup"><span data-stu-id="faad8-146">From the working folder, enter the *app* folder with the example source code and run the following command:</span></span>

```dotnetcli
dotnet publish -c Release
```

<span data-ttu-id="faad8-147">此命令将应用编译到“发布”文件夹中  。</span><span class="sxs-lookup"><span data-stu-id="faad8-147">This command compiles your app to the *publish* folder.</span></span> <span data-ttu-id="faad8-148">从工作文件夹到“发布”文件夹的路径应为 `.\app\bin\Release\netcoreapp3.1\publish\` </span><span class="sxs-lookup"><span data-stu-id="faad8-148">The path to the *publish* folder from the working folder should be `.\app\bin\Release\netcoreapp3.1\publish\`</span></span>

<span data-ttu-id="faad8-149">在“应用”  文件夹中获取“发布”文件夹的目录清单，以验证 myapp.dll  文件是否已创建。</span><span class="sxs-lookup"><span data-stu-id="faad8-149">From the *app* folder, get a directory listing of the publish folder to verify that the *myapp.dll* file was created.</span></span>

```console
> dir bin\Release\netcoreapp3.1\publish

    Directory:  C:\docker-working\app\bin\Release\netcoreapp3.1\publish

01/09/2020  11:41 AM    <DIR>          .
01/09/2020  11:41 AM    <DIR>          ..
01/09/2020  11:41 AM               407 myapp.deps.json
01/09/2020  12:15 PM             4,608 myapp.dll
01/09/2020  12:15 PM           169,984 myapp.exe
01/09/2020  12:15 PM               736 myapp.pdb
01/09/2020  11:41 AM               154 myapp.runtimeconfig.json
```

<span data-ttu-id="faad8-150">如果使用的是 Linux 或 macOS，请使用 `ls` 命令获取目录列表，并验证是否已创建 myapp  文件。</span><span class="sxs-lookup"><span data-stu-id="faad8-150">If you're using Linux or macOS, use the `ls` command to get a directory listing and verify that the *myapp.dll* file was created.</span></span>

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp3.1/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

## <a name="create-the-dockerfile"></a><span data-ttu-id="faad8-151">创建 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="faad8-151">Create the Dockerfile</span></span>

<span data-ttu-id="faad8-152">`docker build` 命令使用 Dockerfile  文件来创建容器映像。</span><span class="sxs-lookup"><span data-stu-id="faad8-152">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="faad8-153">此文件是名为“Dockerfile”  的文本文件，它没有扩展名。</span><span class="sxs-lookup"><span data-stu-id="faad8-153">This file is a text file named *Dockerfile* that doesn't have an extension.</span></span>

<span data-ttu-id="faad8-154">在终端中，导航到你在启动时创建的工作文件夹的目录。</span><span class="sxs-lookup"><span data-stu-id="faad8-154">In your terminal, navigate up a directory to the working folder you created at the start.</span></span> <span data-ttu-id="faad8-155">在工作文件夹中创建名为“Dockerfile”的文件，在文本编辑器中打开它  。</span><span class="sxs-lookup"><span data-stu-id="faad8-155">Create a file named *Dockerfile* in your working folder and open it in a text editor.</span></span> <span data-ttu-id="faad8-156">根据要容器化的应用程序类型，选择 ASP.NET Core 运行时或 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="faad8-156">Depending on the type of application you're going to containerize, you'll choose either the ASP.NET Core runtime or the .NET Core runtime.</span></span> <span data-ttu-id="faad8-157">如有疑问，请选择包含 .NET Core 运行时的 ASP.NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="faad8-157">When in doubt, choose the ASP.NET Core runtime, which includes the .NET Core runtime.</span></span> <span data-ttu-id="faad8-158">本教程将使用 ASP.NET Core 运行时映像，但在前面部分中创建的应用是 .NET Core 应用。</span><span class="sxs-lookup"><span data-stu-id="faad8-158">This tutorial will use the ASP.NET Core runtime image, but the application created in the previous sections is an .NET Core application.</span></span>

- <span data-ttu-id="faad8-159">ASP.NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="faad8-159">ASP.NET Core runtime</span></span>

  ```dockerfile
  FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
  ```

- <span data-ttu-id="faad8-160">.NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="faad8-160">.NET Core runtime</span></span>

  ```dockerfile
  FROM mcr.microsoft.com/dotnet/core/runtime:3.1
  ```

<span data-ttu-id="faad8-161">`FROM` 命令指示 Docker 从指定存储库中拉取标记为“3.1”  的映像。</span><span class="sxs-lookup"><span data-stu-id="faad8-161">The `FROM` command tells Docker to pull down the image tagged **3.1** from the specified repository.</span></span> <span data-ttu-id="faad8-162">请确保拉取的运行时版本与 SDK 面向的运行时一致。</span><span class="sxs-lookup"><span data-stu-id="faad8-162">Make sure that you pull the runtime version that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="faad8-163">例如，在上一节中创建的应用使用的是 .NET Core 3.1 SDK，并且 Dockerfile  中引用的基本映像标记有 3.1  。</span><span class="sxs-lookup"><span data-stu-id="faad8-163">For example, the app created in the previous section used the .NET Core 3.1 SDK and the base image referred to in the *Dockerfile* is tagged with **3.1**.</span></span>

<span data-ttu-id="faad8-164">保存 Dockerfile 文件  。</span><span class="sxs-lookup"><span data-stu-id="faad8-164">Save the *Dockerfile* file.</span></span> <span data-ttu-id="faad8-165">工作文件夹的目录结果应如下所示。</span><span class="sxs-lookup"><span data-stu-id="faad8-165">The directory structure of the working folder should look like the following.</span></span> <span data-ttu-id="faad8-166">为节省本文的空间，删掉了一些更深级别的文件和文件夹：</span><span class="sxs-lookup"><span data-stu-id="faad8-166">Some of the deeper-level files and folders have been cut to save space in the article:</span></span>

```
docker-working
│   Dockerfile
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    ├───bin
    │   └───Release
    │       └───netcoreapp3.1
    │           └───publish
    │                   myapp.deps.json
    │                   myapp.exe
    │                   myapp.dll
    │                   myapp.pdb
    │                   myapp.runtimeconfig.json
    │
    └───obj
```

<span data-ttu-id="faad8-167">在终端中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="faad8-167">From your terminal, run the following command:</span></span>

```console
docker build -t myimage -f Dockerfile .
```

<span data-ttu-id="faad8-168">Docker 会处理 Dockerfile  中的每一行。</span><span class="sxs-lookup"><span data-stu-id="faad8-168">Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="faad8-169">`docker build` 命令中的 `.` 指示 Docker 在当前文件夹中查找 Dockerfile  。</span><span class="sxs-lookup"><span data-stu-id="faad8-169">The `.` in the `docker build` command tells Docker to use the current folder to find a *Dockerfile*.</span></span> <span data-ttu-id="faad8-170">此命令生成映像，并创建指向相应映像的本地存储库“myimage”  。</span><span class="sxs-lookup"><span data-stu-id="faad8-170">This command builds the image and creates a local repository named **myimage** that points to that image.</span></span> <span data-ttu-id="faad8-171">在此命令完成后，运行 `docker images` 以列出已安装的映像：</span><span class="sxs-lookup"><span data-stu-id="faad8-171">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              38db0eb8f648        4 weeks ago         346MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 38db0eb8f648        4 weeks ago         346MB
```

<span data-ttu-id="faad8-172">请注意，两个映像共用相同的“IMAGE ID”  值。</span><span class="sxs-lookup"><span data-stu-id="faad8-172">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="faad8-173">两个映像使用的 ID 值相同是因为，Dockerfile  中的唯一命令是在现有映像的基础之上生成新映像。</span><span class="sxs-lookup"><span data-stu-id="faad8-173">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="faad8-174">接下来，在 Dockerfile  中添加两个命令。</span><span class="sxs-lookup"><span data-stu-id="faad8-174">Let's add two commands to the *Dockerfile*.</span></span> <span data-ttu-id="faad8-175">两个命令都新建映像层，最后一个命令表示 myimage  存储库条目指向的映像。</span><span class="sxs-lookup"><span data-stu-id="faad8-175">Each command creates a new image layer with the final command representing the image the **myimage** repository entry points to.</span></span>

```dockerfile
COPY app/bin/Release/netcoreapp3.1/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

<span data-ttu-id="faad8-176">`COPY` 命令指示 Docker 将计算机上的指定文件夹复制到容器中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="faad8-176">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="faad8-177">在此示例中，“发布”  文件夹被复制到容器中的“应用”  文件夹。</span><span class="sxs-lookup"><span data-stu-id="faad8-177">In this example, the *publish* folder is copied to a folder named *app* in the container.</span></span>

<span data-ttu-id="faad8-178">下一个命令 `ENTRYPOINT` 指示 Docker 将容器配置为可执行文件运行。</span><span class="sxs-lookup"><span data-stu-id="faad8-178">The next command, `ENTRYPOINT`, tells Docker to configure the container to run as an executable.</span></span> <span data-ttu-id="faad8-179">在容器启动时，`ENTRYPOINT` 命令运行。</span><span class="sxs-lookup"><span data-stu-id="faad8-179">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="faad8-180">当此命令结束时，容器也会自动停止。</span><span class="sxs-lookup"><span data-stu-id="faad8-180">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="faad8-181">在终端中，运行 `docker build -t myimage -f Dockerfile .`；在此命令完成后，运行 `docker images`。</span><span class="sxs-lookup"><span data-stu-id="faad8-181">From your terminal, run `docker build -t myimage -f Dockerfile .` and when that command finishes, run `docker images`.</span></span>

```console
> docker build -t myimage -f Dockerfile .
Sending build context to Docker daemon  1.624MB
Step 1/3 : FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
 ---> 38db0eb8f648
Step 2/3 : COPY app/bin/Release/netcoreapp3.1/publish/ app/
 ---> 37873673e468
Step 3/3 : ENTRYPOINT ["dotnet", "app/myapp.dll"]
 ---> Running in d8deb7b3aa9e
Removing intermediate container d8deb7b3aa9e
 ---> 0d602ca35c1d
Successfully built 0d602ca35c1d
Successfully tagged myimage:latest

> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              0d602ca35c1d        4 seconds ago       346MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 38db0eb8f648        4 weeks ago         346MB
```

<span data-ttu-id="faad8-182">Dockerfile  中的每个命令生成了一个层，并创建了“IMAGE ID”  。</span><span class="sxs-lookup"><span data-stu-id="faad8-182">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="faad8-183">最终“IMAGE ID”  是“ddcc6646461b”  （你的 ID 会有所不同），接下来在此映像的基础之上创建容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-183">The final **IMAGE ID** (yours will be different) is **ddcc6646461b** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="faad8-184">创建容器</span><span class="sxs-lookup"><span data-stu-id="faad8-184">Create a container</span></span>

<span data-ttu-id="faad8-185">至此，已有包含应用的映像，可以创建容器了。</span><span class="sxs-lookup"><span data-stu-id="faad8-185">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="faad8-186">可以通过两种方式来创建容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-186">You can create a container in two ways.</span></span> <span data-ttu-id="faad8-187">首先，新建已停止的容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-187">First, create a new container that is stopped.</span></span>

```console
> docker create myimage
ceda87b219a4e55e9ad5d833ee1a7ea4da21b5ea7ce5a7d08f3051152e784944
```

<span data-ttu-id="faad8-188">上面的 `docker create` 命令在 myimage  映像的基础之上创建容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-188">The `docker create` command from above will create a container based on the **myimage** image.</span></span> <span data-ttu-id="faad8-189">此命令的输出显示已创建容器的“CONTAINER ID”  （你的 ID 会有所不同）。</span><span class="sxs-lookup"><span data-stu-id="faad8-189">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="faad8-190">若要查看所有  容器的列表，请使用 `docker ps -a` 命令：</span><span class="sxs-lookup"><span data-stu-id="faad8-190">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               gallant_lehmann
```

### <a name="manage-the-container"></a><span data-ttu-id="faad8-191">管理容器</span><span class="sxs-lookup"><span data-stu-id="faad8-191">Manage the container</span></span>

<span data-ttu-id="faad8-192">每个容器都分配有随机名称，可用来引用相应容器实例。</span><span class="sxs-lookup"><span data-stu-id="faad8-192">Each container is assigned a random name that you can use to refer to that container instance.</span></span> <span data-ttu-id="faad8-193">例如，自动创建的容器选择了名称“gallant_lehmann”  （你的名称会有所不同），此名称可用于启动容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-193">For example, the container that was created automatically chose the name **gallant_lehmann** (yours will be different) and that name can be used to start the container.</span></span> <span data-ttu-id="faad8-194">可以使用 `docker create --name` 参数将自动名称替代为特定名称。</span><span class="sxs-lookup"><span data-stu-id="faad8-194">You override the automatic name with a specific one by using the `docker create --name` parameter.</span></span>

<span data-ttu-id="faad8-195">下面的示例使用 `docker start` 命令来启动容器，然后使用 `docker ps` 命令仅显示正在运行的容器：</span><span class="sxs-lookup"><span data-stu-id="faad8-195">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```console
> docker start gallant_lehmann
gallant_lehmann

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           gallant_lehmann
```

<span data-ttu-id="faad8-196">同样，`docker stop` 命令会停止容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-196">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="faad8-197">下面的示例使用 `docker stop` 命令来停止容器，然后使用 `docker ps` 命令来显示未在运行的容器：</span><span class="sxs-lookup"><span data-stu-id="faad8-197">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running:</span></span>

```console
> docker stop gallant_lehmann
gallant_lehmann

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="faad8-198">连接到容器</span><span class="sxs-lookup"><span data-stu-id="faad8-198">Connect to a container</span></span>

<span data-ttu-id="faad8-199">在容器运行后，可以连接到它来查看输出。</span><span class="sxs-lookup"><span data-stu-id="faad8-199">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="faad8-200">使用 `docker start` 和 `docker attach` 命令，启动容器并查看输出流。</span><span class="sxs-lookup"><span data-stu-id="faad8-200">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="faad8-201">在此示例中，<kbd>CTRL + C</kbd> 击键用于从正在运行的容器中分离出来。</span><span class="sxs-lookup"><span data-stu-id="faad8-201">In this example, the <kbd>CTRL + C</kbd> keystroke is used to detach from the running container.</span></span> <span data-ttu-id="faad8-202">此击键其实是结束容器中的进程，进而停止容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-202">This keystroke may actually end the process in the container, which will stop the container.</span></span> <span data-ttu-id="faad8-203">`--sig-proxy=false` 参数可确保 <kbd>Ctrl + C</kbd> 不停止容器中的进程。</span><span class="sxs-lookup"><span data-stu-id="faad8-203">The `--sig-proxy=false` parameter ensures that <kbd>CTRL + C</kbd> won't stop the process in the container.</span></span>

<span data-ttu-id="faad8-204">从容器中分离出来后重新连接，以验证它是否仍在运行和计数。</span><span class="sxs-lookup"><span data-stu-id="faad8-204">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

```console
> docker start gallant_lehmann
gallant_lehmann

> docker attach --sig-proxy=false gallant_lehmann
Counter: 7
Counter: 8
Counter: 9
^C

> docker attach --sig-proxy=false gallant_lehmann
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a><span data-ttu-id="faad8-205">删除容器</span><span class="sxs-lookup"><span data-stu-id="faad8-205">Delete a container</span></span>

<span data-ttu-id="faad8-206">就本文而言，你不希望存在不执行任何操作的容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-206">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="faad8-207">删除前面创建的容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-207">Delete the container you previously created.</span></span> <span data-ttu-id="faad8-208">如果容器正在运行，停止容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-208">If the container is running, stop it.</span></span>

```console
> docker stop gallant_lehmann
```

<span data-ttu-id="faad8-209">下面的示例列出了所有容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-209">The following example lists all containers.</span></span> <span data-ttu-id="faad8-210">然后，它使用 `docker rm` 命令来删除容器，并再次检查是否有任何正在运行的容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-210">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             gallant_lehmann

> docker rm gallant_lehmann
gallant_lehmann

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="faad8-211">单次运行</span><span class="sxs-lookup"><span data-stu-id="faad8-211">Single run</span></span>

<span data-ttu-id="faad8-212">Docker 提供了 `docker run` 命令，用于将容器作为单一命令进行创建和运行。</span><span class="sxs-lookup"><span data-stu-id="faad8-212">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="faad8-213">使用此命令，无需依次运行 `docker create` 和 `docker start`。</span><span class="sxs-lookup"><span data-stu-id="faad8-213">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="faad8-214">另外，还可以将此命令设置为，在容器停止时自动删除容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-214">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="faad8-215">例如，使用 `docker run -it --rm` 可以执行两项操作，先自动使用当前终端连接到容器，再在容器完成时删除容器：</span><span class="sxs-lookup"><span data-stu-id="faad8-215">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```console
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="faad8-216">使用 `docker run -it`，<kbd>CTRL + C</kbd> 命令会停止在容器中运行的进程，进而停止容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-216">With `docker run -it`, the <kbd>CTRL + C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="faad8-217">由于提供了 `--rm` 参数，因此在进程停止时自动删除容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-217">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="faad8-218">验证它是否不存在：</span><span class="sxs-lookup"><span data-stu-id="faad8-218">Verify that it doesn't exist:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="faad8-219">更改 ENTRYPOINT</span><span class="sxs-lookup"><span data-stu-id="faad8-219">Change the ENTRYPOINT</span></span>

<span data-ttu-id="faad8-220">使用 `docker run` 命令，还可以修改 Dockerfile  中的 `ENTRYPOINT` 命令，并运行其他内容，但只能针对相应容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-220">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="faad8-221">例如，使用以下命令来运行 `bash` 或 `cmd.exe`。</span><span class="sxs-lookup"><span data-stu-id="faad8-221">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="faad8-222">根据需要，编辑此命令。</span><span class="sxs-lookup"><span data-stu-id="faad8-222">Edit the command as necessary.</span></span>

#### <a name="windows"></a><span data-ttu-id="faad8-223">Windows</span><span class="sxs-lookup"><span data-stu-id="faad8-223">Windows</span></span>

<span data-ttu-id="faad8-224">在本例中，`ENTRYPOINT` 更改为 `cmd.exe`。</span><span class="sxs-lookup"><span data-stu-id="faad8-224">In this example, `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="faad8-225">通过按下 <kbd>CTRL</kbd>+<kbd>C</kbd> 来结束进程并停止容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-225"><kbd>CTRL</kbd>+<kbd>C</kbd> is pressed to end the process and stop the container.</span></span>

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

#### <a name="linux"></a><span data-ttu-id="faad8-226">Linux</span><span class="sxs-lookup"><span data-stu-id="faad8-226">Linux</span></span>

<span data-ttu-id="faad8-227">在本例中，`ENTRYPOINT` 更改为 `bash`。</span><span class="sxs-lookup"><span data-stu-id="faad8-227">In this example, `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="faad8-228">通过运行 `quit` 命令来结束进程并停止容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-228">The `quit` command is run which ends the process and stop the container.</span></span>

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a><span data-ttu-id="faad8-229">重要命令</span><span class="sxs-lookup"><span data-stu-id="faad8-229">Essential commands</span></span>

<span data-ttu-id="faad8-230">Docker 有许多不同的命令，可用于执行你要对容器和映像执行的操作。</span><span class="sxs-lookup"><span data-stu-id="faad8-230">Docker has many different commands that cover what you want to do with your container and images.</span></span> <span data-ttu-id="faad8-231">下面这些 Docker 命令对于管理容器来说至关重要：</span><span class="sxs-lookup"><span data-stu-id="faad8-231">These Docker commands are essential to managing your containers:</span></span>

- [<span data-ttu-id="faad8-232">docker build</span><span class="sxs-lookup"><span data-stu-id="faad8-232">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
- [<span data-ttu-id="faad8-233">docker run</span><span class="sxs-lookup"><span data-stu-id="faad8-233">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
- [<span data-ttu-id="faad8-234">docker ps</span><span class="sxs-lookup"><span data-stu-id="faad8-234">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
- [<span data-ttu-id="faad8-235">docker stop</span><span class="sxs-lookup"><span data-stu-id="faad8-235">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
- [<span data-ttu-id="faad8-236">docker rm</span><span class="sxs-lookup"><span data-stu-id="faad8-236">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
- [<span data-ttu-id="faad8-237">docker rmi</span><span class="sxs-lookup"><span data-stu-id="faad8-237">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
- [<span data-ttu-id="faad8-238">docker image</span><span class="sxs-lookup"><span data-stu-id="faad8-238">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="faad8-239">清理资源</span><span class="sxs-lookup"><span data-stu-id="faad8-239">Clean up resources</span></span>

<span data-ttu-id="faad8-240">在本教程中，你创建了容器和映像。</span><span class="sxs-lookup"><span data-stu-id="faad8-240">During this tutorial, you created containers and images.</span></span> <span data-ttu-id="faad8-241">如果需要，请删除这些资源。</span><span class="sxs-lookup"><span data-stu-id="faad8-241">If you want, delete these resources.</span></span> <span data-ttu-id="faad8-242">以下命令可用于</span><span class="sxs-lookup"><span data-stu-id="faad8-242">Use the following commands to</span></span>

01. <span data-ttu-id="faad8-243">列出所有容器</span><span class="sxs-lookup"><span data-stu-id="faad8-243">List all containers</span></span>

    ```console
    > docker ps -a
    ```

02. <span data-ttu-id="faad8-244">停止正在运行的容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-244">Stop containers that are running.</span></span> <span data-ttu-id="faad8-245">`CONTAINER_NAME` 表示自动分配给容器的名称。</span><span class="sxs-lookup"><span data-stu-id="faad8-245">The `CONTAINER_NAME` represents the name automatically assigned to the container.</span></span>

    ```console
    > docker stop CONTAINER_NAME
    ```

03. <span data-ttu-id="faad8-246">删除容器</span><span class="sxs-lookup"><span data-stu-id="faad8-246">Delete the container</span></span>

    ```console
    > docker rm CONTAINER_NAME
    ```

<span data-ttu-id="faad8-247">接下来，删除计算机上不再需要的任何映像。</span><span class="sxs-lookup"><span data-stu-id="faad8-247">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="faad8-248">依次删除 Dockerfile  创建的映像，以及 Dockerfile  所依据的 .NET Core 映像。</span><span class="sxs-lookup"><span data-stu-id="faad8-248">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="faad8-249">可以使用 IMAGE ID  或 REPOSITORY:TAG  格式字符串。</span><span class="sxs-lookup"><span data-stu-id="faad8-249">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/aspnet:3.1
```

<span data-ttu-id="faad8-250">使用 `docker images` 命令来列出已安装的映像。</span><span class="sxs-lookup"><span data-stu-id="faad8-250">Use the `docker images` command to see a list of images installed.</span></span>

> [!NOTE]
> <span data-ttu-id="faad8-251">映像文件可能很大。</span><span class="sxs-lookup"><span data-stu-id="faad8-251">Image files can be large.</span></span> <span data-ttu-id="faad8-252">通常情况下，需要删除在测试和开发应用期间创建的临时容器。</span><span class="sxs-lookup"><span data-stu-id="faad8-252">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="faad8-253">如果计划在相应运行时的基础之上生成其他映像，通常会将基础映像与运行时一同安装。</span><span class="sxs-lookup"><span data-stu-id="faad8-253">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="faad8-254">后续步骤</span><span class="sxs-lookup"><span data-stu-id="faad8-254">Next steps</span></span>

- [<span data-ttu-id="faad8-255">了解如何容器化 ASP.NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="faad8-255">Learn how to containerize an ASP.NET Core application.</span></span>](/aspnet/core/host-and-deploy/docker/building-net-docker-images)
- [<span data-ttu-id="faad8-256">试学“ASP.NET Core 微服务”教程。</span><span class="sxs-lookup"><span data-stu-id="faad8-256">Try the ASP.NET Core Microservice Tutorial.</span></span>](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
- [<span data-ttu-id="faad8-257">查看支持容器的 Azure 服务。</span><span class="sxs-lookup"><span data-stu-id="faad8-257">Review the Azure services that support containers.</span></span>](https://azure.microsoft.com/overview/containers/)
- [<span data-ttu-id="faad8-258">了解 Dockerfile 命令。</span><span class="sxs-lookup"><span data-stu-id="faad8-258">Read about Dockerfile commands.</span></span>](https://docs.docker.com/engine/reference/builder/)
- [<span data-ttu-id="faad8-259">了解用于 Visual Studio 的容器工具</span><span class="sxs-lookup"><span data-stu-id="faad8-259">Explore the Container Tools for Visual Studio</span></span>](/visualstudio/containers/overview)
