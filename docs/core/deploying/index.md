---
title: .NET Core 应用程序部署
description: 部署 .NET Core 应用程序。
author: rpetrusha
ms.author: ronpet
ms.date: 09/03/2018
ms.openlocfilehash: 2ef63ebd737739b2c8e671d982c3844135689ab4
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44185644"
---
# <a name="net-core-application-deployment"></a><span data-ttu-id="98420-103">.NET Core 应用程序部署</span><span class="sxs-lookup"><span data-stu-id="98420-103">.NET Core application deployment</span></span>

<span data-ttu-id="98420-104">可以为 .NET Core 应用程序创建两种部署：</span><span class="sxs-lookup"><span data-stu-id="98420-104">You can create two types of deployments for .NET Core applications:</span></span>

- <span data-ttu-id="98420-105">依赖框架的部署。</span><span class="sxs-lookup"><span data-stu-id="98420-105">Framework-dependent deployment.</span></span> <span data-ttu-id="98420-106">顾名思义，依赖框架的部署 (FDD) 依赖目标系统上存在共享系统级版本的 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="98420-106">As the name implies, framework-dependent deployment (FDD) relies on the presence of a shared system-wide version of .NET Core on the target system.</span></span> <span data-ttu-id="98420-107">由于已存在 .NET Core，因此应用在 .NET Core 安装程序间也是可移植的。</span><span class="sxs-lookup"><span data-stu-id="98420-107">Because .NET Core is already present, your app is also portable between installations of .NET Core.</span></span> <span data-ttu-id="98420-108">应用仅包含其自己的代码和任何位于 .NET Core 库外的第三方依赖项。</span><span class="sxs-lookup"><span data-stu-id="98420-108">Your app contains only its own code and any third-party dependencies that are outside of the .NET Core libraries.</span></span> <span data-ttu-id="98420-109">FDD 包含可通过在命令行中使用 [dotnet 实用程序](../tools/dotnet.md)启动的 *.dll* 文件。</span><span class="sxs-lookup"><span data-stu-id="98420-109">FDDs contain *.dll* files that can be launched by using the [dotnet utility](../tools/dotnet.md) from the command line.</span></span> <span data-ttu-id="98420-110">例如，`dotnet app.dll` 就可以运行一个名为 `app` 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="98420-110">For example, `dotnet app.dll` runs an application named `app`.</span></span>

- <span data-ttu-id="98420-111">独立部署。</span><span class="sxs-lookup"><span data-stu-id="98420-111">Self-contained deployment.</span></span> <span data-ttu-id="98420-112">与 FDD 不同，独立部署 (SCD) 不依赖目标系统上存在的共享组件。</span><span class="sxs-lookup"><span data-stu-id="98420-112">Unlike FDD, a self-contained deployment (SCD) doesn't rely on the presence of shared components on the target system.</span></span> <span data-ttu-id="98420-113">所有组件（包括 .NET Core 库和 .NET Core 运行时）都包含在应用程序中，并且独立于其他 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="98420-113">All components, including both the .NET Core libraries and the .NET Core runtime, are included with the application and are isolated from other .NET Core applications.</span></span> <span data-ttu-id="98420-114">SCD 包括一个可执行文件（如 Windows 平台上名为 `app` 的应用程序的 *app.exe*），它是特定于平台的 .NET Core 主机的重命名版本，还包括一个 .*.dll* 文件（如 *app.dll*），而它是实际的应用程序。</span><span class="sxs-lookup"><span data-stu-id="98420-114">SCDs include an executable (such as *app.exe* on Windows platforms for an application named `app`), which is  a renamed version of the platform-specific .NET Core host, and a *.dll* file (such as *app.dll*), which is the actual application.</span></span>

## <a name="framework-dependent-deployments-fdd"></a><span data-ttu-id="98420-115">依赖框架的部署 (FDD)</span><span class="sxs-lookup"><span data-stu-id="98420-115">Framework-dependent deployments (FDD)</span></span>

<span data-ttu-id="98420-116">对于 FDD，仅部署应用程序和第三方依赖项。</span><span class="sxs-lookup"><span data-stu-id="98420-116">For an FDD, you deploy only your app and third-party dependencies.</span></span> <span data-ttu-id="98420-117">不需要部署 .NET Core，因为应用将使用目标系统上存在的 .NET Core 版本。</span><span class="sxs-lookup"><span data-stu-id="98420-117">You don't have to deploy .NET Core, since your app will use the version of .NET Core that's present on the target system.</span></span> <span data-ttu-id="98420-118">这是定目标到 .NET Core 的 .NET Core 和 ASP.NET Core 应用程序的默认部署模型。</span><span class="sxs-lookup"><span data-stu-id="98420-118">This is the default deployment model for .NET Core and ASP.NET Core apps that target .NET Core.</span></span>

### <a name="why-create-a-framework-dependent-deployment"></a><span data-ttu-id="98420-119">为什么创建依赖框架的部署？</span><span class="sxs-lookup"><span data-stu-id="98420-119">Why create a framework-dependent deployment?</span></span>

<span data-ttu-id="98420-120">部署 FDD 具有很多优点：</span><span class="sxs-lookup"><span data-stu-id="98420-120">Deploying an FDD has a number of advantages:</span></span>

- <span data-ttu-id="98420-121">不需要提前定义 .NET Core 应用将在其上运行的目标操作系统。</span><span class="sxs-lookup"><span data-stu-id="98420-121">You don't have to define the target operating systems that your .NET Core app will run on in advance.</span></span> <span data-ttu-id="98420-122">因为无论什么操作系统，.NET Core 的可执行文件和库都是用通用的 PE 文件格式，因此，无论什么基础操作系统，.NET Core 都可执行应用。</span><span class="sxs-lookup"><span data-stu-id="98420-122">Because .NET Core uses a common PE file format for executables and libraries regardless of operating system, .NET Core can execute your app regardless of the underlying operating system.</span></span> <span data-ttu-id="98420-123">有关 PE 文件格式的详细信息，请参阅 [.NET 程序集文件格式](../../standard/assembly-format.md)。</span><span class="sxs-lookup"><span data-stu-id="98420-123">For more information on the PE file format, see [.NET Assembly File Format](../../standard/assembly-format.md).</span></span>

- <span data-ttu-id="98420-124">部署包很小。</span><span class="sxs-lookup"><span data-stu-id="98420-124">The size of your deployment package is small.</span></span> <span data-ttu-id="98420-125">只需部署应用及其依赖项，而无需部署 .NET Core 本身。</span><span class="sxs-lookup"><span data-stu-id="98420-125">You only deploy your app and its dependencies, not .NET Core itself.</span></span>

- <span data-ttu-id="98420-126">许多应用都可使用相同的 .NET Core 安装，从而降低了主机系统上磁盘空间和内存使用量。</span><span class="sxs-lookup"><span data-stu-id="98420-126">Multiple apps use the same .NET Core installation, which reduces both disk space and memory usage on host systems.</span></span>

<span data-ttu-id="98420-127">也有几个缺点：</span><span class="sxs-lookup"><span data-stu-id="98420-127">There are also a few disadvantages:</span></span>

- <span data-ttu-id="98420-128">仅当主机系统上已安装你设为目标的 .NET Core 版本或更高版本时，应用才能运行。</span><span class="sxs-lookup"><span data-stu-id="98420-128">Your app can run only if the version of .NET Core that you target, or a later version, is already installed on the host system.</span></span>

- <span data-ttu-id="98420-129">如果不了解将来版本，.NET Core 运行时和库可能发生更改。</span><span class="sxs-lookup"><span data-stu-id="98420-129">It's possible for the .NET Core runtime and libraries to change without your knowledge in future releases.</span></span> <span data-ttu-id="98420-130">在极少数情况下，这可能会更改应用的行为。</span><span class="sxs-lookup"><span data-stu-id="98420-130">In rare cases, this may change the behavior of your app.</span></span>

## <a name="self-contained-deployments-scd"></a><span data-ttu-id="98420-131">独立部署 (SCD)</span><span class="sxs-lookup"><span data-stu-id="98420-131">Self-contained deployments (SCD)</span></span>

<span data-ttu-id="98420-132">对于独立部署，可以部署应用和所需的第三方依赖项以及生成应用所使用的 .NET Core 版本。</span><span class="sxs-lookup"><span data-stu-id="98420-132">For a self-contained deployment, you deploy your app and any required third-party dependencies along with the version of .NET Core that you used to build the app.</span></span> <span data-ttu-id="98420-133">创建 SCD 不包括各种平台上的 [.NET Core 本机依赖项](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md)，因此运行应用前这些依赖项必须已存在。</span><span class="sxs-lookup"><span data-stu-id="98420-133">Creating an SCD doesn't include the [native dependencies of .NET Core](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) on various platforms, so these must be present before the app runs.</span></span> <span data-ttu-id="98420-134">有关在运行时进行版本绑定的详细信息，请参阅有关 [.NET Core 中的版本绑定](../versions/selection.md)的文章。</span><span class="sxs-lookup"><span data-stu-id="98420-134">For more information on version binding at runtime, see the article on [version binding in .NET Core](../versions/selection.md).</span></span>

<span data-ttu-id="98420-135">从 NET Core 2.1 SDK（版本 2.1.300）开始，.NET Core 支持修补程序版本前滚。</span><span class="sxs-lookup"><span data-stu-id="98420-135">Starting with NET Core 2.1 SDK (version 2.1.300), .NET Core supports *patch version roll forward*.</span></span> <span data-ttu-id="98420-136">在创建独立部署时，.NET Core 工具会自动包含你的应用程序所指向的 .NET Core 版本的最新服务的运行时。</span><span class="sxs-lookup"><span data-stu-id="98420-136">When you create a self-contained deployment, .NET Core tools automatically include the latest serviced runtime of the .NET Core version that your application targets.</span></span> <span data-ttu-id="98420-137">（最新服务的运行时包括安全修补程序和其他 bug 修复程序。）服务的运行时不需要存在于你的生成系统上；它会从 NuGet.org 自动下载。有关详细信息，包括有关如何选择退出修补程序版本前滚的说明，请参阅[独立部署运行时前滚](runtime-patch-selection.md)。</span><span class="sxs-lookup"><span data-stu-id="98420-137">(The latest serviced runtime includes security patches and other bug fixes.) The serviced runtime does not have to be present on your build system; it is downloaded automatically from NuGet.org. For more information, including instructions on how to opt out of patch version roll forward, see [Self-contained deployment runtime roll forward](runtime-patch-selection.md).</span></span>

<span data-ttu-id="98420-138">FDD 和 SCD 部署使用单独的主机可执行文件，使你可以使用发布者签名为 SCD 签署主机可执行文件。</span><span class="sxs-lookup"><span data-stu-id="98420-138">FDD and SCD deployments use separate host executables, so you can sign a host executable for an SCD with your publisher signature.</span></span>

### <a name="why-deploy-a-self-contained-deployment"></a><span data-ttu-id="98420-139">为什么要部署独立部署？</span><span class="sxs-lookup"><span data-stu-id="98420-139">Why deploy a self-contained deployment?</span></span>

<span data-ttu-id="98420-140">部署独立部署主要有两个优点：</span><span class="sxs-lookup"><span data-stu-id="98420-140">Deploying a Self-contained deployment has two major advantages:</span></span>

- <span data-ttu-id="98420-141">可以对与应用一起部署的 .NET Core 版本具有单独的控制权。</span><span class="sxs-lookup"><span data-stu-id="98420-141">You have sole control of the version of .NET Core that is deployed with your app.</span></span> <span data-ttu-id="98420-142">只有你才能维护 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="98420-142">.NET Core can be serviced only by you.</span></span>

- <span data-ttu-id="98420-143">请放心，目标系统可以运行你的 .NET Core 应用，因为你提供的是应用将在其上运行的 .NET Core 版本。</span><span class="sxs-lookup"><span data-stu-id="98420-143">You can be assured that the target system can run your .NET Core app, since you're providing the version of .NET Core that it will run on.</span></span>

<span data-ttu-id="98420-144">它也有几个缺点：</span><span class="sxs-lookup"><span data-stu-id="98420-144">It also has a number of disadvantages:</span></span>

- <span data-ttu-id="98420-145">由于 .NET Core 包含在部署包中，因此必须提前选择为其生成部署包的目标平台。</span><span class="sxs-lookup"><span data-stu-id="98420-145">Because .NET Core is included in your deployment package, you must select the target platforms for which you build deployment packages in advance.</span></span>

- <span data-ttu-id="98420-146">部署包相对较大，因为需要将 .NET Core 和应用及其第三方依赖项包括在内。</span><span class="sxs-lookup"><span data-stu-id="98420-146">The size of your deployment package is relatively large, since you have to include .NET Core as well as your app and its third-party dependencies.</span></span>

  <span data-ttu-id="98420-147">从.NET Core 2.0 开始，可以通过使用 .NET Core [*全球化固定模式*](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md)在 Linux 系统上减少大约 28 MB 的部署大小。</span><span class="sxs-lookup"><span data-stu-id="98420-147">Starting with .NET Core 2.0, you can reduce the size of your deployment on Linux systems by approximately 28 MB by using .NET Core [*globalization invariant mode*](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md).</span></span> <span data-ttu-id="98420-148">通常，Linux 上的 .NET Core 依赖于 [ICU 库](https://github.com/dotnet/docs/issues/http%22//icu-project.org)来实现全球化支持。</span><span class="sxs-lookup"><span data-stu-id="98420-148">Ordinarily, .NET Core on Linux relies on the [ICU libraries](https://github.com/dotnet/docs/issues/http%22//icu-project.org) for globalization support.</span></span> <span data-ttu-id="98420-149">在固定模式下，库不包含在部署中，并且所有区域性的行为均类似于[固定区域性](xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType)。</span><span class="sxs-lookup"><span data-stu-id="98420-149">In invariant mode, the libraries are not included with your deployment, and all cultures behave like the [invariannt culture](xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType).</span></span>

- <span data-ttu-id="98420-150">向系统部署大量独立的 .NET Core 应用可能会使用大量磁盘空间，因为每个应用都会复制 .NET Core 文件。</span><span class="sxs-lookup"><span data-stu-id="98420-150">Deploying numerous self-contained .NET Core apps to a system can consume significant amounts of disk space, since each app duplicates .NET Core files.</span></span>

## <a name="step-by-step-examples"></a><span data-ttu-id="98420-151">分步示例</span><span class="sxs-lookup"><span data-stu-id="98420-151">Step-by-step examples</span></span>

<span data-ttu-id="98420-152">有关使用 CLI 工具部署 .NET Core 应用的分步示例，请参阅[使用 CLI 工具部署 .NET Core 应用](deploy-with-cli.md)。</span><span class="sxs-lookup"><span data-stu-id="98420-152">For step-by-step examples of deploying .NET Core apps with CLI tools, see [Deploying .NET Core Apps with CLI Tools](deploy-with-cli.md).</span></span> <span data-ttu-id="98420-153">有关使用 Visual Studio 部署 .NET Core 应用的分步示例，请参阅 [使用 Visual Studio 部署 .NET Core 应用](deploy-with-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="98420-153">For step-by-step examples of deploying .NET Core apps with Visual Studio, see [Deploying .NET Core Apps with Visual Studio](deploy-with-vs.md).</span></span> <span data-ttu-id="98420-154">每个主题都包括以下部署的示例：</span><span class="sxs-lookup"><span data-stu-id="98420-154">Each topic includes examples of the following deployments:</span></span>

- <span data-ttu-id="98420-155">依赖框架的部署</span><span class="sxs-lookup"><span data-stu-id="98420-155">Framework-dependent deployment</span></span>
- <span data-ttu-id="98420-156">包含第三方依赖项的依赖框架的部署</span><span class="sxs-lookup"><span data-stu-id="98420-156">Framework-dependent deployment with third-party dependencies</span></span>
- <span data-ttu-id="98420-157">独立部署</span><span class="sxs-lookup"><span data-stu-id="98420-157">Self-contained deployment</span></span>
- <span data-ttu-id="98420-158">包含第三方依赖项的独立部署</span><span class="sxs-lookup"><span data-stu-id="98420-158">Self-contained deployment with third-party dependencies</span></span>

## <a name="see-also"></a><span data-ttu-id="98420-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="98420-159">See also</span></span>

* [<span data-ttu-id="98420-160">使用 CLI 工具部署 .NET Core 应用程序</span><span class="sxs-lookup"><span data-stu-id="98420-160">Deploying .NET Core Apps with CLI Tools</span></span>](deploy-with-cli.md)
* [<span data-ttu-id="98420-161">使用 Visual Studio 部署 .NET Core 应用程序</span><span class="sxs-lookup"><span data-stu-id="98420-161">Deploying .NET Core Apps with Visual Studio</span></span>](deploy-with-vs.md)
* [<span data-ttu-id="98420-162">包、元包和框架</span><span class="sxs-lookup"><span data-stu-id="98420-162">Packages, Metapackages and Frameworks</span></span>](../packages.md)
* [<span data-ttu-id="98420-163">.NET Core 运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="98420-163">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
