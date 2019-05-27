---
title: 通过 Docker 使应用程序容器化的教程
description: 在本教程中，你将了解如何使用 Docker 容器化 .NET Core 应用。
ms.date: 04/10/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 2ea9e9bc2614e62fe6ec0d59e39d42c2e32a80a1
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2019
ms.locfileid: "66051806"
---
# <a name="tutorial-containerize-a-net-core-app"></a>教程：使 .NET Core 应用程序容器化

本教程介绍如何生成包含 .NET Core 应用程序的 Docker 映像。 此映像可用于为本地开发环境、私有云或公有云创建容器。

你将了解如何：

> [!div class="checklist"]
> * 创建并发布简单的 .NET Core 应用
> * 创建并配置用于 .NET Core 的 Dockerfile
> * 生成 Docker 映像
> * 创建并运行 Docker 容器

你将了解用于 .NET Core 应用的 Docker 容器生成和部署任务。 Docker 平台使用 Docker 引擎快速生成应用，并将应用打包为 Docker 映像。 这些映像采用 Dockerfile 格式编写，以供在分层容器中部署和运行。

## <a name="prerequisites"></a>系统必备

安装以下必备组件：

- [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)\
如果已安装 .NET Core，请使用 `dotnet --info` 命令来确定使用的是哪个 SDK。

- [Docker 社区版](https://www.docker.com/products/docker-desktop)

- 用于 Dockerfile 和 .NET Core 示例应用的临时工作目录。

### <a name="use-sdk-version-22"></a>使用 SDK 版本 2.2

如果使用的是更高版本 SDK（如 3.0），请务必强制应用使用 SDK 2.2。 在工作目录中创建名为 `global.json` 的文件，并粘贴以下 json 代码：

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

保存此文件。 此文件会强制 .NET Core 对从这个目录及其下位置调用的任何 `dotnet` 命令使用版本 2.2。

## <a name="create-net-core-app"></a>创建 .Net Core 应用

需要有可供 Docker 容器运行的 .NET Core 应用。 打开终端，然后创建并进入工作目录。 在工作目录中，运行下面的命令，以在子目录“应用”中新建一个项目：

```console
dotnet new console -o app -n myapp
```

此命令新建目录“应用”，并生成“Hello World”应用。 可以通过测试此应用来看看它有何用途。 进入“应用”目录，并执行命令 `dotnet run`。 输出如下：

```console
> dotnet run
Hello World!
```

默认模板创建应用，此应用先打印输出到终端，再退出。 本教程将使用无限循环的应用。 在文本编辑器中，打开“Program.cs”文件。 它应如以下代码所示：

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

将此文件替换为以下每秒计数一次的代码：

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

保存此文件，并使用 `dotnet run` 再次测试程序。 请注意，此应用无限期运行。 使用取消命令 <kbd>CTRL + C</kbd> 可以停止运行。 输出如下：

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

如果你在命令行中向应用传递一个数字，它就只会计数到这个数字，然后退出。 试一试用 `dotnet run -- 5` 计数到 5。

> [!NOTE]
> `--` 后面的任何参数都传递到应用。

## <a name="publish-net-core-app"></a>发布 .Net Core 应用

请先发布 .NET Core 应用，再将它添加到 Docker 映像。 容器会执行启动后的应用的发布版本。

在工作目录中，进入包含示例源代码的“应用”目录，并运行以下命令：

```console
dotnet publish -c Release
```

此命令将应用编译到应用输出文件夹中的“发布”文件夹内。 工作目录中的“发布”文件夹的路径应为 `.\app\bin\Release\netcoreapp2.2\publish\`

获取“发布”文件夹的目录清单，以验证 myapp.dll 是否已创建。 在“应用”目录中，运行下列命令之一：

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

在终端中，转到上一级目录，即工作目录。

## <a name="create-the-dockerfile"></a>创建 Dockerfile

`docker build` 命令使用 Dockerfile 文件来创建容器映像。 此文件是名为“Dockerfile”的纯文本文件，它没有扩展名。 在工作目录中创建名为“Dockerfile”的文件，并在文本编辑器中打开它。 将以下命令添加为此文件的首行：

```dockerfile
FROM mcr.microsoft.com/dotnet/core/runtime:2.2
```

`FROM` 命令指示 Docker 从 mcr.microsoft.com/dotnet/core/runtime 存储库拉取标记为“2.2”的映像。 请确保拉取的 .NET Core 运行时与 SDK 定目标到的运行时一致。 例如，上一部分中创建的应用定目标到 .Net Core 2.2，且使用 .Net Core 2.2 SDK。 因此，Dockerfile 中引用的基础映像被标记为“2.2”。

保存该文件。 在终端中，运行 `docker build -t myimage .`，然后 Docker 会处理 Dockerfile 中的每一行。 `docker build` 命令中的 `.` 指示 Docker 在当前目录中查找 Dockerfile。 此命令生成映像，并创建指向相应映像的本地存储库“myimage”。 在此命令完成后，运行 `docker images` 以列出已安装的映像：

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
myimage                                 latest              d51bb4452469        2 days ago          314MB
```

请注意，两个映像共用相同的“IMAGE ID”值。 两个映像使用的 ID 值相同是因为，Dockerfile 中的唯一命令是在现有映像的基础之上生成新映像。 接下来，在 Dockerfile 中添加两个命令。 两个命令都新建映像层，最后一个命令表示 myimage 存储库将指向的映像。

```dockerfile
COPY app/bin/Release/netcoreapp2.2/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

`COPY` 命令指示 Docker 将计算机上的指定文件夹复制到容器中的文件夹。 在此示例中，“发布”文件夹被复制到容器中的“应用”文件夹。

下一个命令 `ENTRYPOINT` 指示 Docker 将容器配置为可执行文件运行。 在容器启动时，`ENTRYPOINT` 命令运行。 当此命令结束时，容器也会自动停止。

保存该文件。 在终端中，运行 `docker build -t myimage .`；在此命令完成后，运行 `docker images`。

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

Dockerfile 中的每个命令生成了一个层，并创建了“IMAGE ID”。 最终“IMAGE ID”是“ddcc6646461b”（你的 ID 会有所不同），接下来在此映像的基础之上创建容器。

## <a name="create-a-container"></a>创建容器

至此，已有包含应用的映像，可以创建容器了。 可以通过两种方式来创建容器。 首先，新建已停止的容器。

```console
> docker create myimage
0e8f3c2ca32ce773712a5cca38750f41259a4e54e04bdf0946087e230ad7066c
```

上面的 `docker create` 命令在 myimage 映像的基础之上创建容器。 此命令的输出显示已创建容器的“CONTAINER ID”（你的 ID 会有所不同）。 若要查看所有容器的列表，请使用 `docker ps -a` 命令：

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               boring_matsumoto
```

### <a name="manage-the-container"></a>管理容器

每个容器都分配有随机名称，可用来引用相应容器实例。 例如，自动创建的容器选择了名称“boring_matsumoto”（你的名称会有所不同），此名称可用于启动容器。 可以使用 `docker create --name` 参数将自动名称替代为特定名称。

下面的示例使用 `docker start` 命令来启动容器，然后使用 `docker ps` 命令仅显示正在运行的容器：

```console
> docker start boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           boring_matsumoto
```

同样，`docker stop` 命令会停止容器。 下面的示例使用 `docker stop` 命令来停止容器，然后使用 `docker ps` 命令来显示没有正在运行的容器。

```console
> docker stop boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a>连接到容器

在容器运行后，可以连接到它来查看输出。 使用 `docker start` 和 `docker attach` 命令，启动容器并查看输出流。 在此示例中，<kbd>CTRL + C</kbd> 命令用于从正在运行的容器中分离出来。 这其实是结束容器中的进程，进而停止容器。 `--sig-proxy=false` 参数可确保 <kbd>CTRL + C</kbd> 不会停止容器中的进程。

从容器中分离出来后重新连接，以验证它是否仍在运行和计数。

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

### <a name="delete-a-container"></a>删除容器

就本文而言，你不希望存在不执行任何操作的容器。 删除前面创建的容器。 如果容器正在运行，停止容器。

```console
> docker stop boring_matsumoto
```

下面的示例列出了所有容器。 然后，它使用 `docker rm` 命令来删除容器，并再次检查是否有任何正在运行的容器。

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             boring_matsumoto

> docker rm boring_matsumoto
boring_matsumoto

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a>单次运行

Docker 提供了 `docker run` 命令，用于将容器作为单一命令进行创建和运行。 使用此命令，无需依次运行 `docker create` 和 `docker start`。 另外，还可以将此命令设置为，在容器停止时自动删除容器。 例如，使用 `docker run -it --rm` 可以执行两项操作，先自动使用当前终端连接到容器，再在容器完成时删除容器：

```
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

使用 `docker run -it`，<kbd>CTRL + C</kbd> 命令会停止在容器中运行的进程，进而停止容器。 由于提供了 `--rm` 参数，因此在进程停止时自动删除容器。 验证它是否不存在：

```
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a>更改 ENTRYPOINT

使用 `docker run` 命令，还可以修改 Dockerfile 中的 `ENTRYPOINT` 命令，并运行其他内容，但只能针对相应容器。 例如，使用以下命令来运行 `bash` 或 `cmd.exe`。 根据需要，编辑此命令。

#### <a name="windows"></a>Windows
在此示例中，`ENTRYPOINT` 更改为 `cmd.exe`。 通过按下 <kbd>CTRL + C</kbd> 来结束进程并停止容器。

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

#### <a name="linux"></a>Linux

在此示例中，`ENTRYPOINT` 更改为 `bash`。 通过运行 `quit` 命令来结束进程并停止容器。

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a>重要命令

Docker 有许多不同的命令，可用于执行你要对容器和映像执行的操作。 下面这些 Docker 命令对于管理容器来说至关重要：

* [docker build](https://docs.docker.com/engine/reference/commandline/build/)
* [docker run](https://docs.docker.com/engine/reference/commandline/run/)
* [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
* [docker stop](https://docs.docker.com/engine/reference/commandline/stop/)
* [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
* [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
* [docker image](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a>清理资源

在本教程中，你创建了容器和映像。 如果需要，请删除这些资源。 以下命令可用于

01. 列出所有容器

    ```console
    > docker ps -a
    ```

02. 停止正在运行的容器。 `CONTAINER_NAME` 表示自动分配给容器的名称。

    ```console
    > docker stop CONTAINER_NAME
    ```

03. 删除容器

    ```console
    > docker rm CONTAINER_NAME
    ```

接下来，删除计算机上不再需要的任何映像。 依次删除 Dockerfile 创建的映像，以及 Dockerfile 所依据的 .NET Core 映像。 可以使用 IMAGE ID 或 REPOSITORY:TAG 格式字符串。

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/runtime:2.2
```

使用 `docker images` 命令来列出已安装的映像。

> [!NOTE]
> 映像文件可能很大。 通常情况下，需要删除在测试和开发应用期间创建的临时容器。 如果计划在相应运行时的基础之上生成其他映像，通常会将基础映像与运行时一同安装。

## <a name="next-steps"></a>后续步骤

* [试学“ASP.NET Core 微服务”教程。](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
* [查看支持容器的 Azure 服务。](https://azure.microsoft.com/overview/containers/)
* [了解 Dockerfile 命令。](https://docs.docker.com/engine/reference/builder/)
* [了解用于 Visual Studio 的容器工具](/visualstudio/containers/overview)
