---
title: .NET Core 应用程序部署
description: 部署 .NET Core 应用程序。
author: rpetrusha
ms.author: ronpet
ms.date: 04/18/2017
ms.openlocfilehash: 27f9260166f7e7899501e1798333b982fb728152
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="net-core-application-deployment"></a><span data-ttu-id="df96a-103">.NET Core 应用程序部署</span><span class="sxs-lookup"><span data-stu-id="df96a-103">.NET Core application deployment</span></span>

<span data-ttu-id="df96a-104">可以为 .NET Core 应用程序创建两种部署：</span><span class="sxs-lookup"><span data-stu-id="df96a-104">You can create two types of deployments for .NET Core applications:</span></span>

- <span data-ttu-id="df96a-105">依赖框架的部署。</span><span class="sxs-lookup"><span data-stu-id="df96a-105">Framework-dependent deployment.</span></span> <span data-ttu-id="df96a-106">顾名思义，依赖框架的部署 (FDD) 依赖目标系统上存在共享系统级版本的 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="df96a-106">As the name implies, framework-dependent deployment (FDD) relies on the presence of a shared system-wide version of .NET Core on the target system.</span></span> <span data-ttu-id="df96a-107">由于已存在 .NET Core，因此应用在 .NET Core 安装程序间也是可移植的。</span><span class="sxs-lookup"><span data-stu-id="df96a-107">Because .NET Core is already present, your app is also portable between installations of .NET Core.</span></span> <span data-ttu-id="df96a-108">应用仅包含其自己的代码和任何位于 .NET Core 库外的第三方依赖项。</span><span class="sxs-lookup"><span data-stu-id="df96a-108">Your app contains only its own code and any third-party dependencies that are outside of the .NET Core libraries.</span></span> <span data-ttu-id="df96a-109">FDD 包含可通过在命令行中使用 [dotnet 实用程序](../tools/dotnet.md)启动的 *.dll* 文件。</span><span class="sxs-lookup"><span data-stu-id="df96a-109">FDDs contain *.dll* files that can be launched by using the [dotnet utility](../tools/dotnet.md) from the command line.</span></span> <span data-ttu-id="df96a-110">例如，`dotnet app.dll` 就可以运行一个名为 `app` 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="df96a-110">For example, `dotnet app.dll` runs an application named `app`.</span></span>

- <span data-ttu-id="df96a-111">独立部署。</span><span class="sxs-lookup"><span data-stu-id="df96a-111">Self-contained deployment.</span></span> <span data-ttu-id="df96a-112">与 FDD 不同，独立部署 (SCD) 不依赖目标系统上存在的共享组件。</span><span class="sxs-lookup"><span data-stu-id="df96a-112">Unlike FDD, a self-contained deployment (SCD) doesn't rely on the presence of shared components on the target system.</span></span> <span data-ttu-id="df96a-113">所有组件（包括 .NET Core 库和 .NET Core 运行时）都包含在应用程序中，并且独立于其他 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="df96a-113">All components, including both the .NET Core libraries and the .NET Core runtime, are included with the application and are isolated from other .NET Core applications.</span></span> <span data-ttu-id="df96a-114">SCD 包括一个可执行文件（如 Windows 平台上名为 `app` 的应用程序的 *app.exe*），它是特定于平台的 .NET Core 主机的重命名版本，还包括一个 .*.dll* 文件（如 *app.dll*），而它是实际的应用程序。</span><span class="sxs-lookup"><span data-stu-id="df96a-114">SCDs include an executable (such as *app.exe* on Windows platforms for an application named `app`), which is  a renamed version of the platform-specific .NET Core host, and a *.dll* file (such as *app.dll*), which is the actual application.</span></span>

## <a name="framework-dependent-deployments-fdd"></a><span data-ttu-id="df96a-115">依赖框架的部署 (FDD)</span><span class="sxs-lookup"><span data-stu-id="df96a-115">Framework-dependent deployments (FDD)</span></span>

<span data-ttu-id="df96a-116">对于 FDD，仅部署应用和任何第三方依赖项。</span><span class="sxs-lookup"><span data-stu-id="df96a-116">For an FDD, you deploy only your app and any third-party dependencies.</span></span> <span data-ttu-id="df96a-117">不需要部署 .NET Core，因为应用将使用目标系统上存在的 .NET Core 版本。</span><span class="sxs-lookup"><span data-stu-id="df96a-117">You don't have to deploy .NET Core, since your app will use the version of .NET Core that's present on the target system.</span></span> <span data-ttu-id="df96a-118">这是 .NET Core 应用的默认部署模型。</span><span class="sxs-lookup"><span data-stu-id="df96a-118">This is the default deployment model for .NET Core apps.</span></span>

### <a name="why-create-a-framework-dependent-deployment"></a><span data-ttu-id="df96a-119">为什么创建依赖框架的部署？</span><span class="sxs-lookup"><span data-stu-id="df96a-119">Why create a framework-dependent deployment?</span></span>

<span data-ttu-id="df96a-120">部署 FDD 具有很多优点：</span><span class="sxs-lookup"><span data-stu-id="df96a-120">Deploying an FDD has a number of advantages:</span></span>

- <span data-ttu-id="df96a-121">不需要提前定义 .NET Core 应用将在其上运行的目标操作系统。</span><span class="sxs-lookup"><span data-stu-id="df96a-121">You don't have to define the target operating systems that your .NET Core app will run on in advance.</span></span> <span data-ttu-id="df96a-122">因为无论什么操作系统，.NET Core 的可执行文件和库都是用通用的 PE 文件格式，因此，无论什么基础操作系统，.NET Core 都可执行应用。</span><span class="sxs-lookup"><span data-stu-id="df96a-122">Because .NET Core uses a common PE file format for executables and libraries regardless of operating system, .NET Core can execute your app regardless of the underlying operating system.</span></span> <span data-ttu-id="df96a-123">有关 PE 文件格式的详细信息，请参阅 [.NET 程序集文件格式](../../standard/assembly-format.md)。</span><span class="sxs-lookup"><span data-stu-id="df96a-123">For more information on the PE file format, see [.NET Assembly File Format](../../standard/assembly-format.md).</span></span>

- <span data-ttu-id="df96a-124">部署包很小。</span><span class="sxs-lookup"><span data-stu-id="df96a-124">The size of your deployment package is small.</span></span> <span data-ttu-id="df96a-125">只需部署应用及其依赖项，而无需部署 .NET Core 本身。</span><span class="sxs-lookup"><span data-stu-id="df96a-125">You only deploy your app and its dependencies, not .NET Core itself.</span></span>

- <span data-ttu-id="df96a-126">许多应用都可使用相同的 .NET Core 安装，从而降低了主机系统上磁盘空间和内存使用量。</span><span class="sxs-lookup"><span data-stu-id="df96a-126">Multiple apps use the same .NET Core installation, which reduces both disk space and memory usage on host systems.</span></span>

<span data-ttu-id="df96a-127">也有几个缺点：</span><span class="sxs-lookup"><span data-stu-id="df96a-127">There are also a few disadvantages:</span></span>

- <span data-ttu-id="df96a-128">仅当主机系统上已安装你设为目标的 .NET Core 版本或更高版本时，应用才能运行。</span><span class="sxs-lookup"><span data-stu-id="df96a-128">Your app can run only if the version of .NET Core that you target, or a later version, is already installed on the host system.</span></span>

- <span data-ttu-id="df96a-129">如果不了解将来版本，.NET Core 运行时和库可能发生更改。</span><span class="sxs-lookup"><span data-stu-id="df96a-129">It's possible for the .NET Core runtime and libraries to change without your knowledge in future releases.</span></span> <span data-ttu-id="df96a-130">在极少数情况下，这可能会更改应用的行为。</span><span class="sxs-lookup"><span data-stu-id="df96a-130">In rare cases, this may change the behavior of your app.</span></span>

## <a name="self-contained-deployments-scd"></a><span data-ttu-id="df96a-131">独立部署 (SCD)</span><span class="sxs-lookup"><span data-stu-id="df96a-131">Self-contained deployments (SCD)</span></span>

<span data-ttu-id="df96a-132">对于独立部署，可以部署应用和所需的第三方依赖项以及生成应用所使用的 .NET Core 版本。</span><span class="sxs-lookup"><span data-stu-id="df96a-132">For a self-contained deployment, you deploy your app and any required third-party dependencies along with the version of .NET Core that you used to build the app.</span></span> <span data-ttu-id="df96a-133">创建 SCD 不包括各种平台上的 [.NET Core 本机依赖项](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md)，因此运行应用前这些依赖项必须已存在。</span><span class="sxs-lookup"><span data-stu-id="df96a-133">Creating an SCD doesn't include the [native dependencies of .NET Core](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) on various platforms, so these must be present before the app runs.</span></span>

<span data-ttu-id="df96a-134">FDD 和 SCD 部署使用单独的主机可执行文件，使你可以使用发布者签名为 SCD 签署主机可执行文件。</span><span class="sxs-lookup"><span data-stu-id="df96a-134">FDD and SCD deployments use separate host executables, so you can sign a host executable for an SCD with your publisher signature.</span></span>

### <a name="why-deploy-a-self-contained-deployment"></a><span data-ttu-id="df96a-135">为什么要部署独立部署？</span><span class="sxs-lookup"><span data-stu-id="df96a-135">Why deploy a self-contained deployment?</span></span>

<span data-ttu-id="df96a-136">部署独立部署主要有两个优点：</span><span class="sxs-lookup"><span data-stu-id="df96a-136">Deploying a Self-contained deployment has two major advantages:</span></span>

- <span data-ttu-id="df96a-137">可以对与应用一起部署的 .NET Core 版本具有单独的控制权。</span><span class="sxs-lookup"><span data-stu-id="df96a-137">You have sole control of the version of .NET Core that is deployed with your app.</span></span> <span data-ttu-id="df96a-138">只有你才能维护 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="df96a-138">.NET Core can be serviced only by you.</span></span>

- <span data-ttu-id="df96a-139">请放心，目标系统可以运行你的 .NET Core 应用，因为你提供的是应用将在其上运行的 .NET Core 版本。</span><span class="sxs-lookup"><span data-stu-id="df96a-139">You can be assured that the target system can run your .NET Core app, since you're providing the version of .NET Core that it will run on.</span></span>

<span data-ttu-id="df96a-140">它也有几个缺点：</span><span class="sxs-lookup"><span data-stu-id="df96a-140">It also has a number of disadvantages:</span></span>

- <span data-ttu-id="df96a-141">由于 .NET Core 包含在部署包中，因此必须提前选择为其生成部署包的目标平台。</span><span class="sxs-lookup"><span data-stu-id="df96a-141">Because .NET Core is included in your deployment package, you must select the target platforms for which you build deployment packages in advance.</span></span>

- <span data-ttu-id="df96a-142">部署包相对较大，因为需要将 .NET Core 和应用及其第三方依赖项包括在内。</span><span class="sxs-lookup"><span data-stu-id="df96a-142">The size of your deployment package is relatively large, since you have to include .NET Core as well as your app and its third-party dependencies.</span></span>

- <span data-ttu-id="df96a-143">向系统部署大量独立的 .NET Core 应用可能会使用大量磁盘空间，因为每个应用都会复制 .NET Core 文件。</span><span class="sxs-lookup"><span data-stu-id="df96a-143">Deploying numerous self-contained .NET Core apps to a system can consume significant amounts of disk space, since each app duplicates .NET Core files.</span></span>

## <a name="step-by-step-examples"></a><span data-ttu-id="df96a-144">分步示例</span><span class="sxs-lookup"><span data-stu-id="df96a-144">Step-by-step examples</span></span>

<span data-ttu-id="df96a-145">有关使用 CLI 工具部署 .NET Core 应用的分步示例，请参阅[使用 CLI 工具部署 .NET Core 应用](deploy-with-cli.md)。</span><span class="sxs-lookup"><span data-stu-id="df96a-145">For step-by-step examples of deploying .NET Core apps with CLI tools, see [Deploying .NET Core Apps with CLI Tools](deploy-with-cli.md).</span></span> <span data-ttu-id="df96a-146">有关使用 Visual Studio 部署 .NET Core 应用的分步示例，请参阅 [使用 Visual Studio 部署 .NET Core 应用](deploy-with-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="df96a-146">For step-by-step examples of deploying .NET Core apps with Visual Studio, see [Deploying .NET Core Apps with Visual Studio](deploy-with-vs.md).</span></span> <span data-ttu-id="df96a-147">每个主题都包括以下部署的示例：</span><span class="sxs-lookup"><span data-stu-id="df96a-147">Each topic includes examples of the following deployments:</span></span>

- <span data-ttu-id="df96a-148">依赖框架的部署</span><span class="sxs-lookup"><span data-stu-id="df96a-148">Framework-dependent deployment</span></span>
- <span data-ttu-id="df96a-149">包含第三方依赖项的依赖框架的部署</span><span class="sxs-lookup"><span data-stu-id="df96a-149">Framework-dependent deployment with third-party dependencies</span></span>
- <span data-ttu-id="df96a-150">独立部署</span><span class="sxs-lookup"><span data-stu-id="df96a-150">Self-contained deployment</span></span>
- <span data-ttu-id="df96a-151">包含第三方依赖项的独立部署</span><span class="sxs-lookup"><span data-stu-id="df96a-151">Self-contained deployment with third-party dependencies</span></span>

# <a name="see-also"></a><span data-ttu-id="df96a-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="df96a-152">See also</span></span>

<span data-ttu-id="df96a-153">[使用 CLI 工具部署 .NET Core 应用](deploy-with-cli.md) </span><span class="sxs-lookup"><span data-stu-id="df96a-153">[Deploying .NET Core Apps with CLI Tools](deploy-with-cli.md) </span></span>  
<span data-ttu-id="df96a-154">[使用 Visual Studio 部署 .NET Core 应用](deploy-with-vs.md) </span><span class="sxs-lookup"><span data-stu-id="df96a-154">[Deploying .NET Core Apps with Visual Studio](deploy-with-vs.md) </span></span>  
<span data-ttu-id="df96a-155">[包、元包和框架](../packages.md) </span><span class="sxs-lookup"><span data-stu-id="df96a-155">[Packages, Metapackages and Frameworks](../packages.md) </span></span>  
[<span data-ttu-id="df96a-156">.NET Core 运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="df96a-156">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
