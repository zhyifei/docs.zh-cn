---
title: 构建 ASP.NET Core 2.1 应用程序部署到 AKS/Kubernetes 群集与 Linux 容器
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/25/2019
ms.openlocfilehash: a00a5c42facb105a23cd85fce79f9fd16a96ccfa
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835507"
---
# <a name="build-aspnet-core-21-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a><span data-ttu-id="5896e-103">构建 ASP.NET Core 2.1 应用程序与 Linux 容器部署到 AKS/Kubernetes 业务流程协调程序</span><span class="sxs-lookup"><span data-stu-id="5896e-103">Build ASP.NET Core 2.1 applications deployed as Linux containers into an AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="5896e-104">Azure Kubernetes 服务 (AKS) 是 Azure 的托管的 Kubernetes 业务流程服务可简化容器部署和管理。</span><span class="sxs-lookup"><span data-stu-id="5896e-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="5896e-105">AKS 主要功能如下：</span><span class="sxs-lookup"><span data-stu-id="5896e-105">AKS main features are:</span></span>

- <span data-ttu-id="5896e-106">Azure 托管的控制平面</span><span class="sxs-lookup"><span data-stu-id="5896e-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="5896e-107">自动的升级</span><span class="sxs-lookup"><span data-stu-id="5896e-107">Automated upgrades</span></span>
- <span data-ttu-id="5896e-108">自我修复</span><span class="sxs-lookup"><span data-stu-id="5896e-108">Self-healing</span></span>
- <span data-ttu-id="5896e-109">用户可配置缩放</span><span class="sxs-lookup"><span data-stu-id="5896e-109">User configurable scaling</span></span>
- <span data-ttu-id="5896e-110">简单的用户体验的开发人员和群集操作员。</span><span class="sxs-lookup"><span data-stu-id="5896e-110">A simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="5896e-111">下面的示例探索的 ASP.NET Core 2.1 应用程序在 Linux 上运行并完成开发时，将部署到 AKS 群集在 Azure 中，创建使用 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="5896e-111">The following examples explore the creation of an ASP.NET Core 2.1 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2017.</span></span>

## <a name="creating-the-aspnet-core-21-project-using-visual-studio-2017"></a><span data-ttu-id="5896e-112">创建 ASP.NET Core 2.1 项目使用 Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="5896e-112">Creating the ASP.NET Core 2.1 Project using Visual Studio 2017</span></span>

<span data-ttu-id="5896e-113">ASP.NET Core 是由 Microsoft 和 GitHub 上的.NET 社区维护一个通用开发平台。</span><span class="sxs-lookup"><span data-stu-id="5896e-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="5896e-114">它是跨平台的，支持 Windows、macOS 和 Linux，并且可用于设备、云和嵌入式/IoT 方案。</span><span class="sxs-lookup"><span data-stu-id="5896e-114">It is cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="5896e-115">此示例使用一个简单的项目为基础的基于 Visual Studio Web API 模板，因此您无需任何其他的知识来创建示例。</span><span class="sxs-lookup"><span data-stu-id="5896e-115">This example uses a simple project that's based based on a Visual Studio Web API template, so you don't need any additional knowledge to create the sample.</span></span> <span data-ttu-id="5896e-116">只需使用一个包含所有要使用 REST API，使用 ASP.NET Core 2.1 技术运行一个小的项目的元素的标准模板创建项目。</span><span class="sxs-lookup"><span data-stu-id="5896e-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API, using ASP.NET Core 2.1 technology.</span></span>

![在 Visual Studio 中，选择 ASP.NET Core Web 应用程序中添加新项目窗口。](media/create-aspnet-core-application.png)

<span data-ttu-id="5896e-118">**图 4-36**。</span><span class="sxs-lookup"><span data-stu-id="5896e-118">**Figure 4-36**.</span></span> <span data-ttu-id="5896e-119">创建 ASP.NET Core 应用程序</span><span class="sxs-lookup"><span data-stu-id="5896e-119">Creating ASP.NET Core Application</span></span>

<span data-ttu-id="5896e-120">若要在 Visual Studio 中创建示例项目，选择**文件** > **新建** > **项目**，选择**Web**项目类型的左窗格中后, 跟**ASP.NET Core Web 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="5896e-120">To create the sample project in Visual Studio, select **File** > **New** > **Project**, select the **Web** project types in the left pane, followed by **ASP.NET Core Web Application**.</span></span>

<span data-ttu-id="5896e-121">Visual Studio 列出了 web 项目的模板。</span><span class="sxs-lookup"><span data-stu-id="5896e-121">Visual Studio lists templates for web projects.</span></span> <span data-ttu-id="5896e-122">对于本示例中，选择**API**创建 ASP.NET Web API 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5896e-122">For our example, select **API** to create an ASP.NET Web API Application.</span></span>

<span data-ttu-id="5896e-123">验证已作为框架选择 ASP.NET Core 2.1。</span><span class="sxs-lookup"><span data-stu-id="5896e-123">Verify that you have selected ASP.NET Core 2.1 as the framework.</span></span> <span data-ttu-id="5896e-124">.NET core 2.1 中的最后一个版本的 Visual Studio 2017 包含和自动安装和安装 Visual Studio 2017 时为你配置。</span><span class="sxs-lookup"><span data-stu-id="5896e-124">.NET Core 2.1 is included in the last version of Visual Studio 2017 and is automatically installed and configured for you when you install Visual Studio 2017.</span></span>

![Visual Studio 对话框用于选择的 API 选项中选择的 ASP.NET Core Web 应用程序的类型。](media/create-web-api-application.png)

<span data-ttu-id="5896e-126">**图 4 37**。</span><span class="sxs-lookup"><span data-stu-id="5896e-126">**Figure 4-37**.</span></span> <span data-ttu-id="5896e-127">选择 ASP.NET CORE 2.1 和 Web API 项目类型</span><span class="sxs-lookup"><span data-stu-id="5896e-127">Selecting ASP.NET CORE 2.1 and Web API project type</span></span>

<span data-ttu-id="5896e-128">如果有任何以前版本的.NET Core，您可以下载并安装中的 2.1 版本<https://www.microsoft.com/net/download/core#/sdk>。</span><span class="sxs-lookup"><span data-stu-id="5896e-128">If you have any previous version of .NET Core, you can download and install the 2.1 version from <https://www.microsoft.com/net/download/core#/sdk>.</span></span>

<span data-ttu-id="5896e-129">创建项目时，可以添加 Docker 支持或之后，因此您可以 Docker 项目在任何时间。</span><span class="sxs-lookup"><span data-stu-id="5896e-129">You can add Docker support when creating the project or afterwards, so you can "Dockerize" your project at any time.</span></span> <span data-ttu-id="5896e-130">若要创建项目后添加 Docker 支持，请右键单击解决方案资源管理器中的项目节点并选择**外** > **Docker 支持**上下文菜单上。</span><span class="sxs-lookup"><span data-stu-id="5896e-130">To add Docker support after project creation, right-click on the project node in Solution Explorer and select **Add** > **Docker support** on the context menu.</span></span>

![若要向现有项目添加 Docker 支持的上下文菜单选项：右键单击 （项目） > 添加 > Docker 支持。](media/add-docker-support-to-project.png)

<span data-ttu-id="5896e-132">**图 4-38**。</span><span class="sxs-lookup"><span data-stu-id="5896e-132">**Figure 4-38**.</span></span> <span data-ttu-id="5896e-133">向现有项目添加 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="5896e-133">Adding Docker support to existing project</span></span>

<span data-ttu-id="5896e-134">若要完成添加 Docker 支持，可以选择 Windows 或 Linux。</span><span class="sxs-lookup"><span data-stu-id="5896e-134">To complete adding Docker support, you can choose Windows or Linux.</span></span> <span data-ttu-id="5896e-135">在这种情况下，选择**Linux**，这是因为 AKS 不支持 Windows 容器 （作为后期 2018)。</span><span class="sxs-lookup"><span data-stu-id="5896e-135">In this case, select **Linux**, because AKS doesn’t support Windows Containers (as of late 2018).</span></span>

![选项对话框，可选择目标 OS 的 Dockerfile。](media/select-linux-docker-support.png)

<span data-ttu-id="5896e-137">**图 4-39**。</span><span class="sxs-lookup"><span data-stu-id="5896e-137">**Figure 4-39**.</span></span> <span data-ttu-id="5896e-138">选择 Linux 容器。</span><span class="sxs-lookup"><span data-stu-id="5896e-138">Selecting Linux containers.</span></span>

<span data-ttu-id="5896e-139">使用这些简单的步骤，可以在 Linux 容器上运行 ASP.NET Core 2.1 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5896e-139">With these simple steps, you have your ASP.NET Core 2.1 application running on a Linux container.</span></span>

<span data-ttu-id="5896e-140">正如您所看到的 Visual Studio 2017 和 Docker 之间的集成是完全面向开发人员工作效率。</span><span class="sxs-lookup"><span data-stu-id="5896e-140">As you can see, the integration between Visual Studio 2017 and Docker is totally oriented to the developer’s productivity.</span></span>

<span data-ttu-id="5896e-141">现在可以运行应用程序**F5**密钥或通过使用**播放**按钮。</span><span class="sxs-lookup"><span data-stu-id="5896e-141">Now you can run your application with the **F5** key or by using the **Play** button.</span></span>

<span data-ttu-id="5896e-142">在运行该项目之后, 可以列出使用的映像`docker images`命令。</span><span class="sxs-lookup"><span data-stu-id="5896e-142">After running the project, you can list the images using the `docker images` command.</span></span> <span data-ttu-id="5896e-143">应会看到`mssampleapplication`创建自动部署我们的项目使用 Visual Studio 2017 的映像。</span><span class="sxs-lookup"><span data-stu-id="5896e-143">You should see the `mssampleapplication` image created by the automatic deployment of our project with Visual Studio 2017.</span></span>

```console
docker images
```

![控制台输出 docker 映像命令，从显示的列表：存储库、 标记、 映像 ID、 Created （日期） 和大小。](media/docker-images-command.png)

<span data-ttu-id="5896e-145">**图 4-40**。</span><span class="sxs-lookup"><span data-stu-id="5896e-145">**Figure 4-40**.</span></span> <span data-ttu-id="5896e-146">Docker 映像的视图</span><span class="sxs-lookup"><span data-stu-id="5896e-146">View of Docker images</span></span>

## <a name="register-the-solution-in-the-azure-container-registry"></a><span data-ttu-id="5896e-147">在 Azure 容器注册表中注册解决方案</span><span class="sxs-lookup"><span data-stu-id="5896e-147">Register the Solution in the Azure Container Registry</span></span>

<span data-ttu-id="5896e-148">将图像上传到任何 Docker 注册表，如[Azure 容器注册表 (ACR)](https://azure.microsoft.com/services/container-registry/)或 Docker 中心，以便映像可以从该注册表部署到 AKS 群集。</span><span class="sxs-lookup"><span data-stu-id="5896e-148">Upload the image to any Docker registry, like [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) or Docker Hub, so the images can be deployed to the AKS cluster from that registry.</span></span> <span data-ttu-id="5896e-149">在这种情况下，我们正在正在映像上载到 Azure 容器注册表。</span><span class="sxs-lookup"><span data-stu-id="5896e-149">In this case, we’re uploading the image to Azure Container Registry.</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="5896e-150">在发布模式下创建的映像</span><span class="sxs-lookup"><span data-stu-id="5896e-150">Create the image in Release mode</span></span>

<span data-ttu-id="5896e-151">现在，我们将创建中的图像**发行**模式 （可用于生产） 更改为**发行**，如下所示图 4: 41，并像之前那样运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="5896e-151">We'll now create the image in **Release** mode (ready for production) by changing to **Release**, as shown in Figure 4-41, and running the application as we did before.</span></span>

![工具栏在 VS 中的选项以在发布模式下生成。](media/select-release-mode.png)

<span data-ttu-id="5896e-153">**图 4: 41**。</span><span class="sxs-lookup"><span data-stu-id="5896e-153">**Figure 4-41**.</span></span> <span data-ttu-id="5896e-154">选择发布模式下</span><span class="sxs-lookup"><span data-stu-id="5896e-154">Selecting Release Mode</span></span>

<span data-ttu-id="5896e-155">如果您执行`docker image`命令，你将看到这两个映像创建，另一个用于`debug`，另一个用于`release`模式。</span><span class="sxs-lookup"><span data-stu-id="5896e-155">If you execute the `docker image` command, you'll see both images created, one for `debug` and the other for `release` mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="5896e-156">为映像创建新标记</span><span class="sxs-lookup"><span data-stu-id="5896e-156">Create a new Tag for the Image</span></span>

<span data-ttu-id="5896e-157">需要使用标记每个容器映像`loginServer`注册表的名称。</span><span class="sxs-lookup"><span data-stu-id="5896e-157">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="5896e-158">此标记用于路由时将容器映像推送到映像注册表。</span><span class="sxs-lookup"><span data-stu-id="5896e-158">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="5896e-159">您可以查看`loginServer`名称在 Azure 门户中，Azure 容器注册表中提取信息</span><span class="sxs-lookup"><span data-stu-id="5896e-159">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![在右上角的 Azure 容器注册表名称，浏览器视图。](media/loginServer-name.png)

<span data-ttu-id="5896e-161">**图 4-42**。</span><span class="sxs-lookup"><span data-stu-id="5896e-161">**Figure 4-42**.</span></span> <span data-ttu-id="5896e-162">注册表名称的视图</span><span class="sxs-lookup"><span data-stu-id="5896e-162">View of the name of the Registry</span></span>

<span data-ttu-id="5896e-163">或通过运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5896e-163">Or by running the following command:</span></span>

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![控制台输出从上面的命令。](media/az-cli-loginServer-name.png)

<span data-ttu-id="5896e-165">**图 4-43**。</span><span class="sxs-lookup"><span data-stu-id="5896e-165">**Figure 4-43**.</span></span> <span data-ttu-id="5896e-166">获取使用 PowerShell 的注册表的名称</span><span class="sxs-lookup"><span data-stu-id="5896e-166">Get the name of the registry using PowerShell</span></span>

<span data-ttu-id="5896e-167">在这两种情况下，将获取的名称。</span><span class="sxs-lookup"><span data-stu-id="5896e-167">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="5896e-168">在本例中为`mssampleacr.azurecr.io`。</span><span class="sxs-lookup"><span data-stu-id="5896e-168">In our example, `mssampleacr.azurecr.io`.</span></span>

<span data-ttu-id="5896e-169">现在你可以标记该映像，采用最新映像 （版本映像），使用命令：</span><span class="sxs-lookup"><span data-stu-id="5896e-169">Now you can tag the image, taking the latest image (the Release image), with the command:</span></span>

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="5896e-170">运行之后`docker tag`命令，列出与映像`docker images`命令，并且应可以看到具有新的标记的图像。</span><span class="sxs-lookup"><span data-stu-id="5896e-170">After running the `docker tag` command, list the images with the `docker images` command, and you should see the image with the new tag.</span></span>

![控制台输出从 docker images 命令。](media/tagged-docker-images-list.png)

<span data-ttu-id="5896e-172">**图 4-44**。</span><span class="sxs-lookup"><span data-stu-id="5896e-172">**Figure 4-44**.</span></span> <span data-ttu-id="5896e-173">带标记的图像的视图</span><span class="sxs-lookup"><span data-stu-id="5896e-173">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="5896e-174">将映像推送到 Azure ACR</span><span class="sxs-lookup"><span data-stu-id="5896e-174">Push the image into the Azure ACR</span></span>

<span data-ttu-id="5896e-175">将映像推送到 Azure ACR，使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="5896e-175">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="5896e-176">此命令需要一段时间上载图像，但在该过程为您提供反馈。</span><span class="sxs-lookup"><span data-stu-id="5896e-176">This command takes a while uploading the images but gives you feedback in the process.</span></span>

![控制台从 docker push 命令的输出： 显示了每个层的基于字符的进度条。](media/uploading-image-to-acr.png)

<span data-ttu-id="5896e-178">**图 4-45**。</span><span class="sxs-lookup"><span data-stu-id="5896e-178">**Figure 4-45**.</span></span> <span data-ttu-id="5896e-179">将图像上传到 ACR</span><span class="sxs-lookup"><span data-stu-id="5896e-179">Uploading the image to the ACR</span></span>

<span data-ttu-id="5896e-180">如下所示结果过程完成时应显示：</span><span class="sxs-lookup"><span data-stu-id="5896e-180">You can see below the result you should get when the process completes:</span></span>

![控制台输出从 docker push 命令，完成后，显示所有层或多个节点。](media/uploading-docker-images-complete.png)

<span data-ttu-id="5896e-182">**图 4 46**。</span><span class="sxs-lookup"><span data-stu-id="5896e-182">**Figure 4-46**.</span></span> <span data-ttu-id="5896e-183">节点视图</span><span class="sxs-lookup"><span data-stu-id="5896e-183">View of nodes</span></span>

<span data-ttu-id="5896e-184">下一步是将容器部署到 AKS 的 Kubernetes 群集。</span><span class="sxs-lookup"><span data-stu-id="5896e-184">The next step is to deploy your container into your AKS Kubernetes cluster.</span></span> <span data-ttu-id="5896e-185">为此，需要一个文件 (**.yml 文件部署**) 包含以下：</span><span class="sxs-lookup"><span data-stu-id="5896e-185">For that, you need a file (**.yml deploy file**) that contains the following:</span></span>

```yml
apiVersion: apps/v1beta1
kind: Deployment
metadata:
  name: mssamplesbook
spec:
  replicas: 1
  template:
    metadata:
      labels:
        app: mssample-kub-app
    spec:
      containers:
        - mane: mssample-services-app
          image: mssampleacr.azurecr.io/mssampleaksapplication:v1
          ports:
            - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
    name: mssample-kub-app
spec:
  ports:
    - name: http-port
      port: 80
      targetPort: 80
  selector:
    app: mssample-kub-app
  type: LoadBalancer
```

> [!NOTE]
> <span data-ttu-id="5896e-186">使用 Kubernetes 部署的详细信息请参阅： <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span><span class="sxs-lookup"><span data-stu-id="5896e-186">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

<span data-ttu-id="5896e-187">现在您已基本准备好使用部署**Kubectl**，但首先必须获取到 AKS 群集使用此命令的凭据：</span><span class="sxs-lookup"><span data-stu-id="5896e-187">Now you're almost ready to deploy using **Kubectl**, but first you must get the credentials to the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![控制台输出从上面的命令：合并"MSSampleK8Cluster 作为当前上下文中 /root/.kube/config](media/getting-aks-credentials.png)

<span data-ttu-id="5896e-189">**图 4-47**。</span><span class="sxs-lookup"><span data-stu-id="5896e-189">**Figure 4-47**.</span></span> <span data-ttu-id="5896e-190">获取凭据</span><span class="sxs-lookup"><span data-stu-id="5896e-190">getting credentials</span></span>

<span data-ttu-id="5896e-191">然后，使用`kubectl create`命令来启动部署。</span><span class="sxs-lookup"><span data-stu-id="5896e-191">Then, use the `kubectl create` command to launch the deployment.</span></span>

```console
kubectl create -f mssample-deploy.yml
```

![控制台从上面的命令的输出:"mssamplesbook"创建部署。](media/kubectl-create-command.png)

<span data-ttu-id="5896e-194">**图 4-48**。</span><span class="sxs-lookup"><span data-stu-id="5896e-194">**Figure 4-48**.</span></span> <span data-ttu-id="5896e-195">将部署到 Kubernetes</span><span class="sxs-lookup"><span data-stu-id="5896e-195">Deploy to Kubernetes</span></span>

<span data-ttu-id="5896e-196">部署完成后，可以使用你可以使用此命令按时间顺序访问的本地代理来访问 Kubernetes 控制台：</span><span class="sxs-lookup"><span data-stu-id="5896e-196">When the deployment completes, you can access the Kubernetes console with a local proxy that you can temporally access with this command:</span></span>

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

<span data-ttu-id="5896e-197">并访问 url `http://127.0.0.1:8001`。</span><span class="sxs-lookup"><span data-stu-id="5896e-197">And accessing the url `http://127.0.0.1:8001`.</span></span>

![Kubernetes 仪表板，显示部署、 Pod、 副本集和服务的浏览器视图。](media/kubernetes-cluster-information.png)

<span data-ttu-id="5896e-199">**图 4 49**。</span><span class="sxs-lookup"><span data-stu-id="5896e-199">**Figure 4-49**.</span></span> <span data-ttu-id="5896e-200">查看 Kubernetes 群集的信息</span><span class="sxs-lookup"><span data-stu-id="5896e-200">View Kubernetes cluster information</span></span>

<span data-ttu-id="5896e-201">现在可以使用 Linux 容器和 AKS Kubernetes 群集的 Azure 上部署的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5896e-201">Now you have your application deployed on Azure, using a Linux Container, and an AKS Kubernetes Cluster.</span></span> <span data-ttu-id="5896e-202">您可以访问您的应用程序浏览到你的服务，你可以从 Azure 门户获取的公共 IP。</span><span class="sxs-lookup"><span data-stu-id="5896e-202">You can access your app browsing to the public IP of your service, which you can get from the Azure portal.</span></span>

> [!NOTE]
> <span data-ttu-id="5896e-203">您可以了解如何在部分中创建此示例在 AKS 群集[**部署到 Azure Kubernetes 服务 (AKS)** ](deploy-azure-kubernetes-service.md)有关本指南。</span><span class="sxs-lookup"><span data-stu-id="5896e-203">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5896e-204">[上一页](set-up-windows-containers-with-powershell.md)
>[下一页](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="5896e-204">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
