---
title: 构建作为 Linux 容器部署到 AKS/Kubernetes 群集中的 ASP.NET Core 2.2 应用程序
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
ms.date: 02/25/2019
ms.openlocfilehash: 89843e0041c12f001f974360da2e5903499155d1
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2019
ms.locfileid: "65644786"
---
# <a name="build-aspnet-core-22-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a><span data-ttu-id="145d7-103">构建作为 Linux 容器部署到 AKS/Kubernetes 业务流程协调程序中的 ASP.NET Core 2.2 应用程序</span><span class="sxs-lookup"><span data-stu-id="145d7-103">Build ASP.NET Core 2.2 applications deployed as Linux containers into an AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="145d7-104">Azure Kubernetes 服务 (AKS) 是 Azure 的托管 Kubernetes 业务流程服务，可简化容器部署和管理。</span><span class="sxs-lookup"><span data-stu-id="145d7-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="145d7-105">AKS 主要功能如下：</span><span class="sxs-lookup"><span data-stu-id="145d7-105">AKS main features are:</span></span>

- <span data-ttu-id="145d7-106">Azure 托管的控制面板</span><span class="sxs-lookup"><span data-stu-id="145d7-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="145d7-107">自动升级</span><span class="sxs-lookup"><span data-stu-id="145d7-107">Automated upgrades</span></span>
- <span data-ttu-id="145d7-108">自我修复</span><span class="sxs-lookup"><span data-stu-id="145d7-108">Self-healing</span></span>
- <span data-ttu-id="145d7-109">用户可配置缩放</span><span class="sxs-lookup"><span data-stu-id="145d7-109">User configurable scaling</span></span>
- <span data-ttu-id="145d7-110">针对开发人员和群集操作员提供的更简单的用户体验。</span><span class="sxs-lookup"><span data-stu-id="145d7-110">A simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="145d7-111">以下示例探讨了如何创建在 Linux 上运行并部署到 Azure 中的 AKS 群集的 ASP.NET Core 2.2 应用程序，同时使用 Visual Studio 2017 完成开发。</span><span class="sxs-lookup"><span data-stu-id="145d7-111">The following examples explore the creation of an ASP.NET Core 2.2 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2017.</span></span>

## <a name="creating-the-aspnet-core-22-project-using-visual-studio-2017"></a><span data-ttu-id="145d7-112">使用 Visual Studio 2017 创建 ASP.NET Core 2.2 项目</span><span class="sxs-lookup"><span data-stu-id="145d7-112">Creating the ASP.NET Core 2.2 Project using Visual Studio 2017</span></span>

<span data-ttu-id="145d7-113">ASP.NET Core 是一个通用开发平台，由 Microsoft 和 GitHub 上的 .NET 社区共同维护。</span><span class="sxs-lookup"><span data-stu-id="145d7-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="145d7-114">它跨平台支持 Windows、macOS 和 Linux，并且可用于设备、云和嵌入式/IoT 方案。</span><span class="sxs-lookup"><span data-stu-id="145d7-114">It's cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="145d7-115">此示例使用基于 Visual Studio Web API 模板的简单项目，因此你无需任何其他知识即可创建示例。</span><span class="sxs-lookup"><span data-stu-id="145d7-115">This example uses a simple project that's based on a Visual Studio Web API template, so you don't need any additional knowledge to create the sample.</span></span> <span data-ttu-id="145d7-116">只需使用标准模板创建项目，该模板包含使用 ASP.NET Core 2.2 技术运行带有 REST API 的小项目的所有元素。</span><span class="sxs-lookup"><span data-stu-id="145d7-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API, using ASP.NET Core 2.2 technology.</span></span>

![Visual Studio 中的“添加新项目”窗口，已选择 ASP.NET Core Web 应用。](media/create-aspnet-core-application.png)

<span data-ttu-id="145d7-118">图 4-36  .</span><span class="sxs-lookup"><span data-stu-id="145d7-118">**Figure 4-36**.</span></span> <span data-ttu-id="145d7-119">创建 ASP.NET Core 应用程序</span><span class="sxs-lookup"><span data-stu-id="145d7-119">Creating ASP.NET Core Application</span></span>

<span data-ttu-id="145d7-120">要在 Visual Studio 中创建示例项目，请选择“文件” > “新建” > “项目”，选择左侧窗格中的“Web”项目类型，再选择“ASP.NET Core Web 应用”      。</span><span class="sxs-lookup"><span data-stu-id="145d7-120">To create the sample project in Visual Studio, select **File** > **New** > **Project**, select the **Web** project types in the left pane, followed by **ASP.NET Core Web Application**.</span></span>

<span data-ttu-id="145d7-121">Visual Studio 列出了 Web 项目的模板。</span><span class="sxs-lookup"><span data-stu-id="145d7-121">Visual Studio lists templates for web projects.</span></span> <span data-ttu-id="145d7-122">对于本示例，请选择“API”以创建 ASP.NET Web API 应用程序  。</span><span class="sxs-lookup"><span data-stu-id="145d7-122">For our example, select **API** to create an ASP.NET Web API Application.</span></span>

<span data-ttu-id="145d7-123">验证是否已选择 ASP.NET Core 2.2 作为框架。</span><span class="sxs-lookup"><span data-stu-id="145d7-123">Verify that you've selected ASP.NET Core 2.2 as the framework.</span></span> <span data-ttu-id="145d7-124">.NET Core 2.2 包含在 Visual Studio 2017 的最新版本中，并在安装 Visual Studio 2017 时自动安装和配置。</span><span class="sxs-lookup"><span data-stu-id="145d7-124">.NET Core 2.2 is included in the last version of Visual Studio 2017 and is automatically installed and configured for you when you install Visual Studio 2017.</span></span>

![用于选择 ASP.NET Core Web 应用类型的 Visual Studio 对话框，已选择 API 选项。](media/create-web-api-application.png)

<span data-ttu-id="145d7-126">图 4-37  .</span><span class="sxs-lookup"><span data-stu-id="145d7-126">**Figure 4-37**.</span></span> <span data-ttu-id="145d7-127">选择 ASP.NET Core 2.2 和 Web API 项目类型</span><span class="sxs-lookup"><span data-stu-id="145d7-127">Selecting ASP.NET CORE 2.2 and Web API project type</span></span>

<span data-ttu-id="145d7-128">如果有任何以前版本的 .NET Core，则可以从 <https://www.microsoft.com/net/download/core#/sdk> 下载并安装 2.2 版本。</span><span class="sxs-lookup"><span data-stu-id="145d7-128">If you have any previous version of .NET Core, you can download and install the 2.2 version from <https://www.microsoft.com/net/download/core#/sdk>.</span></span>

<span data-ttu-id="145d7-129">可以在创建项目时或之后添加 Docker 支持，以便能够随时“Docker 化”项目。</span><span class="sxs-lookup"><span data-stu-id="145d7-129">You can add Docker support when creating the project or afterwards, so you can "Dockerize" your project at any time.</span></span> <span data-ttu-id="145d7-130">若要在创建项目后添加 Docker 支持，请在解决方案资源管理器中右键单击项目节点，然后在上下文菜单中选择“添加” > “Docker 支持”   。</span><span class="sxs-lookup"><span data-stu-id="145d7-130">To add Docker support after project creation, right-click on the project node in Solution Explorer and select **Add** > **Docker support** on the context menu.</span></span>

![用于向现有项目添加 Docker 支持的上下文菜单选项：右键单击（在项目上）>“添加”>“Docker 支持”。](media/add-docker-support-to-project.png)

<span data-ttu-id="145d7-132">图 4-38  .</span><span class="sxs-lookup"><span data-stu-id="145d7-132">**Figure 4-38**.</span></span> <span data-ttu-id="145d7-133">向现有项目添加 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="145d7-133">Adding Docker support to existing project</span></span>

<span data-ttu-id="145d7-134">若要完成添加 Docker 支持，可以选择 Windows 或 Linux。</span><span class="sxs-lookup"><span data-stu-id="145d7-134">To complete adding Docker support, you can choose Windows or Linux.</span></span> <span data-ttu-id="145d7-135">在此情况下，选择“Linux”，因为 AKS 不支持 Windows 容器（自 2018 年末起）  。</span><span class="sxs-lookup"><span data-stu-id="145d7-135">In this case, select **Linux**, because AKS doesn’t support Windows Containers (as of late 2018).</span></span>

![为 Dockerfile 选择目标操作系统的选项对话框。](media/select-linux-docker-support.png)

<span data-ttu-id="145d7-137">图 4-39  .</span><span class="sxs-lookup"><span data-stu-id="145d7-137">**Figure 4-39**.</span></span> <span data-ttu-id="145d7-138">选择 Linux 容器。</span><span class="sxs-lookup"><span data-stu-id="145d7-138">Selecting Linux containers.</span></span>

<span data-ttu-id="145d7-139">你已使用这些简单步骤在 Linux 容器上运行 ASP.NET Core 2.2 应用程序。</span><span class="sxs-lookup"><span data-stu-id="145d7-139">With these simple steps, you have your ASP.NET Core 2.2 application running on a Linux container.</span></span>

<span data-ttu-id="145d7-140">如你所见，Visual Studio 2017 与 Docker 之间的集成完全面向开发人员的工作效率。</span><span class="sxs-lookup"><span data-stu-id="145d7-140">As you can see, the integration between Visual Studio 2017 and Docker is totally oriented to the developer’s productivity.</span></span>

<span data-ttu-id="145d7-141">现在，可以使用“F5”键或使用“开始”按钮运行应用程序   。</span><span class="sxs-lookup"><span data-stu-id="145d7-141">Now you can run your application with the **F5** key or by using the **Play** button.</span></span>

<span data-ttu-id="145d7-142">运行项目后，可以使用 `docker images` 命令列出映像。</span><span class="sxs-lookup"><span data-stu-id="145d7-142">After running the project, you can list the images using the `docker images` command.</span></span> <span data-ttu-id="145d7-143">应看到使用 Visual Studio 2017 自动部署项目所创建的 `mssampleapplication` 映像。</span><span class="sxs-lookup"><span data-stu-id="145d7-143">You should see the `mssampleapplication` image created by the automatic deployment of our project with Visual Studio 2017.</span></span>

```console
docker images
```

![来自 Docker 映像命令的控制台输出，显示了一个包含以下内容的列表：存储库、标记、映像 ID、创建（日期）和大小。](media/docker-images-command.png)

<span data-ttu-id="145d7-145">图 4-40  .</span><span class="sxs-lookup"><span data-stu-id="145d7-145">**Figure 4-40**.</span></span> <span data-ttu-id="145d7-146">Docker 映像视图</span><span class="sxs-lookup"><span data-stu-id="145d7-146">View of Docker images</span></span>

## <a name="register-the-solution-in-the-azure-container-registry"></a><span data-ttu-id="145d7-147">在 Azure 容器注册表中注册解决方案</span><span class="sxs-lookup"><span data-stu-id="145d7-147">Register the Solution in the Azure Container Registry</span></span>

<span data-ttu-id="145d7-148">将映像上传到任何 Docker 注册表，如 [Azure 容器注册表 (ACR)](https://azure.microsoft.com/services/container-registry/) 或 Docker Hub，以便能够从该注册表将映像部署到 AKS 群集。</span><span class="sxs-lookup"><span data-stu-id="145d7-148">Upload the image to any Docker registry, like [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) or Docker Hub, so the images can be deployed to the AKS cluster from that registry.</span></span> <span data-ttu-id="145d7-149">在此情况下，我们将映像上传到 Azure 容器注册表。</span><span class="sxs-lookup"><span data-stu-id="145d7-149">In this case, we’re uploading the image to Azure Container Registry.</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="145d7-150">在发布模式下创建映像</span><span class="sxs-lookup"><span data-stu-id="145d7-150">Create the image in Release mode</span></span>

<span data-ttu-id="145d7-151">现在，我们将通过更改为“发布”，在“发布”模式（准备生产）中创建映像，如图 4-41 所示，并像以前一样运行应用程序   。</span><span class="sxs-lookup"><span data-stu-id="145d7-151">We'll now create the image in **Release** mode (ready for production) by changing to **Release**, as shown in Figure 4-41, and running the application as we did before.</span></span>

![VS 中的工具栏选项，用于在发布模式下生成。](media/select-release-mode.png)

<span data-ttu-id="145d7-153">图 4-41  .</span><span class="sxs-lookup"><span data-stu-id="145d7-153">**Figure 4-41**.</span></span> <span data-ttu-id="145d7-154">选择发布模式</span><span class="sxs-lookup"><span data-stu-id="145d7-154">Selecting Release Mode</span></span>

<span data-ttu-id="145d7-155">如果执行 `docker image` 命令，将看到已创建两个映像，一个用于 `debug` 模式，另一个用于 `release` 模式。</span><span class="sxs-lookup"><span data-stu-id="145d7-155">If you execute the `docker image` command, you'll see both images created, one for `debug` and the other for `release` mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="145d7-156">为映像创建新标记</span><span class="sxs-lookup"><span data-stu-id="145d7-156">Create a new Tag for the Image</span></span>

<span data-ttu-id="145d7-157">需要使用注册表的 `loginServer` 名称标记每个容器映像。</span><span class="sxs-lookup"><span data-stu-id="145d7-157">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="145d7-158">在将容器映像推送到映像注册表时，使用此标记进行路由。</span><span class="sxs-lookup"><span data-stu-id="145d7-158">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="145d7-159">可以从 Azure 门户中查看 `loginServer` 名称，从 Azure 容器注册表中获取信息</span><span class="sxs-lookup"><span data-stu-id="145d7-159">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![位于右上角的 Azure 容器注册表名称的浏览器视图。](media/loginServer-name.png)

<span data-ttu-id="145d7-161">图 4-42  .</span><span class="sxs-lookup"><span data-stu-id="145d7-161">**Figure 4-42**.</span></span> <span data-ttu-id="145d7-162">注册表名称的视图</span><span class="sxs-lookup"><span data-stu-id="145d7-162">View of the name of the Registry</span></span>

<span data-ttu-id="145d7-163">或者通过运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="145d7-163">Or by running the following command:</span></span>

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![来自上述命令的控制台输出。](media/az-cli-loginServer-name.png)

<span data-ttu-id="145d7-165">图 4-43  .</span><span class="sxs-lookup"><span data-stu-id="145d7-165">**Figure 4-43**.</span></span> <span data-ttu-id="145d7-166">使用 PowerShell 获取注册表的名称</span><span class="sxs-lookup"><span data-stu-id="145d7-166">Get the name of the registry using PowerShell</span></span>

<span data-ttu-id="145d7-167">这两种情况都可获得名称。</span><span class="sxs-lookup"><span data-stu-id="145d7-167">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="145d7-168">在本示例中，为 `mssampleacr.azurecr.io`。</span><span class="sxs-lookup"><span data-stu-id="145d7-168">In our example, `mssampleacr.azurecr.io`.</span></span>

<span data-ttu-id="145d7-169">现在，可以使用以下命令标记映像，获取最新映像（发布映像）：</span><span class="sxs-lookup"><span data-stu-id="145d7-169">Now you can tag the image, taking the latest image (the Release image), with the command:</span></span>

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="145d7-170">运行 `docker tag` 命令后，使用 `docker images` 命令列出映像，你应看到带有新标记的映像。</span><span class="sxs-lookup"><span data-stu-id="145d7-170">After running the `docker tag` command, list the images with the `docker images` command, and you should see the image with the new tag.</span></span>

![来自 Docker 映像命令的控制台输出。](media/tagged-docker-images-list.png)

<span data-ttu-id="145d7-172">图 4-44  .</span><span class="sxs-lookup"><span data-stu-id="145d7-172">**Figure 4-44**.</span></span> <span data-ttu-id="145d7-173">带标记的映像视图</span><span class="sxs-lookup"><span data-stu-id="145d7-173">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="145d7-174">将映像推送到 Azure ACR</span><span class="sxs-lookup"><span data-stu-id="145d7-174">Push the image into the Azure ACR</span></span>

<span data-ttu-id="145d7-175">登录到 Azure 容器注册表</span><span class="sxs-lookup"><span data-stu-id="145d7-175">Log in to the Azure Container Registry</span></span>

```console
az acr login --name mssampleacr
```

<span data-ttu-id="145d7-176">使用以下命令将映像推送到 Azure ACR：</span><span class="sxs-lookup"><span data-stu-id="145d7-176">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="145d7-177">此命令需要一段时间上传映像，但会在此过程中为你提供反馈。</span><span class="sxs-lookup"><span data-stu-id="145d7-177">This command takes a while uploading the images but gives you feedback in the process.</span></span>

![来自 Docker 推送命令的控制台输出：显示每个层的基于字符的进度栏。](media/uploading-image-to-acr.png)

<span data-ttu-id="145d7-179">图 4-45  .</span><span class="sxs-lookup"><span data-stu-id="145d7-179">**Figure 4-45**.</span></span> <span data-ttu-id="145d7-180">将映像上传到 ACR</span><span class="sxs-lookup"><span data-stu-id="145d7-180">Uploading the image to the ACR</span></span>

<span data-ttu-id="145d7-181">可以在下面看到流程完成时应获得的结果：</span><span class="sxs-lookup"><span data-stu-id="145d7-181">You can see below the result you should get when the process completes:</span></span>

![来自 Docker 推送命令的已完成的控制台输出，显示了所有层或节点。](media/uploading-docker-images-complete.png)

<span data-ttu-id="145d7-183">图 4-46  .</span><span class="sxs-lookup"><span data-stu-id="145d7-183">**Figure 4-46**.</span></span> <span data-ttu-id="145d7-184">节点视图</span><span class="sxs-lookup"><span data-stu-id="145d7-184">View of nodes</span></span>

<span data-ttu-id="145d7-185">下一步是将容器部署到 AKS Kubernetes 群集中。</span><span class="sxs-lookup"><span data-stu-id="145d7-185">The next step is to deploy your container into your AKS Kubernetes cluster.</span></span> <span data-ttu-id="145d7-186">为此，需要一个包含以下内容的文件（.yml 部署文件）  ：</span><span class="sxs-lookup"><span data-stu-id="145d7-186">For that, you need a file (**.yml deploy file**) that contains the following:</span></span>

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
        - name: mssample-services-app
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
> <span data-ttu-id="145d7-187">有关使用 Kubernetes 进行部署的更多信息，请参阅：<https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span><span class="sxs-lookup"><span data-stu-id="145d7-187">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

<span data-ttu-id="145d7-188">现已准备好使用 Kubectl 进行部署，但首先必须使用以下命令获取 AKS 群集的凭据  ：</span><span class="sxs-lookup"><span data-stu-id="145d7-188">Now you're almost ready to deploy using **Kubectl**, but first you must get the credentials to the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![来自上述命令的控制台输出：Merged "MSSampleK8Cluster as current context in  /root/.kube/config](media/getting-aks-credentials.png)

<span data-ttu-id="145d7-190">图 4-47  .</span><span class="sxs-lookup"><span data-stu-id="145d7-190">**Figure 4-47**.</span></span> <span data-ttu-id="145d7-191">获取凭据</span><span class="sxs-lookup"><span data-stu-id="145d7-191">getting credentials</span></span>

<span data-ttu-id="145d7-192">然后，使用 `kubectl create` 命令启动部署。</span><span class="sxs-lookup"><span data-stu-id="145d7-192">Then, use the `kubectl create` command to launch the deployment.</span></span>

```console
kubectl create -f mssample-deploy.yml
```

![来自上述命令的控制台输出：已创建部署“mssamplesbook”。](media/kubectl-create-command.png)

<span data-ttu-id="145d7-195">图 4-48  .</span><span class="sxs-lookup"><span data-stu-id="145d7-195">**Figure 4-48**.</span></span> <span data-ttu-id="145d7-196">部署到 Kubernetes</span><span class="sxs-lookup"><span data-stu-id="145d7-196">Deploy to Kubernetes</span></span>

<span data-ttu-id="145d7-197">部署完成后，可以使用可使用以下命令暂时访问的本地代理访问 Kubernetes 控制台：</span><span class="sxs-lookup"><span data-stu-id="145d7-197">When the deployment completes, you can access the Kubernetes console with a local proxy that you can temporally access with this command:</span></span>

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

<span data-ttu-id="145d7-198">并访问 url `http://127.0.0.1:8001`。</span><span class="sxs-lookup"><span data-stu-id="145d7-198">And accessing the url `http://127.0.0.1:8001`.</span></span>

![Kubernetes 仪表板的浏览器视图，显示了部署、Pod、副本集和服务。](media/kubernetes-cluster-information.png)

<span data-ttu-id="145d7-200">图 4-49  .</span><span class="sxs-lookup"><span data-stu-id="145d7-200">**Figure 4-49**.</span></span> <span data-ttu-id="145d7-201">查看 Kubernetes 群集信息</span><span class="sxs-lookup"><span data-stu-id="145d7-201">View Kubernetes cluster information</span></span>

<span data-ttu-id="145d7-202">现在，你已使用 Linux 容器和 AKS Kubernetes 群集在 Azure 上部署应用程序。</span><span class="sxs-lookup"><span data-stu-id="145d7-202">Now you have your application deployed on Azure, using a Linux Container, and an AKS Kubernetes Cluster.</span></span> <span data-ttu-id="145d7-203">可访问应用，浏览到可从 Azure 门户获取的服务的公共 IP。</span><span class="sxs-lookup"><span data-stu-id="145d7-203">You can access your app browsing to the public IP of your service, which you can get from the Azure portal.</span></span>

> [!NOTE]
> <span data-ttu-id="145d7-204">可在本指南的[部署到 Azure Kubernetes 服务 (AKS)](deploy-azure-kubernetes-service.md) 部分中了解如何为此示例创建 AKS 群集  。</span><span class="sxs-lookup"><span data-stu-id="145d7-204">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="145d7-205">[上一页](set-up-windows-containers-with-powershell.md)
>[下一页](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="145d7-205">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
