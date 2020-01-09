---
title: 适用于 WCF 开发人员的 Docker gRPC
description: 为 ASP.NET Core gRPC 应用程序创建 Docker 映像
ms.date: 09/02/2019
ms.openlocfilehash: d23dc46526183b459c36f11bae4def8b1c9b9410
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711299"
---
# <a name="create-docker-images"></a><span data-ttu-id="19d5f-103">创建 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="19d5f-103">Create Docker images</span></span>

<span data-ttu-id="19d5f-104">本部分介绍如何创建用于 ASP.NET Core gRPC 应用程序的 Docker 映像，并准备在 Docker、Kubernetes 或其他容器环境中运行。</span><span class="sxs-lookup"><span data-stu-id="19d5f-104">This section covers the creation of Docker images for ASP.NET Core gRPC applications, ready to run in Docker, Kubernetes, or other container environments.</span></span> <span data-ttu-id="19d5f-105">在 GitHub 上的[dotnet/gRPC/](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample)存储库中提供了使用的示例应用程序，其中包含 ASP.NET Core MVC web 应用和 gRPC 服务。</span><span class="sxs-lookup"><span data-stu-id="19d5f-105">The sample application used, with an ASP.NET Core MVC web app and a gRPC service, is available on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="microsoft-base-images-for-aspnet-core-applications"></a><span data-ttu-id="19d5f-106">用于 ASP.NET Core 应用程序的 Microsoft 基础映像</span><span class="sxs-lookup"><span data-stu-id="19d5f-106">Microsoft base images for ASP.NET Core applications</span></span>

<span data-ttu-id="19d5f-107">Microsoft 提供了一系列用于构建和运行 .NET Core 应用程序的基本映像。</span><span class="sxs-lookup"><span data-stu-id="19d5f-107">Microsoft provides a range of base images for building and running .NET Core applications.</span></span> <span data-ttu-id="19d5f-108">若要创建 ASP.NET Core 3.0 映像，请使用两个基本映像：</span><span class="sxs-lookup"><span data-stu-id="19d5f-108">To create an ASP.NET Core 3.0 image, you use two base images:</span></span> 

- <span data-ttu-id="19d5f-109">用于生成和发布应用程序的 SDK 映像。</span><span class="sxs-lookup"><span data-stu-id="19d5f-109">An SDK image to build and publish the application.</span></span>
- <span data-ttu-id="19d5f-110">用于部署的运行时映像。</span><span class="sxs-lookup"><span data-stu-id="19d5f-110">A runtime image for deployment.</span></span>

| <span data-ttu-id="19d5f-111">Image</span><span class="sxs-lookup"><span data-stu-id="19d5f-111">Image</span></span> | <span data-ttu-id="19d5f-112">描述</span><span class="sxs-lookup"><span data-stu-id="19d5f-112">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="19d5f-113">mcr.microsoft.com/dotnet/core/sdk</span><span class="sxs-lookup"><span data-stu-id="19d5f-113">mcr.microsoft.com/dotnet/core/sdk</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | <span data-ttu-id="19d5f-114">用于生成具有 `docker build`的应用程序。</span><span class="sxs-lookup"><span data-stu-id="19d5f-114">For building applications with `docker build`.</span></span> <span data-ttu-id="19d5f-115">不能在生产中使用。</span><span class="sxs-lookup"><span data-stu-id="19d5f-115">Not to be used in production.</span></span> |
| [<span data-ttu-id="19d5f-116">mcr.microsoft.com/dotnet/core/aspnet</span><span class="sxs-lookup"><span data-stu-id="19d5f-116">mcr.microsoft.com/dotnet/core/aspnet</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | <span data-ttu-id="19d5f-117">包含运行时和 ASP.NET Core 依赖项。</span><span class="sxs-lookup"><span data-stu-id="19d5f-117">Contains the runtime and ASP.NET Core dependencies.</span></span> <span data-ttu-id="19d5f-118">用于生产。</span><span class="sxs-lookup"><span data-stu-id="19d5f-118">For production.</span></span> |

<span data-ttu-id="19d5f-119">对于每个映像，都有四个基于不同 Linux 分发的变量，由标记来区分。</span><span class="sxs-lookup"><span data-stu-id="19d5f-119">For each image, there are four variants based on different Linux distributions, distinguished by tags.</span></span>

| <span data-ttu-id="19d5f-120">图像标记</span><span class="sxs-lookup"><span data-stu-id="19d5f-120">Image tag(s)</span></span> | <span data-ttu-id="19d5f-121">Linux</span><span class="sxs-lookup"><span data-stu-id="19d5f-121">Linux</span></span> | <span data-ttu-id="19d5f-122">注释</span><span class="sxs-lookup"><span data-stu-id="19d5f-122">Notes</span></span> |
| --------- | ----- | ----- |
| <span data-ttu-id="19d5f-123">3.0-buster、3.0</span><span class="sxs-lookup"><span data-stu-id="19d5f-123">3.0-buster, 3.0</span></span> | <span data-ttu-id="19d5f-124">Debian 10</span><span class="sxs-lookup"><span data-stu-id="19d5f-124">Debian 10</span></span> | <span data-ttu-id="19d5f-125">如果未指定操作系统变体，则为默认映像。</span><span class="sxs-lookup"><span data-stu-id="19d5f-125">The default image if no OS variant is specified.</span></span> |
| <span data-ttu-id="19d5f-126">3.0-alpine</span><span class="sxs-lookup"><span data-stu-id="19d5f-126">3.0-alpine</span></span> | <span data-ttu-id="19d5f-127">Alpine 3。9</span><span class="sxs-lookup"><span data-stu-id="19d5f-127">Alpine 3.9</span></span> | <span data-ttu-id="19d5f-128">Alpine 基本映像比 Debian 或 Ubuntu 映像小得多。</span><span class="sxs-lookup"><span data-stu-id="19d5f-128">Alpine base images are much smaller than Debian or Ubuntu ones.</span></span> |
| <span data-ttu-id="19d5f-129">3.0-disco</span><span class="sxs-lookup"><span data-stu-id="19d5f-129">3.0-disco</span></span> | <span data-ttu-id="19d5f-130">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="19d5f-130">Ubuntu 19.04</span></span> | |
| <span data-ttu-id="19d5f-131">3.0-bionic</span><span class="sxs-lookup"><span data-stu-id="19d5f-131">3.0-bionic</span></span> | <span data-ttu-id="19d5f-132">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="19d5f-132">Ubuntu 18.04</span></span> | |

<span data-ttu-id="19d5f-133">对于 Debian 和 Ubuntu 映像，Alpine 基本映像约 100 MB，比较 200 MB。</span><span class="sxs-lookup"><span data-stu-id="19d5f-133">The Alpine base image is around 100 MB, compared to 200 MB for the Debian and Ubuntu images.</span></span> <span data-ttu-id="19d5f-134">某些软件包或库可能在 Alpine 的包管理中不可用。</span><span class="sxs-lookup"><span data-stu-id="19d5f-134">Some software packages or libraries might not be available in Alpine's package management.</span></span> <span data-ttu-id="19d5f-135">如果你不确定要使用哪个映像，则应选择默认 Debian。</span><span class="sxs-lookup"><span data-stu-id="19d5f-135">If you're not sure which image to use, you should probably choose the default Debian.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19d5f-136">请确保为生成和运行时使用相同的 Linux 变体。</span><span class="sxs-lookup"><span data-stu-id="19d5f-136">Make sure you use the same variant of Linux for the build and the runtime.</span></span> <span data-ttu-id="19d5f-137">在一个变体上构建和发布的应用程序可能无法在另一个上运行。</span><span class="sxs-lookup"><span data-stu-id="19d5f-137">Applications built and published on one variant might not work on another.</span></span>

## <a name="create-a-docker-image"></a><span data-ttu-id="19d5f-138">创建 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="19d5f-138">Create a Docker image</span></span>

<span data-ttu-id="19d5f-139">Docker 映像由*Dockerfile*定义。</span><span class="sxs-lookup"><span data-stu-id="19d5f-139">A Docker image is defined by a *Dockerfile*.</span></span> <span data-ttu-id="19d5f-140">这是一个文本文件，其中包含生成应用程序所需的所有命令，并安装生成或运行该应用程序所需的任何依赖项。</span><span class="sxs-lookup"><span data-stu-id="19d5f-140">This is a text file that contains all the commands needed to build the application and install any dependencies that are required for either building or running the application.</span></span> <span data-ttu-id="19d5f-141">下面的示例演示 ASP.NET Core 3.0 应用程序的最简单的 Dockerfile：</span><span class="sxs-lookup"><span data-stu-id="19d5f-141">The following example shows the simplest Dockerfile for an ASP.NET Core 3.0 application:</span></span>

```dockerfile
# Application build steps
FROM mcr.microsoft.com/dotnet/core/sdk:3.0 as builder

WORKDIR /src

COPY . .

RUN dotnet restore

RUN dotnet publish -c Release -o /published src/StockData/StockData.csproj

# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=builder /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

<span data-ttu-id="19d5f-142">Dockerfile 有两部分：第一个使用 `sdk` 基本映像来生成和发布应用程序;第二个基于 `aspnet` 创建运行时映像。</span><span class="sxs-lookup"><span data-stu-id="19d5f-142">The Dockerfile has two parts: the first uses the `sdk` base image to build and publish the application; the second creates a runtime image from the `aspnet` base.</span></span> <span data-ttu-id="19d5f-143">这是因为，在运行时，`sdk` 图像大约为 900 MB，对于运行时映像约 200 MB，其中的大部分内容是不必要的。</span><span class="sxs-lookup"><span data-stu-id="19d5f-143">This is because the `sdk` image is around 900 MB, compared to around 200 MB for the runtime image, and most of its contents are unnecessary at runtime.</span></span>

### <a name="the-build-steps"></a><span data-ttu-id="19d5f-144">生成步骤</span><span class="sxs-lookup"><span data-stu-id="19d5f-144">The build steps</span></span>

| <span data-ttu-id="19d5f-145">步骤</span><span class="sxs-lookup"><span data-stu-id="19d5f-145">Step</span></span> | <span data-ttu-id="19d5f-146">描述</span><span class="sxs-lookup"><span data-stu-id="19d5f-146">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="19d5f-147">声明基映像并分配 `builder` 别名。</span><span class="sxs-lookup"><span data-stu-id="19d5f-147">Declares the base image and assigns the `builder` alias.</span></span> |
| `WORKDIR /src` | <span data-ttu-id="19d5f-148">创建 `/src` 目录，并将其设置为当前工作目录。</span><span class="sxs-lookup"><span data-stu-id="19d5f-148">Creates the `/src` directory and sets it as the current working directory.</span></span> |
| `COPY . .` | <span data-ttu-id="19d5f-149">将主机上当前目录下的所有内容复制到映像上的当前目录。</span><span class="sxs-lookup"><span data-stu-id="19d5f-149">Copies everything below the current directory on the host into the current directory on the image.</span></span> |
| `RUN dotnet restore` | <span data-ttu-id="19d5f-150">还原任何外部包（ASP.NET Core 3.0 framework 已与 SDK 一起预安装）。</span><span class="sxs-lookup"><span data-stu-id="19d5f-150">Restores any external packages (ASP.NET Core 3.0 framework is pre-installed with the SDK).</span></span> |
| `RUN dotnet publish ...` | <span data-ttu-id="19d5f-151">生成并发布发布版本。</span><span class="sxs-lookup"><span data-stu-id="19d5f-151">Builds and publishes a Release build.</span></span> <span data-ttu-id="19d5f-152">请注意，不需要 `--runtime` 标志。</span><span class="sxs-lookup"><span data-stu-id="19d5f-152">Note that the `--runtime` flag isn't required.</span></span> |

### <a name="the-runtime-image-steps"></a><span data-ttu-id="19d5f-153">运行时映像步骤</span><span class="sxs-lookup"><span data-stu-id="19d5f-153">The runtime image steps</span></span>

| <span data-ttu-id="19d5f-154">步骤</span><span class="sxs-lookup"><span data-stu-id="19d5f-154">Step</span></span> | <span data-ttu-id="19d5f-155">描述</span><span class="sxs-lookup"><span data-stu-id="19d5f-155">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="19d5f-156">声明新的基本映像。</span><span class="sxs-lookup"><span data-stu-id="19d5f-156">Declares a new base image.</span></span> |
| `WORKDIR /app` | <span data-ttu-id="19d5f-157">创建 `/app` 目录，并将其设置为当前工作目录。</span><span class="sxs-lookup"><span data-stu-id="19d5f-157">Creates the `/app` directory and sets it as the current working directory.</span></span> |
| `COPY --from=builder ...` | <span data-ttu-id="19d5f-158">使用第一 `FROM` 行中的 `builder` 别名从上一个映像复制已发布的应用程序。</span><span class="sxs-lookup"><span data-stu-id="19d5f-158">Copies the published application from the previous image, by using the `builder` alias from the first `FROM` line.</span></span> |
| `ENTRYPOINT [ ... ]` | <span data-ttu-id="19d5f-159">设置要在容器启动时运行的命令。</span><span class="sxs-lookup"><span data-stu-id="19d5f-159">Sets the command to run when the container starts.</span></span> <span data-ttu-id="19d5f-160">运行时映像中的 `dotnet` 命令只能运行 DLL 文件。</span><span class="sxs-lookup"><span data-stu-id="19d5f-160">The `dotnet` command in the runtime image can only run DLL files.</span></span> |

### <a name="https-in-docker"></a><span data-ttu-id="19d5f-161">Docker 中的 HTTPS</span><span class="sxs-lookup"><span data-stu-id="19d5f-161">HTTPS in Docker</span></span>

<span data-ttu-id="19d5f-162">用于 Docker 的 Microsoft 基本映像将 `ASPNETCORE_URLS` 环境变量设置为 `http://+:80`，这意味着 Kestrel 在该端口上运行而不运行 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="19d5f-162">Microsoft base images for Docker set the `ASPNETCORE_URLS` environment variable to `http://+:80`, meaning that Kestrel runs without HTTPS on that port.</span></span> <span data-ttu-id="19d5f-163">如果对自定义证书使用 HTTPS （如[自承载 gRPC 应用程序](self-hosted.md)中所述），则应覆盖此项。</span><span class="sxs-lookup"><span data-stu-id="19d5f-163">If you're using HTTPS with a custom certificate (as described in [Self-hosted gRPC applications](self-hosted.md)), you should override this.</span></span> <span data-ttu-id="19d5f-164">在 Dockerfile 的运行时映像创建部分设置环境变量。</span><span class="sxs-lookup"><span data-stu-id="19d5f-164">Set the environment variable in the runtime image creation part of your Dockerfile.</span></span>

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a><span data-ttu-id="19d5f-165">.Dockerignore 文件</span><span class="sxs-lookup"><span data-stu-id="19d5f-165">The .dockerignore file</span></span>

<span data-ttu-id="19d5f-166">与从源代码管理中排除某些文件和目录 `.gitignore` 文件非常相似，`.dockerignore` 文件可用于在生成过程中排除文件和目录被复制到映像。</span><span class="sxs-lookup"><span data-stu-id="19d5f-166">Much like `.gitignore` files that exclude certain files and directories from source control, the `.dockerignore` file can be used to exclude files and directories from being copied to the image during build.</span></span> <span data-ttu-id="19d5f-167">这不仅会节省时间复制，还可以避免在将 `obj` 目录从 PC 复制到映像时出现的一些错误。</span><span class="sxs-lookup"><span data-stu-id="19d5f-167">This not only saves time copying, but can also avoid some errors that arise from having the `obj` directory from your PC copied into the image.</span></span> <span data-ttu-id="19d5f-168">至少应将 `bin` 和 `obj` 条目添加到 `.dockerignore` 文件中。</span><span class="sxs-lookup"><span data-stu-id="19d5f-168">At a minimum, you should add entries for `bin` and `obj` to your `.dockerignore` file.</span></span>

```console
bin/
obj/
```

## <a name="build-the-image"></a><span data-ttu-id="19d5f-169">生成映像</span><span class="sxs-lookup"><span data-stu-id="19d5f-169">Build the image</span></span>

<span data-ttu-id="19d5f-170">对于具有单个应用程序的解决方案，因此，如果是单个 Dockerfile，则最简单的方法是将 Dockerfile 放在基目录中。</span><span class="sxs-lookup"><span data-stu-id="19d5f-170">For a solution with a single application, and thus a single Dockerfile, it's simplest to put the Dockerfile in the base directory.</span></span> <span data-ttu-id="19d5f-171">换句话说，将其放在与 `.sln` 文件相同的目录中。</span><span class="sxs-lookup"><span data-stu-id="19d5f-171">In other words, put it in the same directory as the `.sln` file.</span></span> <span data-ttu-id="19d5f-172">在这种情况下，若要生成映像，请在包含 Dockerfile 的目录中使用以下 `docker build` 命令。</span><span class="sxs-lookup"><span data-stu-id="19d5f-172">In that case, to build the image, use the following `docker build` command from the directory containing the Dockerfile.</span></span>

```console
docker build --tag stockdata .
```

<span data-ttu-id="19d5f-173">名为 `--tag` 标志的令困惑（可将其缩短为 `-t`）指定图像的整个名称，包括实际标记（如果指定）。</span><span class="sxs-lookup"><span data-stu-id="19d5f-173">The confusingly named `--tag` flag (which can be shortened to `-t`) specifies the whole name of the image, including the actual tag if specified.</span></span> <span data-ttu-id="19d5f-174">末尾处的 `.` 指定将在其中运行生成的上下文;Dockerfile 中 `COPY` 命令的当前工作目录。</span><span class="sxs-lookup"><span data-stu-id="19d5f-174">The `.` at the end specifies the context in which the build will be run; the current working directory for the `COPY` commands in the Dockerfile.</span></span>

<span data-ttu-id="19d5f-175">如果一个解决方案中有多个应用程序，则可以将每个应用程序的 Dockerfile 保存在其自己的文件夹中的 `.csproj` 文件旁边。</span><span class="sxs-lookup"><span data-stu-id="19d5f-175">If you have multiple applications within a single solution, you can keep the Dockerfile for each application in its own folder, beside the `.csproj` file.</span></span> <span data-ttu-id="19d5f-176">你仍应该从基本目录运行 `docker build` 命令，以确保将解决方案和所有项目都复制到映像中。</span><span class="sxs-lookup"><span data-stu-id="19d5f-176">You should still run the `docker build` command from the base directory to ensure that the solution and all the projects are copied into the image.</span></span> <span data-ttu-id="19d5f-177">您可以使用 `--file` （或 `-f`）标志在当前目录下指定 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="19d5f-177">You can specify a Dockerfile below the current directory by using the `--file` (or `-f`) flag.</span></span>

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a><span data-ttu-id="19d5f-178">在计算机上的容器中运行映像</span><span class="sxs-lookup"><span data-stu-id="19d5f-178">Run the image in a container on your machine</span></span>

<span data-ttu-id="19d5f-179">若要在本地 Docker 实例中运行映像，请使用 `docker run` 命令。</span><span class="sxs-lookup"><span data-stu-id="19d5f-179">To run the image in your local Docker instance, use the `docker run` command.</span></span>

```console
docker run -ti -p 5000:80 stockdata
```

<span data-ttu-id="19d5f-180">`-ti` 标志将当前终端连接到容器的终端，并在交互模式下运行。</span><span class="sxs-lookup"><span data-stu-id="19d5f-180">The `-ti` flag connects your current terminal to the container's terminal, and runs in interactive mode.</span></span> <span data-ttu-id="19d5f-181">`-p 5000:80` 将容器上的端口80发布（链接）到 localhost 网络接口上的端口80。</span><span class="sxs-lookup"><span data-stu-id="19d5f-181">The `-p 5000:80` publishes (links) port 80 on the container to port 80 on the localhost network interface.</span></span>

## <a name="push-the-image-to-a-registry"></a><span data-ttu-id="19d5f-182">将映像推送到注册表</span><span class="sxs-lookup"><span data-stu-id="19d5f-182">Push the image to a registry</span></span>

<span data-ttu-id="19d5f-183">验证映像工作后，将其推送到 Docker 注册表，使其在其他系统上可用。</span><span class="sxs-lookup"><span data-stu-id="19d5f-183">After you've verified that the image works, push it to a Docker registry to make it available on other systems.</span></span> <span data-ttu-id="19d5f-184">内部网络将需要预配 Docker 注册表。</span><span class="sxs-lookup"><span data-stu-id="19d5f-184">Internal networks will need to provision a Docker registry.</span></span> <span data-ttu-id="19d5f-185">这可以像运行[docker 自己的 `registry` 映像](https://docs.docker.com/registry/deploying/)一样简单（docker 注册表在 docker 容器中运行），但有多个更全面的解决方案可用。</span><span class="sxs-lookup"><span data-stu-id="19d5f-185">This can be as simple as running [Docker's own `registry` image](https://docs.docker.com/registry/deploying/) (the Docker registry runs in a Docker container), but there are various more comprehensive solutions available.</span></span> <span data-ttu-id="19d5f-186">对于外部共享和云使用，有多种可用的托管注册表，如[Azure 容器注册表](https://docs.microsoft.com/azure/container-registry/)或[Docker Hub](https://docs.docker.com/docker-hub/repos/)。</span><span class="sxs-lookup"><span data-stu-id="19d5f-186">For external sharing and cloud use, there are various managed registries available, such as [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) or [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span></span>

<span data-ttu-id="19d5f-187">若要推送到 Docker Hub，请将映像名称作为你的用户或组织名称作为前缀。</span><span class="sxs-lookup"><span data-stu-id="19d5f-187">To push to Docker Hub, prefix the image name with your user or organization name.</span></span>

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

<span data-ttu-id="19d5f-188">若要推送到专用注册表，请使用注册表主机名和组织名称作为映像名称的前缀。</span><span class="sxs-lookup"><span data-stu-id="19d5f-188">To push to a private registry, prefix the image name with the registry host name and the organization name.</span></span>

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

<span data-ttu-id="19d5f-189">映像位于注册表中后，可以将其部署到各个 Docker 主机或容器业务流程引擎（如 Kubernetes）。</span><span class="sxs-lookup"><span data-stu-id="19d5f-189">After the image is in a registry, you can deploy it to individual Docker hosts, or to a container orchestration engine like Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="19d5f-190">[上一页](self-hosted.md)
>[下一页](kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="19d5f-190">[Previous](self-hosted.md)
[Next](kubernetes.md)</span></span>
