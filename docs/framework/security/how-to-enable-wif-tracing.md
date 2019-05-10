---
title: 如何：启用 WIF 跟踪
ms.date: 03/30/2017
ms.assetid: 271b6889-3454-46ff-96ab-9feb15e742ee
author: BrucePerlerMS
ms.openlocfilehash: 72e22fb5e0358c5f216bfe59d16ad030ce02e0eb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626057"
---
# <a name="how-to-enable-wif-tracing"></a><span data-ttu-id="092f2-102">如何：启用 WIF 跟踪</span><span class="sxs-lookup"><span data-stu-id="092f2-102">How To: Enable WIF Tracing</span></span>
## <a name="applies-to"></a><span data-ttu-id="092f2-103">适用于</span><span class="sxs-lookup"><span data-stu-id="092f2-103">Applies To</span></span>  
  
- <span data-ttu-id="092f2-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="092f2-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
- <span data-ttu-id="092f2-105">ASP.NET® Web 窗体</span><span class="sxs-lookup"><span data-stu-id="092f2-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="092f2-106">总结</span><span class="sxs-lookup"><span data-stu-id="092f2-106">Summary</span></span>  
 <span data-ttu-id="092f2-107">此“如何”主题提供了详细的分步过程，用于说明如何在 ASP.NET 应用程序中启用 WIF 跟踪。</span><span class="sxs-lookup"><span data-stu-id="092f2-107">This How-To provides detailed step-by-step procedures for enabling WIF tracing in an ASP.NET application.</span></span> <span data-ttu-id="092f2-108">还说明了如何测试应用程序，以验证跟踪侦听器和日志是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="092f2-108">It also provides instructions testing the application to verify that the trace listener and log are working correctly.</span></span> <span data-ttu-id="092f2-109">此“如何”主题未详细介绍如何创建安全令牌服务 (STS)，而是使用随标识和访问工具提供的开发 STS。</span><span class="sxs-lookup"><span data-stu-id="092f2-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and instead uses the Development STS that comes with the Identity and Access tool.</span></span> <span data-ttu-id="092f2-110">开发 STS 不执行实际的身份验证操作，只是用来进行测试。</span><span class="sxs-lookup"><span data-stu-id="092f2-110">The Development STS does not perform real authentication and is intended for testing purposes only.</span></span> <span data-ttu-id="092f2-111">你将需要安装标识和访问工具才能完成此“如何”主题。</span><span class="sxs-lookup"><span data-stu-id="092f2-111">You will need to install the Identity and Access tool to complete this How-To.</span></span> <span data-ttu-id="092f2-112">它可从以下位置下载：[标识和访问工具](https://go.microsoft.com/fwlink/?LinkID=245849)</span><span class="sxs-lookup"><span data-stu-id="092f2-112">It can be downloaded from the following location: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="092f2-113">为被动应用程序（即使用 WS 联合身份验证协议的应用程序）启用 WIF 跟踪有可能使应用程序受到拒绝服务 (DoS) 攻击或使信息泄漏给恶意方。</span><span class="sxs-lookup"><span data-stu-id="092f2-113">Enabling WIF tracing for passive applications, that is, applications that use the WS-Federation protocol, can potentially expose the application to denial of service (DoS) attacks or to information disclosure to a malicious party.</span></span> <span data-ttu-id="092f2-114">这包括被动 RP 和被动 STS。</span><span class="sxs-lookup"><span data-stu-id="092f2-114">This includes both passive RPs and passive STSes.</span></span> <span data-ttu-id="092f2-115">因此，我们建议不要在生产环境中为被动 RP 和被动 STS 启用 WIF 跟踪。</span><span class="sxs-lookup"><span data-stu-id="092f2-115">For this reason, we recommend that you not enable WIF tracing for passive RPs or STSes in a production environment.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="092f2-116">内容</span><span class="sxs-lookup"><span data-stu-id="092f2-116">Contents</span></span>  
  
- <span data-ttu-id="092f2-117">目标</span><span class="sxs-lookup"><span data-stu-id="092f2-117">Objectives</span></span>  
  
- <span data-ttu-id="092f2-118">概述</span><span class="sxs-lookup"><span data-stu-id="092f2-118">Overview</span></span>  
  
- <span data-ttu-id="092f2-119">步骤摘要</span><span class="sxs-lookup"><span data-stu-id="092f2-119">Summary of Steps</span></span>  
  
- <span data-ttu-id="092f2-120">步骤 1 – 创建简单的 ASP.NET Web 窗体应用程序，并启用跟踪</span><span class="sxs-lookup"><span data-stu-id="092f2-120">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
  
- <span data-ttu-id="092f2-121">步骤 2 - 测试解决方案</span><span class="sxs-lookup"><span data-stu-id="092f2-121">Step 2 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="092f2-122">目标</span><span class="sxs-lookup"><span data-stu-id="092f2-122">Objectives</span></span>  
  
- <span data-ttu-id="092f2-123">创建一个简单的 ASP.NET 应用程序，该应用程序使用标识和访问工具中的 WIF 和开发 STS</span><span class="sxs-lookup"><span data-stu-id="092f2-123">Create a simple ASP.NET application that uses WIF and the Development STS from the Identity and Access Tool</span></span>  
  
- <span data-ttu-id="092f2-124">启用跟踪，并验证其是否正常工作</span><span class="sxs-lookup"><span data-stu-id="092f2-124">Enable tracing and verify that it is working</span></span>  
  
## <a name="overview"></a><span data-ttu-id="092f2-125">概述</span><span class="sxs-lookup"><span data-stu-id="092f2-125">Overview</span></span>  
 <span data-ttu-id="092f2-126">跟踪可通过 WIF 调试和解决许多问题类型，包括令牌、cookie、声明、协议消息等。</span><span class="sxs-lookup"><span data-stu-id="092f2-126">Tracing enables you to debug and troubleshoot many types of issues with WIF, including tokens, cookies, claims, protocol messages, and more.</span></span> <span data-ttu-id="092f2-127">WIF 跟踪类似于 WCF 跟踪；例如，可选择跟踪的详细级别，显示从关键消息到所有消息的一切内容。</span><span class="sxs-lookup"><span data-stu-id="092f2-127">WIF tracing is similar to WCF tracing; for example, you can choose the verbosity of traces to display everything from critical messages to all messages.</span></span> <span data-ttu-id="092f2-128">可以在 .xml 文件或 .svclog 文件中生成 WIF 跟踪，可通过使用服务跟踪查看器工具查看。</span><span class="sxs-lookup"><span data-stu-id="092f2-128">WIF traces can be generated in **.xml** files or in **.svclog** files that are viewable by using the Service Trace Viewer Tool.</span></span> <span data-ttu-id="092f2-129">此工具位于**bin** Windows SDK 目录路径在计算机上安装，例如：**C:\Program Files\Microsoft SDKs\Windows\v7.1\Bin\SvcTraceViewer.exe**.</span><span class="sxs-lookup"><span data-stu-id="092f2-129">This tool is located in the **bin** directory of the Windows SDK install path on your computer, for example: **C:\Program Files\Microsoft SDKs\Windows\v7.1\Bin\SvcTraceViewer.exe**.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="092f2-130">步骤摘要</span><span class="sxs-lookup"><span data-stu-id="092f2-130">Summary of Steps</span></span>  
  
- <span data-ttu-id="092f2-131">步骤 1 – 创建简单的 ASP.NET Web 窗体应用程序，并启用跟踪</span><span class="sxs-lookup"><span data-stu-id="092f2-131">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
  
- <span data-ttu-id="092f2-132">步骤 2 - 测试解决方案</span><span class="sxs-lookup"><span data-stu-id="092f2-132">Step 2 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application-and-enable-tracing"></a><span data-ttu-id="092f2-133">步骤 1 – 创建简单的 ASP.NET Web 窗体应用程序，并启用跟踪</span><span class="sxs-lookup"><span data-stu-id="092f2-133">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
 <span data-ttu-id="092f2-134">此步骤将创建新的 ASP.NET Web 窗体应用程序并修改 Web.config 文件以启用跟踪。</span><span class="sxs-lookup"><span data-stu-id="092f2-134">In this step, you will create a new ASP.NET Web Forms application and modify the *Web.config* file to enable tracing.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="092f2-135">创建一个简单 ASP.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="092f2-135">To create a simple ASP.NET application</span></span>  
  
1. <span data-ttu-id="092f2-136">启动 Visual Studio，然后依次单击“文件”、“新建”和“项目”。</span><span class="sxs-lookup"><span data-stu-id="092f2-136">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2. <span data-ttu-id="092f2-137">在“新建项目”窗口中，单击“ASP.NET Web 窗体应用程序”。</span><span class="sxs-lookup"><span data-stu-id="092f2-137">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3. <span data-ttu-id="092f2-138">在“名称”中，输入 `TestApp`，然后按“确定”。</span><span class="sxs-lookup"><span data-stu-id="092f2-138">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4. <span data-ttu-id="092f2-139">在“解决方案资源管理器”下，右键单击“TestApp”项目，然后选择“标识和访问”。</span><span class="sxs-lookup"><span data-stu-id="092f2-139">Right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
5. <span data-ttu-id="092f2-140">“标识和访问”窗口随即出现。</span><span class="sxs-lookup"><span data-stu-id="092f2-140">The **Identity and Access** window appears.</span></span> <span data-ttu-id="092f2-141">在“提供程序”下，选择“使用本地开发 STS 测试应用程序”，然后单击“应用”。</span><span class="sxs-lookup"><span data-stu-id="092f2-141">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
6. <span data-ttu-id="092f2-142">创建一个新文件夹中名为**日志**中的根**c:** 驱动器中，如所示：**C:\logs**</span><span class="sxs-lookup"><span data-stu-id="092f2-142">Create a new folder in named **logs** in the root of the **C:** drive, like shown: **C:\logs**</span></span>  
  
7. <span data-ttu-id="092f2-143">将以下 \<system.diagnostics > 元素添加到 Web.config 配置文件中，紧跟在 \</configSections > 元素之后，如下所示：</span><span class="sxs-lookup"><span data-stu-id="092f2-143">Add the following **\<system.diagnostics>** element to the *Web.config* configuration file immediately following the closing **\</configSections>** element, like shown:</span></span>  
  
    ```xml  
    <configuration>  
        <configSections>  
            ...
        </configSections>  
        <system.diagnostics>  
            <sources>  
                <source name="System.IdentityModel" switchValue="Verbose">  
                    <listeners>  
                        <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="C:\logs\WIF.xml" />  
                    </listeners>  
                </source>  
            </sources>  
            <trace autoflush="true" />  
        </system.diagnostics>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="092f2-144">在 initializeData 属性中指定的目录位置必须存在，才可开始日志记录。</span><span class="sxs-lookup"><span data-stu-id="092f2-144">The directory location specified in the **initializeData** attribute must exist before logging can begin.</span></span> <span data-ttu-id="092f2-145">如果位置不存在，则无法创建任何日志。</span><span class="sxs-lookup"><span data-stu-id="092f2-145">If the location does not exist, no logs will be created.</span></span>  
  
     <span data-ttu-id="092f2-146">上面的配置设置将启用 WIF 的详细跟踪，并将生成的日志保存在 C:logsWIF.xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="092f2-146">The configuration settings above will enable **Verbose** tracing for WIF and save the resulting log to the **C:logsWIF.xml** file.</span></span>  
  
## <a name="step-2--test-your-solution"></a><span data-ttu-id="092f2-147">步骤 2 - 测试解决方案</span><span class="sxs-lookup"><span data-stu-id="092f2-147">Step 2 – Test Your Solution</span></span>  
 <span data-ttu-id="092f2-148">此步骤将测试已启用 WIF 的 ASP.NET 应用程序，以验证是否正在记录日志。</span><span class="sxs-lookup"><span data-stu-id="092f2-148">In this step, you will test your WIF-enabled ASP.NET application to verify that logs are being recorded.</span></span>  
  
#### <a name="to-test-your-wif-enabled-aspnet-application-for-successful-tracing"></a><span data-ttu-id="092f2-149">测试是否成功跟踪已启用 WIF 的 ASP.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="092f2-149">To test your WIF-enabled ASP.NET application for successful tracing</span></span>  
  
1. <span data-ttu-id="092f2-150">按 F5 键运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="092f2-150">Run the solution by pressing the **F5** key.</span></span> <span data-ttu-id="092f2-151">应显示默认 ASP.NET 主页，且你会通过用户名 Terry （这是由开发 STS 返回的默认用户名）进行自动身份验证。</span><span class="sxs-lookup"><span data-stu-id="092f2-151">You should be presented with the default ASP.NET Home Page and automatically authenticated with the username *Terry*, which is the default user that is returned by the Development STS.</span></span>  
  
2. <span data-ttu-id="092f2-152">关闭浏览器窗口，然后导航到 C:\logs 文件夹。</span><span class="sxs-lookup"><span data-stu-id="092f2-152">Close the browser window and then navigate to the **C:\logs** folder.</span></span> <span data-ttu-id="092f2-153">使用文本编辑器打开 C:\logs\WIF.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="092f2-153">Open the **C:\logs\WIF.xml** file using a text editor.</span></span>  
  
3. <span data-ttu-id="092f2-154">检查 WIF.xml 文件并验证该文件是否包含以 \<E2ETraceEvent> 开头的项。</span><span class="sxs-lookup"><span data-stu-id="092f2-154">Inspect the **WIF.xml** file and verify that it contains entries starting with **\<E2ETraceEvent>**.</span></span> <span data-ttu-id="092f2-155">这些跟踪将包含 \<TraceRecord > 元素，其中包含对跟踪活动的描述，如验证 SecurityToken。</span><span class="sxs-lookup"><span data-stu-id="092f2-155">These traces will contain **\<TraceRecord>** elements with descriptions for the traced activity, such as **Validating SecurityToken**.</span></span>
