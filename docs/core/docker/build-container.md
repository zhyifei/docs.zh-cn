---
title: 通过 Docker 使应用程序容器化的教程
description: 在本教程中，你将了解如何使用 Docker 容器化 .NET Core 应用。
ms.date: 04/10/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: a96f96bd91976b0966fb7e8d0c8fb6fb7842cfe3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631866"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="a6cad-103">教程：使 .NET Core 应用程序容器化</span><span class="sxs-lookup"><span data-stu-id="a6cad-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="a6cad-104">本教程介绍如何生成包含 .NET Core 应用程序的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="a6cad-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="a6cad-105">此映像可用于为本地开发环境、私有云或公有云创建容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="a6cad-106">你将了解如何：</span><span class="sxs-lookup"><span data-stu-id="a6cad-106">You'll learn to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="a6cad-107">创建并发布简单的 .NET Core 应用</span><span class="sxs-lookup"><span data-stu-id="a6cad-107">Create and publish a simple .NET Core app</span></span>
> * <span data-ttu-id="a6cad-108">创建并配置用于 .NET Core 的 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="a6cad-108">Create and configure a Dockerfile for .NET Core</span></span>
> * <span data-ttu-id="a6cad-109">生成 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="a6cad-109">Build a Docker image</span></span>
> * <span data-ttu-id="a6cad-110">创建并运行 Docker 容器</span><span class="sxs-lookup"><span data-stu-id="a6cad-110">Create and run a Docker container</span></span>

<span data-ttu-id="a6cad-111">你将了解用于 .NET Core 应用的 Docker 容器生成和部署任务。</span><span class="sxs-lookup"><span data-stu-id="a6cad-111">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="a6cad-112">Docker 平台使用 Docker 引擎快速生成应用，并将应用打包为 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="a6cad-112">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="a6cad-113">这些映像采用 Dockerfile 格式编写，以供在分层容器中部署和运行。</span><span class="sxs-lookup"><span data-stu-id="a6cad-113">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a6cad-114">系统必备</span><span class="sxs-lookup"><span data-stu-id="a6cad-114">Prerequisites</span></span>

<span data-ttu-id="a6cad-115">安装以下必备组件：</span><span class="sxs-lookup"><span data-stu-id="a6cad-115">Install the following prerequisites:</span></span>

- <span data-ttu-id="a6cad-116">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)\\</span><span class="sxs-lookup"><span data-stu-id="a6cad-116">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)\\</span></span>
<span data-ttu-id="a6cad-117">如果已安装 .NET Core，请使用 `dotnet --info` 命令来确定使用的是哪个 SDK。</span><span class="sxs-lookup"><span data-stu-id="a6cad-117">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>

- [<span data-ttu-id="a6cad-118">Docker 社区版</span><span class="sxs-lookup"><span data-stu-id="a6cad-118">Docker Community Edition</span></span>](https://www.docker.com/products/docker-desktop)

- <span data-ttu-id="a6cad-119">用于 Dockerfile 和 .NET Core 示例应用的临时工作目录。</span><span class="sxs-lookup"><span data-stu-id="a6cad-119">A temporary working directory for the *Dockerfile* and .NET Core example app.</span></span>

### <a name="use-sdk-version-22"></a><span data-ttu-id="a6cad-120">使用 SDK 版本 2.2</span><span class="sxs-lookup"><span data-stu-id="a6cad-120">Use SDK version 2.2</span></span>

<span data-ttu-id="a6cad-121">如果使用的是更高版本 SDK（如 3.0），请务必强制应用使用 SDK 2.2。</span><span class="sxs-lookup"><span data-stu-id="a6cad-121">If you're using an SDK that is newer, like 3.0, make sure that your app is forced to use the 2.2 SDK.</span></span> <span data-ttu-id="a6cad-122">在工作目录中创建名为 `global.json` 的文件，并粘贴以下 json 代码：</span><span class="sxs-lookup"><span data-stu-id="a6cad-122">Create a file named `global.json` in your working directory and paste in the following json code:</span></span>

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

<span data-ttu-id="a6cad-123">保存此文件。</span><span class="sxs-lookup"><span data-stu-id="a6cad-123">Save this file.</span></span> <span data-ttu-id="a6cad-124">此文件会强制 .NET Core 对从这个目录及其下位置调用的任何 `dotnet` 命令使用版本 2.2。</span><span class="sxs-lookup"><span data-stu-id="a6cad-124">The presence of file will force .NET Core to use version 2.2 for any `dotnet` command called from this directory and below.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="a6cad-125">创建 .Net Core 应用</span><span class="sxs-lookup"><span data-stu-id="a6cad-125">Create .NET Core app</span></span>

<span data-ttu-id="a6cad-126">需要有可供 Docker 容器运行的 .NET Core 应用。</span><span class="sxs-lookup"><span data-stu-id="a6cad-126">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="a6cad-127">打开终端，然后创建并进入工作目录。</span><span class="sxs-lookup"><span data-stu-id="a6cad-127">Open your terminal, create a working directory, and enter it.</span></span> <span data-ttu-id="a6cad-128">在工作目录中，运行下面的命令，以在子目录“应用”中新建一个项目：</span><span class="sxs-lookup"><span data-stu-id="a6cad-128">In the working directory, run the following command to create a new project in a subdirectory named app:</span></span>

```console
dotnet new console -o app -n myapp
```

<span data-ttu-id="a6cad-129">此命令新建目录“应用”，并生成“Hello World”应用。</span><span class="sxs-lookup"><span data-stu-id="a6cad-129">That command creates a new directory named *app* and generates a "Hello World" app.</span></span> <span data-ttu-id="a6cad-130">可以通过测试此应用来看看它有何用途。</span><span class="sxs-lookup"><span data-stu-id="a6cad-130">You can test this app to see what it does.</span></span> <span data-ttu-id="a6cad-131">进入“应用”目录，并执行命令 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="a6cad-131">Enter the *app* directory and execute the command `dotnet run`.</span></span> <span data-ttu-id="a6cad-132">输出如下：</span><span class="sxs-lookup"><span data-stu-id="a6cad-132">You'll see the following output:</span></span>

```console
> dotnet run
Hello World!
```

<span data-ttu-id="a6cad-133">默认模板创建应用，此应用先打印输出到终端，再退出。</span><span class="sxs-lookup"><span data-stu-id="a6cad-133">The default template creates an app that prints to the terminal and then exits.</span></span> <span data-ttu-id="a6cad-134">本教程将使用无限循环的应用。</span><span class="sxs-lookup"><span data-stu-id="a6cad-134">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="a6cad-135">在文本编辑器中，打开“Program.cs”文件。</span><span class="sxs-lookup"><span data-stu-id="a6cad-135">Open the **Program.cs** file in a text editor.</span></span> <span data-ttu-id="a6cad-136">它应如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="a6cad-136">It should currently look like the following code:</span></span>

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

<span data-ttu-id="a6cad-137">将此文件替换为以下每秒计数一次的代码：</span><span class="sxs-lookup"><span data-stu-id="a6cad-137">Replace the file with the following code that counts numbers every second:</span></span>

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

<span data-ttu-id="a6cad-138">保存此文件，并使用 `dotnet run` 再次测试程序。</span><span class="sxs-lookup"><span data-stu-id="a6cad-138">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="a6cad-139">请注意，此应用无限期运行。</span><span class="sxs-lookup"><span data-stu-id="a6cad-139">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="a6cad-140">使用取消命令 <kbd>CTRL + C</kbd> 可以停止运行。</span><span class="sxs-lookup"><span data-stu-id="a6cad-140">Use the cancel command <kbd>CTRL + C</kbd> to stop it.</span></span> <span data-ttu-id="a6cad-141">输出如下：</span><span class="sxs-lookup"><span data-stu-id="a6cad-141">You'll see the following output:</span></span>

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="a6cad-142">如果你在命令行中向应用传递一个数字，它就只会计数到这个数字，然后退出。</span><span class="sxs-lookup"><span data-stu-id="a6cad-142">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="a6cad-143">试一试用 `dotnet run -- 5` 计数到 5。</span><span class="sxs-lookup"><span data-stu-id="a6cad-143">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!NOTE]
> <span data-ttu-id="a6cad-144">`--` 后面的任何参数都传递到应用。</span><span class="sxs-lookup"><span data-stu-id="a6cad-144">Any parameters after `--` are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="a6cad-145">发布 .Net Core 应用</span><span class="sxs-lookup"><span data-stu-id="a6cad-145">Publish .NET Core app</span></span>

<span data-ttu-id="a6cad-146">请先发布 .NET Core 应用，再将它添加到 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="a6cad-146">Before you add your .NET Core app to the Docker image, publish it.</span></span> <span data-ttu-id="a6cad-147">容器会执行启动后的应用的发布版本。</span><span class="sxs-lookup"><span data-stu-id="a6cad-147">The container will execute the published version of the app when it's started.</span></span>

<span data-ttu-id="a6cad-148">在工作目录中，进入包含示例源代码的“应用”目录，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a6cad-148">From the working directory, enter the **app** directory with the example source code and run the following command:</span></span>

```console
dotnet publish -c Release
```

<span data-ttu-id="a6cad-149">此命令将应用编译到应用输出文件夹中的“发布”文件夹内。</span><span class="sxs-lookup"><span data-stu-id="a6cad-149">This command compiles your app to the **publish** folder in the output folder of your app.</span></span> <span data-ttu-id="a6cad-150">工作目录中的“发布”文件夹的路径应为 `.\app\bin\Release\netcoreapp2.2\publish\`</span><span class="sxs-lookup"><span data-stu-id="a6cad-150">The path to the **publish** folder from the working directory should be `.\app\bin\Release\netcoreapp2.2\publish\`</span></span>

<span data-ttu-id="a6cad-151">获取“发布”文件夹的目录清单，以验证 myapp.dll 是否已创建。</span><span class="sxs-lookup"><span data-stu-id="a6cad-151">Get a directory listing of the publish folder to verify that the **myapp.dll** was created.</span></span> <span data-ttu-id="a6cad-152">在“应用”目录中，运行下列命令之一：</span><span class="sxs-lookup"><span data-stu-id="a6cad-152">From the **app** directory, run one of the following commands:</span></span>

```console
> dir bin\Release\netcoreapp2.2\publish
 Directory of C:\path-to-working-dir\app\bin\Release\netcoreapp2.2\publish

04/05/2019  11:00 AM    <DIR>          .
04/05/2019  11:00 AM    <DIR>          ..
04/05/2019  11:00 AM               447 myapp.deps.json
04/05/2019  11:00 AM             4,608 myapp.dll
04/05/2019  11:00 AM               448 myapp.pdb
04/05/2019  11:00 AM               154 myapp.runtimeconfig.json
```

```bash
me@DESKTOP:/path-to-working-dir/app$ ls bin/Release/netcoreapp2.2/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

<span data-ttu-id="a6cad-153">在终端中，转到上一级目录，即工作目录。</span><span class="sxs-lookup"><span data-stu-id="a6cad-153">In your terminal, go up a directory to the working directory.</span></span>

## <a name="create-the-dockerfile"></a><span data-ttu-id="a6cad-154">创建 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="a6cad-154">Create the Dockerfile</span></span>

<span data-ttu-id="a6cad-155">`docker build` 命令使用 Dockerfile 文件来创建容器映像。</span><span class="sxs-lookup"><span data-stu-id="a6cad-155">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="a6cad-156">此文件是名为“Dockerfile”的纯文本文件，它没有扩展名。</span><span class="sxs-lookup"><span data-stu-id="a6cad-156">This file is a plaintext file named *Dockerfile* that does not have an extension.</span></span> <span data-ttu-id="a6cad-157">在工作目录中创建名为“Dockerfile”的文件，并在文本编辑器中打开它。</span><span class="sxs-lookup"><span data-stu-id="a6cad-157">Create a file named *Dockerfile* in your working directory and open it in a text editor.</span></span> <span data-ttu-id="a6cad-158">将以下命令添加为此文件的首行：</span><span class="sxs-lookup"><span data-stu-id="a6cad-158">Add the following command as the first line of the file:</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/core/runtime:2.2
```

<span data-ttu-id="a6cad-159">`FROM` 命令指示 Docker 从 mcr.microsoft.com/dotnet/core/runtime 存储库拉取标记为“2.2”的映像。</span><span class="sxs-lookup"><span data-stu-id="a6cad-159">The `FROM` command tells Docker to pull down the image tagged **2.2** from the **mcr.microsoft.com/dotnet/core/runtime** repository.</span></span> <span data-ttu-id="a6cad-160">请确保拉取的 .NET Core 运行时与 SDK 定目标到的运行时一致。</span><span class="sxs-lookup"><span data-stu-id="a6cad-160">Make sure that you pull the .NET Core runtime that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="a6cad-161">例如，上一部分中创建的应用定目标到 .Net Core 2.2，且使用 .Net Core 2.2 SDK。</span><span class="sxs-lookup"><span data-stu-id="a6cad-161">For example, the app created in the previous section used the .NET Core 2.2 SDK and created an app that targeted .NET Core 2.2.</span></span> <span data-ttu-id="a6cad-162">因此，Dockerfile 中引用的基础映像被标记为“2.2”。</span><span class="sxs-lookup"><span data-stu-id="a6cad-162">So the base image referred to in the *Dockerfile* is tagged with **2.2**.</span></span>

<span data-ttu-id="a6cad-163">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="a6cad-163">Save the file.</span></span> <span data-ttu-id="a6cad-164">在终端中，运行 `docker build -t myimage .`，然后 Docker 会处理 Dockerfile 中的每一行。</span><span class="sxs-lookup"><span data-stu-id="a6cad-164">From your terminal, run `docker build -t myimage .` and Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="a6cad-165">`docker build` 命令中的 `.` 指示 Docker 在当前目录中查找 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="a6cad-165">The `.` in the `docker build` command tells docker to use the current directory to find a *Dockerfile*.</span></span> <span data-ttu-id="a6cad-166">此命令生成映像，并创建指向相应映像的本地存储库“myimage”。</span><span class="sxs-lookup"><span data-stu-id="a6cad-166">This command builds the image and creates a local repository named **myimage** that points to that image.</span></span> <span data-ttu-id="a6cad-167">在此命令完成后，运行 `docker images` 以列出已安装的映像：</span><span class="sxs-lookup"><span data-stu-id="a6cad-167">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
myimage                                 latest              d51bb4452469        2 days ago          314MB
```

<span data-ttu-id="a6cad-168">请注意，两个映像共用相同的“IMAGE ID”值。</span><span class="sxs-lookup"><span data-stu-id="a6cad-168">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="a6cad-169">两个映像使用的 ID 值相同是因为，Dockerfile 中的唯一命令是在现有映像的基础之上生成新映像。</span><span class="sxs-lookup"><span data-stu-id="a6cad-169">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="a6cad-170">接下来，在 Dockerfile 中添加两个命令。</span><span class="sxs-lookup"><span data-stu-id="a6cad-170">Let's add two commands to the *Dockerfile*.</span></span> <span data-ttu-id="a6cad-171">两个命令都新建映像层，最后一个命令表示 myimage 存储库将指向的映像。</span><span class="sxs-lookup"><span data-stu-id="a6cad-171">Each command creates a new image layer with the final command representing the image the **myimage** repository will point to.</span></span>

```dockerfile
COPY app/bin/Release/netcoreapp2.2/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

<span data-ttu-id="a6cad-172">`COPY` 命令指示 Docker 将计算机上的指定文件夹复制到容器中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="a6cad-172">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="a6cad-173">在此示例中，“发布”文件夹被复制到容器中的“应用”文件夹。</span><span class="sxs-lookup"><span data-stu-id="a6cad-173">In this example, the **publish** folder is copied to a folder named **app** in the container.</span></span>

<span data-ttu-id="a6cad-174">下一个命令 `ENTRYPOINT` 指示 Docker 将容器配置为可执行文件运行。</span><span class="sxs-lookup"><span data-stu-id="a6cad-174">The next command, `ENTRYPOINT`, tells docker to configure the container to run as an executable.</span></span> <span data-ttu-id="a6cad-175">在容器启动时，`ENTRYPOINT` 命令运行。</span><span class="sxs-lookup"><span data-stu-id="a6cad-175">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="a6cad-176">当此命令结束时，容器也会自动停止。</span><span class="sxs-lookup"><span data-stu-id="a6cad-176">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="a6cad-177">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="a6cad-177">Save the file.</span></span> <span data-ttu-id="a6cad-178">在终端中，运行 `docker build -t myimage .`；在此命令完成后，运行 `docker images`。</span><span class="sxs-lookup"><span data-stu-id="a6cad-178">From your terminal, run `docker build -t myimage .` and when that command finishes, run `docker images`.</span></span>

```console
> docker build -t myimage .
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

<span data-ttu-id="a6cad-179">Dockerfile 中的每个命令生成了一个层，并创建了“IMAGE ID”。</span><span class="sxs-lookup"><span data-stu-id="a6cad-179">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="a6cad-180">最终“IMAGE ID”是“ddcc6646461b”（你的 ID 会有所不同），接下来在此映像的基础之上创建容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-180">The final **IMAGE ID** (yours will be different) is **ddcc6646461b** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="a6cad-181">创建容器</span><span class="sxs-lookup"><span data-stu-id="a6cad-181">Create a container</span></span>

<span data-ttu-id="a6cad-182">至此，已有包含应用的映像，可以创建容器了。</span><span class="sxs-lookup"><span data-stu-id="a6cad-182">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="a6cad-183">可以通过两种方式来创建容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-183">You can create a container in two ways.</span></span> <span data-ttu-id="a6cad-184">首先，新建已停止的容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-184">First, create a new container that is stopped.</span></span>

```console
> docker create myimage
0e8f3c2ca32ce773712a5cca38750f41259a4e54e04bdf0946087e230ad7066c
```

<span data-ttu-id="a6cad-185">上面的 `docker create` 命令在 myimage 映像的基础之上创建容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-185">The `docker create` command from above will create a container based on the **myimage** image.</span></span> <span data-ttu-id="a6cad-186">此命令的输出显示已创建容器的“CONTAINER ID”（你的 ID 会有所不同）。</span><span class="sxs-lookup"><span data-stu-id="a6cad-186">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="a6cad-187">若要查看所有容器的列表，请使用 `docker ps -a` 命令：</span><span class="sxs-lookup"><span data-stu-id="a6cad-187">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               boring_matsumoto
```

### <a name="manage-the-container"></a><span data-ttu-id="a6cad-188">管理容器</span><span class="sxs-lookup"><span data-stu-id="a6cad-188">Manage the container</span></span>

<span data-ttu-id="a6cad-189">每个容器都分配有随机名称，可用来引用相应容器实例。</span><span class="sxs-lookup"><span data-stu-id="a6cad-189">Each container is assigned a random name that you can use to refer to that container instance.</span></span> <span data-ttu-id="a6cad-190">例如，自动创建的容器选择了名称“boring_matsumoto”（你的名称会有所不同），此名称可用于启动容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-190">For example, the container that was created automatically chose the name **boring_matsumoto** (yours will be different) and that name can be used to start the container.</span></span> <span data-ttu-id="a6cad-191">可以使用 `docker create --name` 参数将自动名称替代为特定名称。</span><span class="sxs-lookup"><span data-stu-id="a6cad-191">You override the automatic name with a specific one by using the `docker create --name` parameter.</span></span>

<span data-ttu-id="a6cad-192">下面的示例使用 `docker start` 命令来启动容器，然后使用 `docker ps` 命令仅显示正在运行的容器：</span><span class="sxs-lookup"><span data-stu-id="a6cad-192">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```console
> docker start boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           boring_matsumoto
```

<span data-ttu-id="a6cad-193">同样，`docker stop` 命令会停止容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-193">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="a6cad-194">下面的示例使用 `docker stop` 命令来停止容器，然后使用 `docker ps` 命令来显示没有正在运行的容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-194">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running.</span></span>

```console
> docker stop boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="a6cad-195">连接到容器</span><span class="sxs-lookup"><span data-stu-id="a6cad-195">Connect to a container</span></span>

<span data-ttu-id="a6cad-196">在容器运行后，可以连接到它来查看输出。</span><span class="sxs-lookup"><span data-stu-id="a6cad-196">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="a6cad-197">使用 `docker start` 和 `docker attach` 命令，启动容器并查看输出流。</span><span class="sxs-lookup"><span data-stu-id="a6cad-197">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="a6cad-198">在此示例中，<kbd>CTRL + C</kbd> 命令用于从正在运行的容器中分离出来。</span><span class="sxs-lookup"><span data-stu-id="a6cad-198">In this example, the <kbd>CTRL + C</kbd> command is used to detach from the running container.</span></span> <span data-ttu-id="a6cad-199">这其实是结束容器中的进程，进而停止容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-199">This may actually end the process in the container, which will stop the container.</span></span> <span data-ttu-id="a6cad-200">`--sig-proxy=false` 参数可确保 <kbd>CTRL + C</kbd> 不会停止容器中的进程。</span><span class="sxs-lookup"><span data-stu-id="a6cad-200">The `--sig-proxy=false` parameter ensures that <kbd>CTRL + C</kbd> will not stop the process in the container.</span></span>

<span data-ttu-id="a6cad-201">从容器中分离出来后重新连接，以验证它是否仍在运行和计数。</span><span class="sxs-lookup"><span data-stu-id="a6cad-201">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

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

### <a name="delete-a-container"></a><span data-ttu-id="a6cad-202">删除容器</span><span class="sxs-lookup"><span data-stu-id="a6cad-202">Delete a container</span></span>

<span data-ttu-id="a6cad-203">就本文而言，你不希望存在不执行任何操作的容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-203">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="a6cad-204">删除前面创建的容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-204">Delete the container you previously created.</span></span> <span data-ttu-id="a6cad-205">如果容器正在运行，停止容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-205">If the container is running, stop it.</span></span>

```console
> docker stop boring_matsumoto
```

<span data-ttu-id="a6cad-206">下面的示例列出了所有容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-206">The following example lists all containers.</span></span> <span data-ttu-id="a6cad-207">然后，它使用 `docker rm` 命令来删除容器，并再次检查是否有任何正在运行的容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-207">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             boring_matsumoto

> docker rm boring_matsumoto
boring_matsumoto

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="a6cad-208">单次运行</span><span class="sxs-lookup"><span data-stu-id="a6cad-208">Single run</span></span>

<span data-ttu-id="a6cad-209">Docker 提供了 `docker run` 命令，用于将容器作为单一命令进行创建和运行。</span><span class="sxs-lookup"><span data-stu-id="a6cad-209">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="a6cad-210">使用此命令，无需依次运行 `docker create` 和 `docker start`。</span><span class="sxs-lookup"><span data-stu-id="a6cad-210">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="a6cad-211">另外，还可以将此命令设置为，在容器停止时自动删除容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-211">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="a6cad-212">例如，使用 `docker run -it --rm` 可以执行两项操作，先自动使用当前终端连接到容器，再在容器完成时删除容器：</span><span class="sxs-lookup"><span data-stu-id="a6cad-212">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="a6cad-213">使用 `docker run -it`，<kbd>CTRL + C</kbd> 命令会停止在容器中运行的进程，进而停止容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-213">With `docker run -it`, the <kbd>CTRL + C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="a6cad-214">由于提供了 `--rm` 参数，因此在进程停止时自动删除容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-214">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="a6cad-215">验证它是否不存在：</span><span class="sxs-lookup"><span data-stu-id="a6cad-215">Verify that it does not exist:</span></span>

```
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="a6cad-216">更改 ENTRYPOINT</span><span class="sxs-lookup"><span data-stu-id="a6cad-216">Change the ENTRYPOINT</span></span>

<span data-ttu-id="a6cad-217">使用 `docker run` 命令，还可以修改 Dockerfile 中的 `ENTRYPOINT` 命令，并运行其他内容，但只能针对相应容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-217">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="a6cad-218">例如，使用以下命令来运行 `bash` 或 `cmd.exe`。</span><span class="sxs-lookup"><span data-stu-id="a6cad-218">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="a6cad-219">根据需要，编辑此命令。</span><span class="sxs-lookup"><span data-stu-id="a6cad-219">Edit the command as necessary.</span></span>

#### <a name="windows"></a><span data-ttu-id="a6cad-220">Windows</span><span class="sxs-lookup"><span data-stu-id="a6cad-220">Windows</span></span>
<span data-ttu-id="a6cad-221">在此示例中，`ENTRYPOINT` 更改为 `cmd.exe`。</span><span class="sxs-lookup"><span data-stu-id="a6cad-221">In this example the `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="a6cad-222">通过按下 <kbd>CTRL + C</kbd> 来结束进程并停止容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-222"><kbd>CTRL + C</kbd> is pressed to end the process and stop the container.</span></span>

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

#### <a name="linux"></a><span data-ttu-id="a6cad-223">Linux</span><span class="sxs-lookup"><span data-stu-id="a6cad-223">Linux</span></span>

<span data-ttu-id="a6cad-224">在此示例中，`ENTRYPOINT` 更改为 `bash`。</span><span class="sxs-lookup"><span data-stu-id="a6cad-224">In this example the `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="a6cad-225">通过运行 `quit` 命令来结束进程并停止容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-225">The `quit` command is run which ends the process and stop the container.</span></span>

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a><span data-ttu-id="a6cad-226">重要命令</span><span class="sxs-lookup"><span data-stu-id="a6cad-226">Essential commands</span></span>

<span data-ttu-id="a6cad-227">Docker 有许多不同的命令，可用于执行你要对容器和映像执行的操作。</span><span class="sxs-lookup"><span data-stu-id="a6cad-227">Docker has many different commands that cover what you want to do with your container and images.</span></span> <span data-ttu-id="a6cad-228">下面这些 Docker 命令对于管理容器来说至关重要：</span><span class="sxs-lookup"><span data-stu-id="a6cad-228">These Docker commands are essential to managing your containers:</span></span>

* [<span data-ttu-id="a6cad-229">docker build</span><span class="sxs-lookup"><span data-stu-id="a6cad-229">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="a6cad-230">docker run</span><span class="sxs-lookup"><span data-stu-id="a6cad-230">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="a6cad-231">docker ps</span><span class="sxs-lookup"><span data-stu-id="a6cad-231">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="a6cad-232">docker stop</span><span class="sxs-lookup"><span data-stu-id="a6cad-232">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="a6cad-233">docker rm</span><span class="sxs-lookup"><span data-stu-id="a6cad-233">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="a6cad-234">docker rmi</span><span class="sxs-lookup"><span data-stu-id="a6cad-234">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="a6cad-235">docker image</span><span class="sxs-lookup"><span data-stu-id="a6cad-235">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="a6cad-236">清理资源</span><span class="sxs-lookup"><span data-stu-id="a6cad-236">Clean up resources</span></span>

<span data-ttu-id="a6cad-237">在本教程中，你创建了容器和映像。</span><span class="sxs-lookup"><span data-stu-id="a6cad-237">During this tutorial you created containers and images.</span></span> <span data-ttu-id="a6cad-238">如果需要，请删除这些资源。</span><span class="sxs-lookup"><span data-stu-id="a6cad-238">If you want, delete these resources.</span></span> <span data-ttu-id="a6cad-239">以下命令可用于</span><span class="sxs-lookup"><span data-stu-id="a6cad-239">Use the following commands to</span></span>

01. <span data-ttu-id="a6cad-240">列出所有容器</span><span class="sxs-lookup"><span data-stu-id="a6cad-240">List all containers</span></span>

    ```console
    > docker ps -a
    ```

02. <span data-ttu-id="a6cad-241">停止正在运行的容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-241">Stop containers that are running.</span></span> <span data-ttu-id="a6cad-242">`CONTAINER_NAME` 表示自动分配给容器的名称。</span><span class="sxs-lookup"><span data-stu-id="a6cad-242">The `CONTAINER_NAME` represents the name automatically assigned to the container.</span></span>

    ```console
    > docker stop CONTAINER_NAME
    ```

03. <span data-ttu-id="a6cad-243">删除容器</span><span class="sxs-lookup"><span data-stu-id="a6cad-243">Delete the container</span></span>

    ```console
    > docker rm CONTAINER_NAME
    ```

<span data-ttu-id="a6cad-244">接下来，删除计算机上不再需要的任何映像。</span><span class="sxs-lookup"><span data-stu-id="a6cad-244">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="a6cad-245">依次删除 Dockerfile 创建的映像，以及 Dockerfile 所依据的 .NET Core 映像。</span><span class="sxs-lookup"><span data-stu-id="a6cad-245">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="a6cad-246">可以使用 IMAGE ID 或 REPOSITORY:TAG 格式字符串。</span><span class="sxs-lookup"><span data-stu-id="a6cad-246">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/runtime:2.2
```

<span data-ttu-id="a6cad-247">使用 `docker images` 命令来列出已安装的映像。</span><span class="sxs-lookup"><span data-stu-id="a6cad-247">Use the `docker images` command to see a list of images installed.</span></span>

> [!NOTE]
> <span data-ttu-id="a6cad-248">映像文件可能很大。</span><span class="sxs-lookup"><span data-stu-id="a6cad-248">Image files can be large.</span></span> <span data-ttu-id="a6cad-249">通常情况下，需要删除在测试和开发应用期间创建的临时容器。</span><span class="sxs-lookup"><span data-stu-id="a6cad-249">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="a6cad-250">如果计划在相应运行时的基础之上生成其他映像，通常会将基础映像与运行时一同安装。</span><span class="sxs-lookup"><span data-stu-id="a6cad-250">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a6cad-251">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a6cad-251">Next steps</span></span>

* [<span data-ttu-id="a6cad-252">试学“ASP.NET Core 微服务”教程。</span><span class="sxs-lookup"><span data-stu-id="a6cad-252">Try the ASP.NET Core Microservice Tutorial.</span></span>](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
* [<span data-ttu-id="a6cad-253">查看支持容器的 Azure 服务。</span><span class="sxs-lookup"><span data-stu-id="a6cad-253">Review the Azure services that support containers.</span></span>](https://azure.microsoft.com/en-us/overview/containers/)
* [<span data-ttu-id="a6cad-254">了解 Dockerfile 命令。</span><span class="sxs-lookup"><span data-stu-id="a6cad-254">Read about Dockerfile commands.</span></span>](https://docs.docker.com/engine/reference/builder/)
* [<span data-ttu-id="a6cad-255">了解用于 Visual Studio 的容器工具</span><span class="sxs-lookup"><span data-stu-id="a6cad-255">Explore the Container Tools for Visual Studio</span></span>](/visualstudio/containers/overview)
