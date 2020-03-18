---
title: 为 WCF 开发人员提供 Docker - gRPC
description: 为ASP.NET核心 gRPC 应用程序创建 Docker 映像
ms.date: 09/02/2019
ms.openlocfilehash: e67c43f9486fbfe9a5d3e84e3b74770eb621f604
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148109"
---
# <a name="create-docker-images"></a><span data-ttu-id="d0229-103">创建 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="d0229-103">Create Docker images</span></span>

<span data-ttu-id="d0229-104">本节介绍为ASP.NET Core gRPC 应用程序创建 Docker 映像，这些应用程序可在 Docker、Kubernetes 或其他容器环境中运行。</span><span class="sxs-lookup"><span data-stu-id="d0229-104">This section covers the creation of Docker images for ASP.NET Core gRPC applications, ready to run in Docker, Kubernetes, or other container environments.</span></span> <span data-ttu-id="d0229-105">使用的示例应用程序，带有ASP.NET酷睿 MVC Web 应用和 gRPC 服务，可在 GitHub 上的[dotnet 架构/grpc-for wcf 开发人员](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample)存储库中使用。</span><span class="sxs-lookup"><span data-stu-id="d0229-105">The sample application used, with an ASP.NET Core MVC web app and a gRPC service, is available on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="microsoft-base-images-for-aspnet-core-applications"></a><span data-ttu-id="d0229-106">用于ASP.NET核心应用程序的微软基本映像</span><span class="sxs-lookup"><span data-stu-id="d0229-106">Microsoft base images for ASP.NET Core applications</span></span>

<span data-ttu-id="d0229-107">Microsoft 为构建和运行 .NET Core 应用程序提供了一系列基本映像。</span><span class="sxs-lookup"><span data-stu-id="d0229-107">Microsoft provides a range of base images for building and running .NET Core applications.</span></span> <span data-ttu-id="d0229-108">要创建 ASP.NET酷睿 3.0 图像，请使用两个基本映像：</span><span class="sxs-lookup"><span data-stu-id="d0229-108">To create an ASP.NET Core 3.0 image, you use two base images:</span></span>

- <span data-ttu-id="d0229-109">用于生成和发布应用程序的 SDK 映像。</span><span class="sxs-lookup"><span data-stu-id="d0229-109">An SDK image to build and publish the application.</span></span>
- <span data-ttu-id="d0229-110">用于部署的运行时映像。</span><span class="sxs-lookup"><span data-stu-id="d0229-110">A runtime image for deployment.</span></span>

| <span data-ttu-id="d0229-111">映像</span><span class="sxs-lookup"><span data-stu-id="d0229-111">Image</span></span> | <span data-ttu-id="d0229-112">说明</span><span class="sxs-lookup"><span data-stu-id="d0229-112">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="d0229-113">mcr.microsoft.com/dotnet/core/sdk</span><span class="sxs-lookup"><span data-stu-id="d0229-113">mcr.microsoft.com/dotnet/core/sdk</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | <span data-ttu-id="d0229-114">用于使用`docker build`生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="d0229-114">For building applications with `docker build`.</span></span> <span data-ttu-id="d0229-115">不用于生产。</span><span class="sxs-lookup"><span data-stu-id="d0229-115">Not to be used in production.</span></span> |
| [<span data-ttu-id="d0229-116">mcr.microsoft.com/dotnet/core/aspnet</span><span class="sxs-lookup"><span data-stu-id="d0229-116">mcr.microsoft.com/dotnet/core/aspnet</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | <span data-ttu-id="d0229-117">包含运行时和 ASP.NET核心依赖项。</span><span class="sxs-lookup"><span data-stu-id="d0229-117">Contains the runtime and ASP.NET Core dependencies.</span></span> <span data-ttu-id="d0229-118">用于生产。</span><span class="sxs-lookup"><span data-stu-id="d0229-118">For production.</span></span> |

<span data-ttu-id="d0229-119">对于每个映像，有四种基于不同 Linux 发行版的变体，按标记区分。</span><span class="sxs-lookup"><span data-stu-id="d0229-119">For each image, there are four variants based on different Linux distributions, distinguished by tags.</span></span>

| <span data-ttu-id="d0229-120">图像标记</span><span class="sxs-lookup"><span data-stu-id="d0229-120">Image tag(s)</span></span> | <span data-ttu-id="d0229-121">Linux</span><span class="sxs-lookup"><span data-stu-id="d0229-121">Linux</span></span> | <span data-ttu-id="d0229-122">说明</span><span class="sxs-lookup"><span data-stu-id="d0229-122">Notes</span></span> |
| --------- | ----- | ----- |
| <span data-ttu-id="d0229-123">3.0-破坏者，3.0</span><span class="sxs-lookup"><span data-stu-id="d0229-123">3.0-buster, 3.0</span></span> | <span data-ttu-id="d0229-124">Debian 10</span><span class="sxs-lookup"><span data-stu-id="d0229-124">Debian 10</span></span> | <span data-ttu-id="d0229-125">如果未指定操作系统变体，则默认映像。</span><span class="sxs-lookup"><span data-stu-id="d0229-125">The default image if no OS variant is specified.</span></span> |
| <span data-ttu-id="d0229-126">3.0-高山</span><span class="sxs-lookup"><span data-stu-id="d0229-126">3.0-alpine</span></span> | <span data-ttu-id="d0229-127">阿尔卑斯 3.9</span><span class="sxs-lookup"><span data-stu-id="d0229-127">Alpine 3.9</span></span> | <span data-ttu-id="d0229-128">阿尔卑斯基图图像比Debian或Ubuntu图像小得多。</span><span class="sxs-lookup"><span data-stu-id="d0229-128">Alpine base images are much smaller than Debian or Ubuntu ones.</span></span> |
| <span data-ttu-id="d0229-129">3.0-迪斯科</span><span class="sxs-lookup"><span data-stu-id="d0229-129">3.0-disco</span></span> | <span data-ttu-id="d0229-130">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="d0229-130">Ubuntu 19.04</span></span> | |
| <span data-ttu-id="d0229-131">3.0-仿生</span><span class="sxs-lookup"><span data-stu-id="d0229-131">3.0-bionic</span></span> | <span data-ttu-id="d0229-132">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="d0229-132">Ubuntu 18.04</span></span> | |

<span data-ttu-id="d0229-133">阿尔卑斯基图约为 100 MB，而 Debian 和 Ubuntu 图像的映像为 200 MB。</span><span class="sxs-lookup"><span data-stu-id="d0229-133">The Alpine base image is around 100 MB, compared to 200 MB for the Debian and Ubuntu images.</span></span> <span data-ttu-id="d0229-134">某些软件包或库在 Alpine 的软件包管理中可能不可用。</span><span class="sxs-lookup"><span data-stu-id="d0229-134">Some software packages or libraries might not be available in Alpine's package management.</span></span> <span data-ttu-id="d0229-135">如果您不确定要使用的图像，则可能需要选择默认的 Debian。</span><span class="sxs-lookup"><span data-stu-id="d0229-135">If you're not sure which image to use, you should probably choose the default Debian.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0229-136">请确保在生成和运行时使用相同的 Linux 变体。</span><span class="sxs-lookup"><span data-stu-id="d0229-136">Make sure you use the same variant of Linux for the build and the runtime.</span></span> <span data-ttu-id="d0229-137">在一个变体上构建和发布的应用程序可能不适用于另一个变体。</span><span class="sxs-lookup"><span data-stu-id="d0229-137">Applications built and published on one variant might not work on another.</span></span>

## <a name="create-a-docker-image"></a><span data-ttu-id="d0229-138">创建 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="d0229-138">Create a Docker image</span></span>

<span data-ttu-id="d0229-139">Docker 映像由 Docker*文件*定义。</span><span class="sxs-lookup"><span data-stu-id="d0229-139">A Docker image is defined by a *Dockerfile*.</span></span> <span data-ttu-id="d0229-140">这是一个文本文件，其中包含生成应用程序和安装生成或运行应用程序所需的任何依赖项所需的所有命令。</span><span class="sxs-lookup"><span data-stu-id="d0229-140">This is a text file that contains all the commands needed to build the application and install any dependencies that are required for either building or running the application.</span></span> <span data-ttu-id="d0229-141">下面的示例显示了 ASP.NET Core 3.0 应用程序的最简单的 Dockerfile：</span><span class="sxs-lookup"><span data-stu-id="d0229-141">The following example shows the simplest Dockerfile for an ASP.NET Core 3.0 application:</span></span>

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

<span data-ttu-id="d0229-142">Dockerfile 有两个部分：第一部分使用`sdk`基本映像来构建和发布应用程序;第二部分使用基本映像来构建和发布应用程序。第二个从基中`aspnet`创建运行时映像。</span><span class="sxs-lookup"><span data-stu-id="d0229-142">The Dockerfile has two parts: the first uses the `sdk` base image to build and publish the application; the second creates a runtime image from the `aspnet` base.</span></span> <span data-ttu-id="d0229-143">这是因为`sdk`映像约为 900 MB，而运行时映像的映像约为 200 MB，并且大多数内容在运行时是不必要的。</span><span class="sxs-lookup"><span data-stu-id="d0229-143">This is because the `sdk` image is around 900 MB, compared to around 200 MB for the runtime image, and most of its contents are unnecessary at runtime.</span></span>

### <a name="the-build-steps"></a><span data-ttu-id="d0229-144">生成步骤</span><span class="sxs-lookup"><span data-stu-id="d0229-144">The build steps</span></span>

| <span data-ttu-id="d0229-145">步骤</span><span class="sxs-lookup"><span data-stu-id="d0229-145">Step</span></span> | <span data-ttu-id="d0229-146">说明</span><span class="sxs-lookup"><span data-stu-id="d0229-146">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="d0229-147">声明基本映像并分配`builder`别名。</span><span class="sxs-lookup"><span data-stu-id="d0229-147">Declares the base image and assigns the `builder` alias.</span></span> |
| `WORKDIR /src` | <span data-ttu-id="d0229-148">创建`/src`目录并将其设置为当前工作目录。</span><span class="sxs-lookup"><span data-stu-id="d0229-148">Creates the `/src` directory and sets it as the current working directory.</span></span> |
| `COPY . .` | <span data-ttu-id="d0229-149">将主机上当前目录下的所有内容复制到映像上的当前目录中。</span><span class="sxs-lookup"><span data-stu-id="d0229-149">Copies everything below the current directory on the host into the current directory on the image.</span></span> |
| `RUN dotnet restore` | <span data-ttu-id="d0229-150">还原任何外部包（ASP.NET与 SDK 一起预安装核心 3.0 框架）。</span><span class="sxs-lookup"><span data-stu-id="d0229-150">Restores any external packages (ASP.NET Core 3.0 framework is pre-installed with the SDK).</span></span> |
| `RUN dotnet publish ...` | <span data-ttu-id="d0229-151">生成和发布发布版本。</span><span class="sxs-lookup"><span data-stu-id="d0229-151">Builds and publishes a Release build.</span></span> <span data-ttu-id="d0229-152">请注意，`--runtime`该标志不是必需的。</span><span class="sxs-lookup"><span data-stu-id="d0229-152">Note that the `--runtime` flag isn't required.</span></span> |

### <a name="the-runtime-image-steps"></a><span data-ttu-id="d0229-153">运行时映像步骤</span><span class="sxs-lookup"><span data-stu-id="d0229-153">The runtime image steps</span></span>

| <span data-ttu-id="d0229-154">步骤</span><span class="sxs-lookup"><span data-stu-id="d0229-154">Step</span></span> | <span data-ttu-id="d0229-155">说明</span><span class="sxs-lookup"><span data-stu-id="d0229-155">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="d0229-156">声明新的基本映像。</span><span class="sxs-lookup"><span data-stu-id="d0229-156">Declares a new base image.</span></span> |
| `WORKDIR /app` | <span data-ttu-id="d0229-157">创建`/app`目录并将其设置为当前工作目录。</span><span class="sxs-lookup"><span data-stu-id="d0229-157">Creates the `/app` directory and sets it as the current working directory.</span></span> |
| `COPY --from=builder ...` | <span data-ttu-id="d0229-158">使用第一`builder``FROM`行中的别名从上一个图像复制已发布的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d0229-158">Copies the published application from the previous image, by using the `builder` alias from the first `FROM` line.</span></span> |
| `ENTRYPOINT [ ... ]` | <span data-ttu-id="d0229-159">将命令设置在容器启动时运行。</span><span class="sxs-lookup"><span data-stu-id="d0229-159">Sets the command to run when the container starts.</span></span> <span data-ttu-id="d0229-160">运行时`dotnet`映像中的命令只能运行 DLL 文件。</span><span class="sxs-lookup"><span data-stu-id="d0229-160">The `dotnet` command in the runtime image can only run DLL files.</span></span> |

### <a name="https-in-docker"></a><span data-ttu-id="d0229-161">Docker 中的 HTTPS</span><span class="sxs-lookup"><span data-stu-id="d0229-161">HTTPS in Docker</span></span>

<span data-ttu-id="d0229-162">Docker 的 Microsoft 基本`ASPNETCORE_URLS`映像将环境`http://+:80`变量设置为 ，这意味着 Kestrel 在该端口上运行没有 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="d0229-162">Microsoft base images for Docker set the `ASPNETCORE_URLS` environment variable to `http://+:80`, meaning that Kestrel runs without HTTPS on that port.</span></span> <span data-ttu-id="d0229-163">如果将 HTTPS 与自定义证书一起使用（如[自托管 gRPC 应用程序中](self-hosted.md)所述），则应重写此证书。</span><span class="sxs-lookup"><span data-stu-id="d0229-163">If you're using HTTPS with a custom certificate (as described in [Self-hosted gRPC applications](self-hosted.md)), you should override this.</span></span> <span data-ttu-id="d0229-164">在 Dockerfile 的运行时映像创建部分设置环境变量。</span><span class="sxs-lookup"><span data-stu-id="d0229-164">Set the environment variable in the runtime image creation part of your Dockerfile.</span></span>

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a><span data-ttu-id="d0229-165">.dockerignore 文件</span><span class="sxs-lookup"><span data-stu-id="d0229-165">The .dockerignore file</span></span>

<span data-ttu-id="d0229-166">与从`.gitignore`源代码管理中排除某些文件和目录的文件类似，`.dockerignore`该文件可用于在生成期间将文件和目录复制到映像。</span><span class="sxs-lookup"><span data-stu-id="d0229-166">Much like `.gitignore` files that exclude certain files and directories from source control, the `.dockerignore` file can be used to exclude files and directories from being copied to the image during build.</span></span> <span data-ttu-id="d0229-167">这不仅节省了复制时间，还可以避免将 PC 中的`obj`目录复制到映像中出现的一些错误。</span><span class="sxs-lookup"><span data-stu-id="d0229-167">This not only saves time copying, but can also avoid some errors that arise from having the `obj` directory from your PC copied into the image.</span></span> <span data-ttu-id="d0229-168">至少，应为`bin`文件添加条目，并`obj`添加到文件中`.dockerignore`。</span><span class="sxs-lookup"><span data-stu-id="d0229-168">At a minimum, you should add entries for `bin` and `obj` to your `.dockerignore` file.</span></span>

```console
bin/
obj/
```

## <a name="build-the-image"></a><span data-ttu-id="d0229-169">生成映像</span><span class="sxs-lookup"><span data-stu-id="d0229-169">Build the image</span></span>

<span data-ttu-id="d0229-170">对于具有单个应用程序的解决方案，以及单个 Dockerfile，将 Dockerfile 放在基本目录中是最简单的。</span><span class="sxs-lookup"><span data-stu-id="d0229-170">For a solution with a single application, and thus a single Dockerfile, it's simplest to put the Dockerfile in the base directory.</span></span> <span data-ttu-id="d0229-171">换句话说，将其放在与`.sln`文件相同的目录中。</span><span class="sxs-lookup"><span data-stu-id="d0229-171">In other words, put it in the same directory as the `.sln` file.</span></span> <span data-ttu-id="d0229-172">在这种情况下，要生成映像，请使用包含 Dockerfile`docker build`的目录中的以下命令。</span><span class="sxs-lookup"><span data-stu-id="d0229-172">In that case, to build the image, use the following `docker build` command from the directory containing the Dockerfile.</span></span>

```console
docker build --tag stockdata .
```

<span data-ttu-id="d0229-173">令人困惑的名称`--tag`标志（可以缩短为`-t`）指定图像的整个名称，包括指定的实际标记。</span><span class="sxs-lookup"><span data-stu-id="d0229-173">The confusingly named `--tag` flag (which can be shortened to `-t`) specifies the whole name of the image, including the actual tag if specified.</span></span> <span data-ttu-id="d0229-174">`.`末尾指定将在其中运行生成的上下文;Docker 文件中命令的`COPY`当前工作目录。</span><span class="sxs-lookup"><span data-stu-id="d0229-174">The `.` at the end specifies the context in which the build will be run; the current working directory for the `COPY` commands in the Dockerfile.</span></span>

<span data-ttu-id="d0229-175">如果单个解决方案中有多个应用程序，则可以将每个应用程序的 Dockerfile 保留在文件旁边的`.csproj`自己的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d0229-175">If you have multiple applications within a single solution, you can keep the Dockerfile for each application in its own folder, beside the `.csproj` file.</span></span> <span data-ttu-id="d0229-176">您仍应从基`docker build`目录中运行该命令，以确保将解决方案和所有项目复制到映像中。</span><span class="sxs-lookup"><span data-stu-id="d0229-176">You should still run the `docker build` command from the base directory to ensure that the solution and all the projects are copied into the image.</span></span> <span data-ttu-id="d0229-177">可以使用`--file`（ 或`-f`） 标志在当前目录下方指定 Docker 文件。</span><span class="sxs-lookup"><span data-stu-id="d0229-177">You can specify a Dockerfile below the current directory by using the `--file` (or `-f`) flag.</span></span>

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a><span data-ttu-id="d0229-178">在计算机上的容器中运行映像</span><span class="sxs-lookup"><span data-stu-id="d0229-178">Run the image in a container on your machine</span></span>

<span data-ttu-id="d0229-179">要在本地 Docker 实例中运行映像，请使用`docker run`命令。</span><span class="sxs-lookup"><span data-stu-id="d0229-179">To run the image in your local Docker instance, use the `docker run` command.</span></span>

```console
docker run -ti -p 5000:80 stockdata
```

<span data-ttu-id="d0229-180">标志`-ti`将当前终端连接到容器的终端，并在交互式模式下运行。</span><span class="sxs-lookup"><span data-stu-id="d0229-180">The `-ti` flag connects your current terminal to the container's terminal, and runs in interactive mode.</span></span> <span data-ttu-id="d0229-181">容器`-p 5000:80`上的发布（链接）端口 80 到本地主机网络接口上的端口 5000。</span><span class="sxs-lookup"><span data-stu-id="d0229-181">The `-p 5000:80` publishes (links) port 80 on the container to port 5000 on the localhost network interface.</span></span>

## <a name="push-the-image-to-a-registry"></a><span data-ttu-id="d0229-182">将映像推送到注册表</span><span class="sxs-lookup"><span data-stu-id="d0229-182">Push the image to a registry</span></span>

<span data-ttu-id="d0229-183">验证映像是否正常工作后，将其推送到 Docker 注册表，使其在其他系统上可用。</span><span class="sxs-lookup"><span data-stu-id="d0229-183">After you've verified that the image works, push it to a Docker registry to make it available on other systems.</span></span> <span data-ttu-id="d0229-184">内部网络将需要预配 Docker 注册表。</span><span class="sxs-lookup"><span data-stu-id="d0229-184">Internal networks will need to provision a Docker registry.</span></span> <span data-ttu-id="d0229-185">这可以像运行[Docker 自己的`registry`映像](https://docs.docker.com/registry/deploying/)（Docker 注册表在 Docker 容器中运行）一样简单，但有多种更全面的解决方案可用。</span><span class="sxs-lookup"><span data-stu-id="d0229-185">This can be as simple as running [Docker's own `registry` image](https://docs.docker.com/registry/deploying/) (the Docker registry runs in a Docker container), but there are various more comprehensive solutions available.</span></span> <span data-ttu-id="d0229-186">对于外部共享和云使用，可以使用各种托管注册表，例如[Azure 容器注册表](https://docs.microsoft.com/azure/container-registry/)或[Docker Hub。](https://docs.docker.com/docker-hub/repos/)</span><span class="sxs-lookup"><span data-stu-id="d0229-186">For external sharing and cloud use, there are various managed registries available, such as [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) or [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span></span>

<span data-ttu-id="d0229-187">要推送到 Docker 中心，请用用户或组织名称对图像名称进行前缀。</span><span class="sxs-lookup"><span data-stu-id="d0229-187">To push to Docker Hub, prefix the image name with your user or organization name.</span></span>

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

<span data-ttu-id="d0229-188">要推送到专用注册表，使用注册表主机名和组织名称对映像名称进行前缀。</span><span class="sxs-lookup"><span data-stu-id="d0229-188">To push to a private registry, prefix the image name with the registry host name and the organization name.</span></span>

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

<span data-ttu-id="d0229-189">映像在注册表中后，您可以将其部署到单独的 Docker 主机，或部署到容器编排引擎（如 Kubernetes）。</span><span class="sxs-lookup"><span data-stu-id="d0229-189">After the image is in a registry, you can deploy it to individual Docker hosts, or to a container orchestration engine like Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d0229-190">[上一个](self-hosted.md)
>[下一个](kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="d0229-190">[Previous](self-hosted.md)
[Next](kubernetes.md)</span></span>
