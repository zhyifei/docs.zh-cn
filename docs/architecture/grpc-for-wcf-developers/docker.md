---
title: 适用于 WCF 开发人员的 Docker gRPC
description: 为 ASP.NET Core gRPC 应用程序创建 Docker 映像
ms.date: 09/02/2019
ms.openlocfilehash: a5aceb4b5270cb828965e990a62db4147012adff
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967842"
---
# <a name="docker"></a><span data-ttu-id="2b547-103">Docker</span><span class="sxs-lookup"><span data-stu-id="2b547-103">Docker</span></span>

<span data-ttu-id="2b547-104">本部分将介绍如何创建用于 ASP.NET Core gRPC 应用程序的 Docker 映像，并准备在 Docker、Kubernetes 或其他容器环境中运行。</span><span class="sxs-lookup"><span data-stu-id="2b547-104">This section will cover the creation of Docker images for ASP.NET Core gRPC applications, ready to run in Docker, Kubernetes, or other container environments.</span></span> <span data-ttu-id="2b547-105">在 GitHub 上的[dotnet/gRPC/](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample)存储库中提供了使用的示例应用程序，其中包含 ASP.NET Core MVC web 应用和 gRPC 服务。</span><span class="sxs-lookup"><span data-stu-id="2b547-105">The sample application used, with an ASP.NET Core MVC web app and a gRPC service, is available on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="microsoft-base-images-for-aspnet-core-applications"></a><span data-ttu-id="2b547-106">用于 ASP.NET Core 应用程序的 Microsoft 基础映像</span><span class="sxs-lookup"><span data-stu-id="2b547-106">Microsoft base images for ASP.NET Core applications</span></span>

<span data-ttu-id="2b547-107">Microsoft 提供了一系列用于构建和运行 .NET Core 应用程序的基本映像。</span><span class="sxs-lookup"><span data-stu-id="2b547-107">Microsoft provides a range of base images for building and running .NET Core applications.</span></span> <span data-ttu-id="2b547-108">若要创建 ASP.NET Core 3.0 图像，请使用两个基本映像：用于生成和发布应用程序的 SDK 映像，以及用于部署的运行时映像。</span><span class="sxs-lookup"><span data-stu-id="2b547-108">To create an ASP.NET Core 3.0 image, two base images are used: an SDK image to build and publish the application, and a runtime image for deployment.</span></span>

| <span data-ttu-id="2b547-109">映像</span><span class="sxs-lookup"><span data-stu-id="2b547-109">Image</span></span> | <span data-ttu-id="2b547-110">说明</span><span class="sxs-lookup"><span data-stu-id="2b547-110">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="2b547-111">mcr.microsoft.com/dotnet/core/sdk</span><span class="sxs-lookup"><span data-stu-id="2b547-111">mcr.microsoft.com/dotnet/core/sdk</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | <span data-ttu-id="2b547-112">用于生成具有 `docker build`的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2b547-112">For building applications with `docker build`.</span></span> <span data-ttu-id="2b547-113">不能在生产中使用。</span><span class="sxs-lookup"><span data-stu-id="2b547-113">Not to be used in production.</span></span> |
| [<span data-ttu-id="2b547-114">mcr.microsoft.com/dotnet/core/aspnet</span><span class="sxs-lookup"><span data-stu-id="2b547-114">mcr.microsoft.com/dotnet/core/aspnet</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | <span data-ttu-id="2b547-115">包含运行时和 ASP.NET Core 依赖项。</span><span class="sxs-lookup"><span data-stu-id="2b547-115">Contains the runtime and ASP.NET Core dependencies.</span></span> <span data-ttu-id="2b547-116">用于生产。</span><span class="sxs-lookup"><span data-stu-id="2b547-116">For production.</span></span> |

<span data-ttu-id="2b547-117">对于每个映像，都有四个基于不同 Linux 分发的变量，由标记来区分。</span><span class="sxs-lookup"><span data-stu-id="2b547-117">For each image, there are four variants based on different Linux distributions, distinguished by tags.</span></span>

| <span data-ttu-id="2b547-118">图像标记</span><span class="sxs-lookup"><span data-stu-id="2b547-118">Image tag(s)</span></span> | <span data-ttu-id="2b547-119">Linux</span><span class="sxs-lookup"><span data-stu-id="2b547-119">Linux</span></span> | <span data-ttu-id="2b547-120">注意</span><span class="sxs-lookup"><span data-stu-id="2b547-120">Notes</span></span> |
| --------- | ----- | ----- |
| <span data-ttu-id="2b547-121">3.0-buster、3。0</span><span class="sxs-lookup"><span data-stu-id="2b547-121">3.0-buster, 3.0</span></span> | <span data-ttu-id="2b547-122">Debian 10</span><span class="sxs-lookup"><span data-stu-id="2b547-122">Debian 10</span></span> | <span data-ttu-id="2b547-123">如果未指定操作系统变体，则为默认映像。</span><span class="sxs-lookup"><span data-stu-id="2b547-123">The default image if no OS variant is specified.</span></span> |
| <span data-ttu-id="2b547-124">3.0-alpine</span><span class="sxs-lookup"><span data-stu-id="2b547-124">3.0-alpine</span></span> | <span data-ttu-id="2b547-125">Alpine 3。9</span><span class="sxs-lookup"><span data-stu-id="2b547-125">Alpine 3.9</span></span> | <span data-ttu-id="2b547-126">Alpine 基本映像比 Debian 或 Ubuntu 映像小得多。</span><span class="sxs-lookup"><span data-stu-id="2b547-126">Alpine base images are much smaller than Debian or Ubuntu ones.</span></span> |
| <span data-ttu-id="2b547-127">3.0-disco</span><span class="sxs-lookup"><span data-stu-id="2b547-127">3.0-disco</span></span> | <span data-ttu-id="2b547-128">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="2b547-128">Ubuntu 19.04</span></span> | |
| <span data-ttu-id="2b547-129">3.0-bionic</span><span class="sxs-lookup"><span data-stu-id="2b547-129">3.0-bionic</span></span> | <span data-ttu-id="2b547-130">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="2b547-130">Ubuntu 18.04</span></span> | |

<span data-ttu-id="2b547-131">相比200于 Debian 和 Ubuntu 映像，Alpine 基本映像约 100 MB，但在 Alpine 的包管理中，某些软件包或库可能不可用。</span><span class="sxs-lookup"><span data-stu-id="2b547-131">The Alpine base image is around 100 MB, compared to 200 MB for the Debian and Ubuntu images, but some software packages or libraries may not be available in Alpine's package management.</span></span> <span data-ttu-id="2b547-132">如果你不确定要使用哪个图像，则最好坚持使用默认的 Debian，除非你有说服力需要使用不同的发行版。</span><span class="sxs-lookup"><span data-stu-id="2b547-132">If you're not sure which image to use, it's best to stick to the default Debian unless you have a compelling need to use a different distro.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b547-133">请确保为生成和运行时使用相同的 Linux 变体。</span><span class="sxs-lookup"><span data-stu-id="2b547-133">Make sure you use the same variant of Linux for the build and the runtime.</span></span> <span data-ttu-id="2b547-134">在一个变体上构建和发布的应用程序可能无法在另一个上运行。</span><span class="sxs-lookup"><span data-stu-id="2b547-134">Applications built and published on one variant may not work on another.</span></span>

## <a name="create-a-docker-image"></a><span data-ttu-id="2b547-135">创建 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="2b547-135">Create a Docker image</span></span>

<span data-ttu-id="2b547-136">Docker 映像是由*Dockerfile*定义的，它包含生成应用程序所需的所有命令，并安装生成或运行应用程序所需的任何依赖项。</span><span class="sxs-lookup"><span data-stu-id="2b547-136">A Docker image is defined by a *Dockerfile*, a text file that contains all the commands that are needed to build the application and install any dependencies that are required for either building or running the application.</span></span> <span data-ttu-id="2b547-137">下面的示例演示 ASP.NET Core 3.0 应用程序的最简单的 Dockerfile：</span><span class="sxs-lookup"><span data-stu-id="2b547-137">The following example shows the simplest Dockerfile for an ASP.NET Core 3.0 application:</span></span>

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

<span data-ttu-id="2b547-138">Dockerfile 有两部分：第一个使用 `sdk` 基本映像来生成和发布应用程序;第二个基于 `aspnet` 创建运行时映像。</span><span class="sxs-lookup"><span data-stu-id="2b547-138">The Dockerfile has two parts: the first uses the `sdk` base image to build and publish the application; the second creates a runtime image from the `aspnet` base.</span></span> <span data-ttu-id="2b547-139">这是因为，对于运行时映像，`sdk` 图像大约为 900 MB （约 200 MB），并且在运行时不需要其大部分内容。</span><span class="sxs-lookup"><span data-stu-id="2b547-139">This is because the `sdk` image is around 900 MB compared to around 200 MB for the runtime image, and most of its contents are unnecessary at runtime.</span></span>

### <a name="the-build-steps"></a><span data-ttu-id="2b547-140">生成步骤</span><span class="sxs-lookup"><span data-stu-id="2b547-140">The build steps</span></span>

| <span data-ttu-id="2b547-141">步骤</span><span class="sxs-lookup"><span data-stu-id="2b547-141">Step</span></span> | <span data-ttu-id="2b547-142">说明</span><span class="sxs-lookup"><span data-stu-id="2b547-142">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="2b547-143">声明基映像并分配 `builder` 别名（有关说明，请参阅下一部分）。</span><span class="sxs-lookup"><span data-stu-id="2b547-143">Declares the base image and assigns the `builder` alias (see next section for explanation).</span></span> |
| `WORKDIR /src` | <span data-ttu-id="2b547-144">创建 `/src` 目录，并将其设置为当前工作目录。</span><span class="sxs-lookup"><span data-stu-id="2b547-144">Creates the `/src` directory and sets it as the current working directory.</span></span> |
| `COPY . .` | <span data-ttu-id="2b547-145">将主机上当前目录下的所有内容复制到映像上的当前目录。</span><span class="sxs-lookup"><span data-stu-id="2b547-145">Copies everything below the current directory on the host into the current directory on the image.</span></span> |
| `RUN dotnet restore` | <span data-ttu-id="2b547-146">还原任何外部包（ASP.NET Core 3.0 framework 已与 SDK 一起预安装）。</span><span class="sxs-lookup"><span data-stu-id="2b547-146">Restores any external packages (ASP.NET Core 3.0 framework is pre-installed with the SDK).</span></span> |
| `RUN dotnet publish ...` | <span data-ttu-id="2b547-147">生成并发布发布版本。</span><span class="sxs-lookup"><span data-stu-id="2b547-147">Builds and publishes a Release build.</span></span> <span data-ttu-id="2b547-148">请注意，不需要 `--runtime` 标志。</span><span class="sxs-lookup"><span data-stu-id="2b547-148">Note that the `--runtime` flag isn't required.</span></span> |

### <a name="the-runtime-image-steps"></a><span data-ttu-id="2b547-149">运行时映像步骤</span><span class="sxs-lookup"><span data-stu-id="2b547-149">The runtime image steps</span></span>

| <span data-ttu-id="2b547-150">步骤</span><span class="sxs-lookup"><span data-stu-id="2b547-150">Step</span></span> | <span data-ttu-id="2b547-151">说明</span><span class="sxs-lookup"><span data-stu-id="2b547-151">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="2b547-152">声明新的基本映像。</span><span class="sxs-lookup"><span data-stu-id="2b547-152">Declares a new base image.</span></span> |
| `WORKDIR /app` | <span data-ttu-id="2b547-153">创建 `/app` 目录，并将其设置为当前工作目录。</span><span class="sxs-lookup"><span data-stu-id="2b547-153">Creates the `/app` directory and sets it as the current working directory.</span></span> |
| `COPY --from=builder ...` | <span data-ttu-id="2b547-154">使用第一个 `FROM` 行中的 `builder` 别名从上一个映像复制已发布的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2b547-154">Copies the published application from the previous image, using the `builder` alias from the first `FROM` line.</span></span> |
| `ENTRYPOINT [ ... ]` | <span data-ttu-id="2b547-155">设置要在容器启动时运行的命令。</span><span class="sxs-lookup"><span data-stu-id="2b547-155">Sets the command to run when the container starts.</span></span> <span data-ttu-id="2b547-156">运行时映像中的 `dotnet` 命令只能运行 DLL 文件。</span><span class="sxs-lookup"><span data-stu-id="2b547-156">The `dotnet` command in the runtime image can only run DLL files.</span></span> |

### <a name="https-in-docker"></a><span data-ttu-id="2b547-157">Docker 中的 HTTPS</span><span class="sxs-lookup"><span data-stu-id="2b547-157">HTTPS in Docker</span></span>

<span data-ttu-id="2b547-158">用于 Docker 的 Microsoft 基础映像将 `ASPNETCORE_URLS` 环境变量设置为 `http://+:80`，这意味着 Kestrel 将在该端口上不带 HTTPS 运行。</span><span class="sxs-lookup"><span data-stu-id="2b547-158">Microsoft's base images for Docker set the `ASPNETCORE_URLS` environment variable to `http://+:80`, meaning that Kestrel will run without HTTPS on that port.</span></span> <span data-ttu-id="2b547-159">如果你使用的是带有自定义证书的 HTTPS （如[前一部分](self-hosted.md)中所述），则应通过**在 Dockerfile 的运行时映像创建部分**设置环境变量来替代此设置。</span><span class="sxs-lookup"><span data-stu-id="2b547-159">If you're using HTTPS with a custom certificate (as described in [the previous section](self-hosted.md)), you should override this by setting the environment variable **in the runtime image creation part** of your Dockerfile.</span></span>

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a><span data-ttu-id="2b547-160">.Dockerignore 文件</span><span class="sxs-lookup"><span data-stu-id="2b547-160">The .dockerignore file</span></span>

<span data-ttu-id="2b547-161">与从源代码管理中排除某些文件和目录 `.gitignore` 文件非常相似，`.dockerignore` 文件可用于在生成过程中排除文件和目录被复制到映像。</span><span class="sxs-lookup"><span data-stu-id="2b547-161">Much like `.gitignore` files that exclude certain files and directories from source control, the `.dockerignore` file can be used to exclude files and directories from being copied to the image during build.</span></span> <span data-ttu-id="2b547-162">这不仅节省了时间复制，还可以避免由于将 `obj` 目录从 PC 复制到映像中而导致的一些混乱的错误。</span><span class="sxs-lookup"><span data-stu-id="2b547-162">This not only saves time copying, but can also avoid some confusing errors that arise from having (particularly) the `obj` directory from your PC copied into the image.</span></span> <span data-ttu-id="2b547-163">应将 `bin` 和 `obj` 的条目至少添加到 `.dockerignore` 文件中。</span><span class="sxs-lookup"><span data-stu-id="2b547-163">You should add at least entries for `bin` and `obj` to your `.dockerignore` file.</span></span>

```console
bin/
obj/
```

## <a name="build-the-image"></a><span data-ttu-id="2b547-164">生成映像</span><span class="sxs-lookup"><span data-stu-id="2b547-164">Build the image</span></span>

<span data-ttu-id="2b547-165">对于具有单个应用程序的解决方案，因此，如果是单个 Dockerfile，则最简单的方法是将 Dockerfile 放在基目录中;这就是与 `.sln` 文件相同的目录。</span><span class="sxs-lookup"><span data-stu-id="2b547-165">For a solution with a single application, and thus a single Dockerfile, it is simplest to put the Dockerfile in the base directory; that is, the same directory as the `.sln` file.</span></span> <span data-ttu-id="2b547-166">在这种情况下，若要生成映像，请在包含 Dockerfile 的目录中使用以下 `docker build` 命令。</span><span class="sxs-lookup"><span data-stu-id="2b547-166">In that case, to build the image, use the following `docker build` command from the directory containing the Dockerfile.</span></span>

```console
docker build --tag stockdata .
```

<span data-ttu-id="2b547-167">名为 `--tag` 标志的令困惑（可将其缩短为 `-t`）指定图像的整个名称，*包括*实际标记（如果指定）。</span><span class="sxs-lookup"><span data-stu-id="2b547-167">The confusingly named `--tag` flag (which can be shortened to `-t`) specifies the whole name of the image, *including* the actual tag if specified.</span></span> <span data-ttu-id="2b547-168">末尾处的 `.` 指定将在其中运行生成的*上下文*;Dockerfile 中 `COPY` 命令的当前工作目录。</span><span class="sxs-lookup"><span data-stu-id="2b547-168">The `.` at the end specifies the *context* in which the build will be run; the current working directory for the `COPY` commands in the Dockerfile.</span></span>

<span data-ttu-id="2b547-169">如果一个解决方案中有多个应用程序，则可以将每个应用程序的 Dockerfile 保存在其自己的文件夹中的 `.csproj` 文件旁边，但你仍应该从基本目录运行 `docker build` 命令，以确保将解决方案和所有项目都复制到该映像。</span><span class="sxs-lookup"><span data-stu-id="2b547-169">If you have multiple applications within a single solution, you can keep the Dockerfile for each application in its own folder, beside the `.csproj` file, but you should still run the `docker build` command from the base directory to ensure that the solution and all the projects are copied into the image.</span></span> <span data-ttu-id="2b547-170">可以使用 `--file` （或 `-f`）标志在当前目录下指定 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="2b547-170">You can specify a Dockerfile below the current directory using the `--file` (or `-f`) flag.</span></span>

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a><span data-ttu-id="2b547-171">在计算机上的容器中运行映像</span><span class="sxs-lookup"><span data-stu-id="2b547-171">Run the image in a container on your machine</span></span>

<span data-ttu-id="2b547-172">若要在本地 Docker 实例中运行映像，请使用 `docker run` 命令。</span><span class="sxs-lookup"><span data-stu-id="2b547-172">To run the image in your local Docker instance, use the `docker run` command.</span></span>

```console
docker run -ti -p 5000:80 stockdata
```

<span data-ttu-id="2b547-173">`-ti` 标志将当前终端连接到容器的终端并在交互模式下运行。</span><span class="sxs-lookup"><span data-stu-id="2b547-173">The `-ti` flag connects your current terminal to the container's terminal and runs in interactive mode.</span></span> <span data-ttu-id="2b547-174">`-p 5000:80` 将容器上的端口80发布（链接）到 localhost 网络接口上的端口80。</span><span class="sxs-lookup"><span data-stu-id="2b547-174">The `-p 5000:80` publishes (links) port 80 on the container to port 80 on the localhost network interface.</span></span>

## <a name="push-the-image-to-a-registry"></a><span data-ttu-id="2b547-175">将映像推送到注册表</span><span class="sxs-lookup"><span data-stu-id="2b547-175">Push the image to a registry</span></span>

<span data-ttu-id="2b547-176">验证映像是否正常工作后，需要将其推送到 Docker 注册表，使其在其他系统上可用。</span><span class="sxs-lookup"><span data-stu-id="2b547-176">Once you've verified that the image works, you need to push it to a Docker registry to make it available on other systems.</span></span> <span data-ttu-id="2b547-177">内部网络将需要预配 Docker 注册表。</span><span class="sxs-lookup"><span data-stu-id="2b547-177">Internal networks will need to provision a Docker registry.</span></span> <span data-ttu-id="2b547-178">这就像运行[Docker 自己的 `registry` 映像](https://docs.docker.com/registry/deploying/)一样简单（即 docker 注册表在 docker 容器中运行），但有多种更全面的解决方案可用。</span><span class="sxs-lookup"><span data-stu-id="2b547-178">This can be as simple as running [Docker's own `registry` image](https://docs.docker.com/registry/deploying/) (that's right, the Docker registry runs in a Docker container), but there are various more comprehensive solutions available.</span></span> <span data-ttu-id="2b547-179">对于外部共享和云使用，有多种可用的托管注册表，如[Azure 容器注册表](https://docs.microsoft.com/azure/container-registry/)或[Docker Hub](https://docs.docker.com/docker-hub/repos/)。</span><span class="sxs-lookup"><span data-stu-id="2b547-179">For external sharing and cloud use, there are various managed registries available, such as [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) or [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span></span>

<span data-ttu-id="2b547-180">若要推送到 Docker 中心，请在映像名称后加上用户或组织名称。</span><span class="sxs-lookup"><span data-stu-id="2b547-180">To push to the Docker Hub, prefix the image name with your user or organization name.</span></span>

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

<span data-ttu-id="2b547-181">若要推送到专用注册表，请使用注册表主机名和组织名称作为映像名称的前缀。</span><span class="sxs-lookup"><span data-stu-id="2b547-181">To push to a private registry, prefix the image name with the registry host name and the organization name.</span></span>

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

<span data-ttu-id="2b547-182">映像进入注册表后，可将其部署到各个 Docker 主机或容器业务流程引擎（如 Kubernetes）。</span><span class="sxs-lookup"><span data-stu-id="2b547-182">Once the image is in a registry, you can deploy it to individual Docker hosts or to a container orchestration engine like Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2b547-183">[上一页](self-hosted.md)
>[下一页](kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="2b547-183">[Previous](self-hosted.md)
[Next](kubernetes.md)</span></span>
