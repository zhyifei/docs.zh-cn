---
title: 构建 ASP.NET Core 2.1 应用程序部署到 AKS/Kubernetes 群集与 Linux 容器
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: b03b6fab9dcd53e97c2bc4d7e5c958ca4b931077
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221458"
---
# <a name="build-aspnet-core-21-applications-deployed-as-linux-containers-into-akskubernetes-orchestrator"></a><span data-ttu-id="706b9-103">构建 ASP.NET Core 2.1 应用程序与 Linux 容器部署到 AKS/Kubernetes 业务流程协调程序</span><span class="sxs-lookup"><span data-stu-id="706b9-103">Build ASP.NET Core 2.1 applications deployed as Linux containers into AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="706b9-104">Azure Kubernetes 服务 (AKS) 是 Azure 的托管的 Kubernetes 业务流程服务可简化容器部署和管理。</span><span class="sxs-lookup"><span data-stu-id="706b9-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="706b9-105">AKS 主要功能如下：</span><span class="sxs-lookup"><span data-stu-id="706b9-105">AKS main features are:</span></span>

- <span data-ttu-id="706b9-106">Azure 托管的控制平面</span><span class="sxs-lookup"><span data-stu-id="706b9-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="706b9-107">自动的升级</span><span class="sxs-lookup"><span data-stu-id="706b9-107">Automated upgrades</span></span>
- <span data-ttu-id="706b9-108">自我修复</span><span class="sxs-lookup"><span data-stu-id="706b9-108">Self-healing</span></span>
- <span data-ttu-id="706b9-109">用户可配置缩放</span><span class="sxs-lookup"><span data-stu-id="706b9-109">User configurable scaling</span></span>
- <span data-ttu-id="706b9-110">简单的用户体验的开发人员和群集操作员。</span><span class="sxs-lookup"><span data-stu-id="706b9-110">A simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="706b9-111">下面的示例探索的 ASP.NET Core 2.1 应用程序在 Linux 上运行并完成开发时，将部署到 AKS 群集在 Azure 中，创建使用 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="706b9-111">The following examples explore the creation of an ASP.NET Core 2.1 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2017.</span></span>

## <a name="creating-the-aspnet-core-21-project-using-visual-studio-2017"></a><span data-ttu-id="706b9-112">创建 ASP.NET Core 2.1 项目使用 Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="706b9-112">Creating the ASP.NET Core 2.1 Project using Visual Studio 2017</span></span>

<span data-ttu-id="706b9-113">ASP.NET Core 是由 Microsoft 和 GitHub 上的.NET 社区维护一个通用开发平台。</span><span class="sxs-lookup"><span data-stu-id="706b9-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="706b9-114">它是跨平台的，支持 Windows、macOS 和 Linux，并且可用于设备、云和嵌入式/IoT 方案。</span><span class="sxs-lookup"><span data-stu-id="706b9-114">It is cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="706b9-115">此示例使用一个简单的项目为基础的基于 Visual Studio Web API 模板，因此您无需任何其他的知识来创建示例。</span><span class="sxs-lookup"><span data-stu-id="706b9-115">This example uses a simple project that's based based on a Visual Studio Web API template, so you don't need any additional knowledge to create the sample.</span></span> <span data-ttu-id="706b9-116">只需使用一个包含所有要使用 REST API，使用 ASP.NET Core 2.1 技术运行一个小的项目的元素的标准模板创建项目。</span><span class="sxs-lookup"><span data-stu-id="706b9-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API, using ASP.NET Core 2.1 technology.</span></span>

![在 Visual Studio 中，选择 ASP.NET Core Web 应用程序中添加新项目窗口。](media/create-aspnet-core-application.png)

<span data-ttu-id="706b9-118">**图 4-36**。</span><span class="sxs-lookup"><span data-stu-id="706b9-118">**Figure 4-36**.</span></span> <span data-ttu-id="706b9-119">创建 ASP.NET Core 应用程序</span><span class="sxs-lookup"><span data-stu-id="706b9-119">Creating ASP.NET Core Application</span></span>

<span data-ttu-id="706b9-120">若要创建示例项目，您必须选择**文件** > **新建** > **项目**上 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="706b9-120">To create the sample project, you have to select **File** > **New** > **Project** on Visual Studio.</span></span> <span data-ttu-id="706b9-121">然后您将看到一系列针对多种类型的项目中，模板需要寻找**Web** > **.NET Core**左侧面板上。</span><span class="sxs-lookup"><span data-stu-id="706b9-121">Then you'll see a list of templates for several types of projects, where you have to look for **Web** > **.NET Core** on the left panel.</span></span> <span data-ttu-id="706b9-122">对于此示例选择**ASP.NET Core Web 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="706b9-122">For this example select **ASP.NET Core Web Application**.</span></span>

<span data-ttu-id="706b9-123">在下一个对话框中确保已选择.NET Core 和 ASP.NET Core 2.1 作为顶级 pulldowns，如图 4-37 中所示中的目标框架，然后选择 API 选项，创建 ASP.NET Core Web API 应用程序。</span><span class="sxs-lookup"><span data-stu-id="706b9-123">In the next dialog ensure that you have selected .NET Core and ASP.NET Core 2.1 as the target framework in the top pulldowns, as shown in figure 4-37, and then select the API option, to create an ASP.NET Core Web API application.</span></span>

<span data-ttu-id="706b9-124">.NET Core 2.1 是包含在 Visual Studio 2017 15.7.0 版或更高版本，会自动安装并配置为你选择时 **.NET Core 跨平台开发**在安装过程中的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="706b9-124">The .NET Core 2.1 is included in Visual Studio 2017 version 15.7.0 or higher and is automatically installed and configured for you when you select the **.NET Core cross-platform development** workload during installation.</span></span>

![Visual Studio 对话框用于选择的 API 选项中选择的 ASP.NET Core Web 应用程序的类型。](media/create-web-api-application.png)

<span data-ttu-id="706b9-126">**图 4 37**。</span><span class="sxs-lookup"><span data-stu-id="706b9-126">**Figure 4-37**.</span></span> <span data-ttu-id="706b9-127">选择 ASP.NET CORE 2.1 和 Web API 项目类型</span><span class="sxs-lookup"><span data-stu-id="706b9-127">Selecting ASP.NET CORE 2.1 and Web API project type</span></span>

<span data-ttu-id="706b9-128">如果有任何以前版本的.NET Core，您可以下载并安装中的 2.1 版本<https://www.microsoft.com/net/download/core#/sdk>。</span><span class="sxs-lookup"><span data-stu-id="706b9-128">If you have any previous version of .NET Core, you can download and install the 2.1 version from <https://www.microsoft.com/net/download/core#/sdk>.</span></span>

<span data-ttu-id="706b9-129">在上一步骤中，或更高版本，如果需要在启动项目后创建项目时，可以添加 Docker 支持。</span><span class="sxs-lookup"><span data-stu-id="706b9-129">You can add Docker support when creating the project in the previous step, or later, if the need arises after starting the project.</span></span> <span data-ttu-id="706b9-130">若要创建项目后添加 Docker 支持，请右键单击项目文件**解决方案资源管理器**，然后选择**添加** > **Docker 支持**上上下文菜单中。</span><span class="sxs-lookup"><span data-stu-id="706b9-130">To add the Docker support after the project creation, right-click on the project file in the **Solution Explorer** and select **Add** > **Docker support** on the context menu.</span></span>

![若要向现有项目添加 Docker 支持的上下文菜单选项：右键单击 （项目） > 添加 > Docker 支持。](media/add-docker-support-to-project.png)

<span data-ttu-id="706b9-132">**图 4-38**。</span><span class="sxs-lookup"><span data-stu-id="706b9-132">**Figure 4-38**.</span></span> <span data-ttu-id="706b9-133">向现有项目添加 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="706b9-133">Adding Docker support to existing project</span></span>

<span data-ttu-id="706b9-134">若要完成添加 Docker 支持，必须选择 Windows 或 Linux。</span><span class="sxs-lookup"><span data-stu-id="706b9-134">To complete adding Docker support, you have the choice of Windows or Linux.</span></span> <span data-ttu-id="706b9-135">在这种情况下，选择**Linux**，这是因为 AKS 不支持 Windows 容器 （作为后期 2018)。</span><span class="sxs-lookup"><span data-stu-id="706b9-135">In this case, select **Linux**, because AKS doesn’t support Windows Containers (as of late 2018).</span></span>

![选项对话框，可选择目标 OS 的 Dockerfile。](media/select-linux-docker-support.png)

<span data-ttu-id="706b9-137">**图 4-39**。</span><span class="sxs-lookup"><span data-stu-id="706b9-137">**Figure 4-39**.</span></span> <span data-ttu-id="706b9-138">选择 Linux 容器。</span><span class="sxs-lookup"><span data-stu-id="706b9-138">Selecting Linux containers.</span></span>

<span data-ttu-id="706b9-139">这些简单的步骤，则必须在 Linux 容器上运行 ASP.NET Core 2.1 应用程序。</span><span class="sxs-lookup"><span data-stu-id="706b9-139">With these simple steps, you will have your ASP.NET Core 2.1 application running on a Linux container.</span></span>

<span data-ttu-id="706b9-140">正如您所看到的 Visual Studio 2017 和 Docker 之间的集成是完全面向开发人员工作效率。</span><span class="sxs-lookup"><span data-stu-id="706b9-140">As you can see, the integration between Visual Studio 2017 and Docker is totally oriented to the developer’s productivity.</span></span>

<span data-ttu-id="706b9-141">现在可以按**F5**生成并运行你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="706b9-141">Now you can press **F5** to build and run your application.</span></span>

<span data-ttu-id="706b9-142">在运行该项目之后, 可以列出使用的映像`docker images`命令。</span><span class="sxs-lookup"><span data-stu-id="706b9-142">After running the project, you can list the images using the `docker images` command.</span></span> <span data-ttu-id="706b9-143">应会看到`mssampleapplication`创建我们的项目使用 Visual Studio 2017 自动部署映像。</span><span class="sxs-lookup"><span data-stu-id="706b9-143">You should see the `mssampleapplication` image created with the automatic deploy of our project with Visual Studio 2017.</span></span>

```console
docker images
```

![控制台输出 docker 映像命令，从显示的列表：存储库、 标记、 映像 ID、 Created （日期） 和大小。](media/docker-images-command.png)

<span data-ttu-id="706b9-145">**图 4-40**。</span><span class="sxs-lookup"><span data-stu-id="706b9-145">**Figure 4-40**.</span></span> <span data-ttu-id="706b9-146">Docker 映像的视图</span><span class="sxs-lookup"><span data-stu-id="706b9-146">View of Docker images</span></span>

## <a name="register-the-solution-in-the-azure-container-registry"></a><span data-ttu-id="706b9-147">在 Azure 容器注册表中注册解决方案</span><span class="sxs-lookup"><span data-stu-id="706b9-147">Register the Solution in the Azure Container Registry</span></span>

<span data-ttu-id="706b9-148">将图像上传到任何 Docker 注册表，如[Azure 容器注册表 (ACR)](https://azure.microsoft.com/services/container-registry/)或 Docker Hub 以便映像可以从该注册表部署到 AKS 群集。</span><span class="sxs-lookup"><span data-stu-id="706b9-148">Upload the image to any Docker registry, like [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) or Docker Hub so the images can be deployed to the AKS cluster from that registry.</span></span> <span data-ttu-id="706b9-149">在这种情况下，我们正在正在映像上载到 Azure 容器注册表。</span><span class="sxs-lookup"><span data-stu-id="706b9-149">In this case, we’re uploading the image to Azure Container Registry.</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="706b9-150">在发布模式下创建的映像</span><span class="sxs-lookup"><span data-stu-id="706b9-150">Create the image in Release mode</span></span>

<span data-ttu-id="706b9-151">创建中的图像**版本**模式 （可用于生产） 切换到版本，如下所示，按 f5 键以运行一次应用程序。</span><span class="sxs-lookup"><span data-stu-id="706b9-151">Create the image in **Release** Mode (ready for production) changing to Release as shown here and press F5 to run the application again.</span></span>

![工具栏在 VS 中的选项以在发布模式下生成。](media/select-release-mode.png)

<span data-ttu-id="706b9-153">**图 4: 41**。</span><span class="sxs-lookup"><span data-stu-id="706b9-153">**Figure 4-41**.</span></span> <span data-ttu-id="706b9-154">选择发布模式下</span><span class="sxs-lookup"><span data-stu-id="706b9-154">Selecting Release Mode</span></span>

<span data-ttu-id="706b9-155">如果您执行`docker image`命令，你将看到创建这两个映像。</span><span class="sxs-lookup"><span data-stu-id="706b9-155">If you execute the `docker image` command, you'll see both images created.</span></span> <span data-ttu-id="706b9-156">一个用于`debug`，另一个用于`release`模式。</span><span class="sxs-lookup"><span data-stu-id="706b9-156">One for `debug` and the other for `release` mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="706b9-157">为映像创建新标记</span><span class="sxs-lookup"><span data-stu-id="706b9-157">Create a new Tag for the Image</span></span>

<span data-ttu-id="706b9-158">需要使用标记每个容器映像`loginServer`注册表的名称。</span><span class="sxs-lookup"><span data-stu-id="706b9-158">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="706b9-159">此标记用于路由时将容器映像推送到映像注册表。</span><span class="sxs-lookup"><span data-stu-id="706b9-159">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="706b9-160">您可以查看`loginServer`名称在 Azure 门户中，Azure 容器注册表中提取信息</span><span class="sxs-lookup"><span data-stu-id="706b9-160">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![在右上角的 Azure 容器注册表名称，浏览器视图。](media/loginServer-name.png)

<span data-ttu-id="706b9-162">**图 4-42**。</span><span class="sxs-lookup"><span data-stu-id="706b9-162">**Figure 4-42**.</span></span> <span data-ttu-id="706b9-163">注册表名称的视图</span><span class="sxs-lookup"><span data-stu-id="706b9-163">View of the name of the Registry</span></span>

<span data-ttu-id="706b9-164">或通过运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="706b9-164">Or by running the following command:</span></span>

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![控制台输出从上面的命令。](media/az-cli-loginServer-name.png)

<span data-ttu-id="706b9-166">**图 4-43**。</span><span class="sxs-lookup"><span data-stu-id="706b9-166">**Figure 4-43**.</span></span> <span data-ttu-id="706b9-167">获取使用 PowerShell 的注册表的名称</span><span class="sxs-lookup"><span data-stu-id="706b9-167">Get the name of the registry using PowerShell</span></span>

<span data-ttu-id="706b9-168">在这两种情况下，将获取的名称。</span><span class="sxs-lookup"><span data-stu-id="706b9-168">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="706b9-169">在本例中为`mssampleacr.azurecr.io`。</span><span class="sxs-lookup"><span data-stu-id="706b9-169">In our example, `mssampleacr.azurecr.io`.</span></span>

<span data-ttu-id="706b9-170">现在你可以标记该映像，采用最新映像 （版本映像），使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="706b9-170">Now you can tag the image, taking the latest image (Release image), with the following command:</span></span>

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="706b9-171">运行之后`docker tag`命令，列出与映像`docker images`命令。</span><span class="sxs-lookup"><span data-stu-id="706b9-171">After running the `docker tag` command, list the images with the `docker images` command.</span></span> <span data-ttu-id="706b9-172">应会看到具有新的标记图像。</span><span class="sxs-lookup"><span data-stu-id="706b9-172">You should see the image with the new tag.</span></span>

![控制台输出从 docker images 命令。](media/tagged-docker-images-list.png)

<span data-ttu-id="706b9-174">**图 4-44**。</span><span class="sxs-lookup"><span data-stu-id="706b9-174">**Figure 4-44**.</span></span> <span data-ttu-id="706b9-175">带标记的图像的视图</span><span class="sxs-lookup"><span data-stu-id="706b9-175">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="706b9-176">将映像推送到 Azure ACR</span><span class="sxs-lookup"><span data-stu-id="706b9-176">Push the image into the Azure ACR</span></span>

<span data-ttu-id="706b9-177">将映像推送到 Azure ACR，使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="706b9-177">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="706b9-178">此命令需要一段时间上载图像，但在该过程为您提供反馈。</span><span class="sxs-lookup"><span data-stu-id="706b9-178">This command takes a while uploading the images but gives you feedback in the process.</span></span>

![控制台从 docker push 命令的输出： 显示了每个层的基于字符的进度条。](media/uploading-image-to-acr.png)

<span data-ttu-id="706b9-180">**图 4-45**。</span><span class="sxs-lookup"><span data-stu-id="706b9-180">**Figure 4-45**.</span></span> <span data-ttu-id="706b9-181">将图像上传到 ACR</span><span class="sxs-lookup"><span data-stu-id="706b9-181">Uploading the image to the ACR</span></span>

<span data-ttu-id="706b9-182">如下所示结果过程完成时应显示：</span><span class="sxs-lookup"><span data-stu-id="706b9-182">You can see below the result you should get when the process completes:</span></span>

![控制台输出从 docker push 命令，完成后，显示所有层或多个节点。](media/uploading-docker-images-complete.png)

<span data-ttu-id="706b9-184">**图 4 46**。</span><span class="sxs-lookup"><span data-stu-id="706b9-184">**Figure 4-46**.</span></span> <span data-ttu-id="706b9-185">节点视图</span><span class="sxs-lookup"><span data-stu-id="706b9-185">View of nodes</span></span>

<span data-ttu-id="706b9-186">下一步是将容器部署到 AKS 的 Kubernetes 群集。</span><span class="sxs-lookup"><span data-stu-id="706b9-186">The next step is to deploy your container into your AKS Kubernetes cluster.</span></span> <span data-ttu-id="706b9-187">为此，您需要一个文件 (**.yml 文件部署**)，在这种情况下，包含：</span><span class="sxs-lookup"><span data-stu-id="706b9-187">For that you need a file (**.yml deploy file**) that, in this case, contains:</span></span>

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
> <span data-ttu-id="706b9-188">使用 Kubernetes 部署的详细信息请参阅： <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span><span class="sxs-lookup"><span data-stu-id="706b9-188">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

<span data-ttu-id="706b9-189">现在您已基本准备好使用部署**Kubectl**，但首先必须获取到 AKS 群集使用此命令的凭据：</span><span class="sxs-lookup"><span data-stu-id="706b9-189">Now you're almost ready to deploy using **Kubectl**, but first you must get the credentials to the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![控制台输出从上面的命令：合并"MSSampleK8Cluster 作为当前上下文中 /root/.kube/config](media/getting-aks-credentials.png)

<span data-ttu-id="706b9-191">**图 4-47**。</span><span class="sxs-lookup"><span data-stu-id="706b9-191">**Figure 4-47**.</span></span> <span data-ttu-id="706b9-192">获取凭据</span><span class="sxs-lookup"><span data-stu-id="706b9-192">getting credentials</span></span>

<span data-ttu-id="706b9-193">然后，使用`kubectl create`命令来启动部署。</span><span class="sxs-lookup"><span data-stu-id="706b9-193">Then, use the `kubectl create` command to launch the deployment.</span></span>

```console
kubectl create -f mssample-deploy.yml
```

![控制台从上面的命令的输出:"mssamplesbook"创建部署。](media/kubectl-create-command.png)

<span data-ttu-id="706b9-196">**图 4-48**。</span><span class="sxs-lookup"><span data-stu-id="706b9-196">**Figure 4-48**.</span></span> <span data-ttu-id="706b9-197">将部署到 Kubernetes</span><span class="sxs-lookup"><span data-stu-id="706b9-197">Deploy to Kubernetes</span></span>

<span data-ttu-id="706b9-198">部署完成后，可以使用你可以使用此命令按时间顺序访问的本地代理来访问 Kubernetes 控制台：</span><span class="sxs-lookup"><span data-stu-id="706b9-198">When the deployment completes, you can access the Kubernetes console with a local proxy that you can temporally access with this command:</span></span>

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

<span data-ttu-id="706b9-199">并访问 url `http://127.0.0.1:8001`。</span><span class="sxs-lookup"><span data-stu-id="706b9-199">And accessing the url `http://127.0.0.1:8001`.</span></span>

![Kubernetes 仪表板，显示部署、 Pod、 副本集和服务的浏览器视图。](media/kubernetes-cluster-information.png)

<span data-ttu-id="706b9-201">**图 4 49**。</span><span class="sxs-lookup"><span data-stu-id="706b9-201">**Figure 4-49**.</span></span> <span data-ttu-id="706b9-202">查看 Kubernetes 群集的信息</span><span class="sxs-lookup"><span data-stu-id="706b9-202">View Kubernetes cluster information</span></span>

<span data-ttu-id="706b9-203">现在可以使用 Linux 容器和 AKS Kubernetes 群集的 Azure 上部署的应用程序。</span><span class="sxs-lookup"><span data-stu-id="706b9-203">Now you have your application deployed on Azure, using a Linux Container, and an AKS Kubernetes Cluster.</span></span> <span data-ttu-id="706b9-204">您可以访问您的应用程序浏览到你的服务，你可以从 Azure 门户获取的公共 IP。</span><span class="sxs-lookup"><span data-stu-id="706b9-204">You can access your app browsing to the public IP of your service, which you can get from the Azure portal.</span></span>

> [!NOTE]
> <span data-ttu-id="706b9-205">您可以了解如何在部分中创建此示例在 AKS 群集[**部署到 Azure Kubernetes 服务 (AKS)** ](deploy-azure-kubernetes-service.md)有关本指南。</span><span class="sxs-lookup"><span data-stu-id="706b9-205">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="706b9-206">[上一页](set-up-windows-containers-with-powershell.md)
>[下一页](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="706b9-206">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
