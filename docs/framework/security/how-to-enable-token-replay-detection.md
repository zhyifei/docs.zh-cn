---
title: "如何：启用令牌重播检测"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a9f5771-f5f6-4100-8501-406aa20d731a
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: cde32407f072f3d29af4a8d1aae559e46057ae3a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enable-token-replay-detection"></a><span data-ttu-id="4dfbf-102">如何：启用令牌重播检测</span><span class="sxs-lookup"><span data-stu-id="4dfbf-102">How To: Enable Token Replay Detection</span></span>
## <a name="applies-to"></a><span data-ttu-id="4dfbf-103">适用于</span><span class="sxs-lookup"><span data-stu-id="4dfbf-103">Applies To</span></span>  
  
-   <span data-ttu-id="4dfbf-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="4dfbf-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="4dfbf-105">ASP.NET® Web 窗体</span><span class="sxs-lookup"><span data-stu-id="4dfbf-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="4dfbf-106">摘要</span><span class="sxs-lookup"><span data-stu-id="4dfbf-106">Summary</span></span>  
 <span data-ttu-id="4dfbf-107">此“如何”主题提供了详细的分步过程，用于说明如何在使用 WIF 的 ASP.NET 应用程序中启用令牌重播检测。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-107">This How-To provides detailed step-by-step procedures for enabling token replay detection in an ASP.NET application that uses WIF.</span></span> <span data-ttu-id="4dfbf-108">还说明了如何测试应用程序，以验证是否启用令牌重播检测。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-108">It also provides instructions for how to test the application to verify that token replay detection is enabled.</span></span> <span data-ttu-id="4dfbf-109">此“如何”主题未详细介绍如何创建安全令牌服务 (STS)，而是使用随标识和访问工具提供的开发 STS。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and instead uses the Development STS that comes with the Identity and Access tool.</span></span> <span data-ttu-id="4dfbf-110">开发 STS 不执行实际的身份验证操作，只是用来进行测试。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-110">The Development STS does not perform real authentication and is intended for testing purposes only.</span></span> <span data-ttu-id="4dfbf-111">你将需要安装标识和访问工具才能完成此“如何”主题。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-111">You will need to install the Identity and Access tool to complete this How-To.</span></span> <span data-ttu-id="4dfbf-112">此工具可以从下列位置下载：[标识和访问工具](http://go.microsoft.com/fwlink/?LinkID=245849)</span><span class="sxs-lookup"><span data-stu-id="4dfbf-112">It can be downloaded from the following location: [Identity and Access Tool](http://go.microsoft.com/fwlink/?LinkID=245849)</span></span>  
  
## <a name="contents"></a><span data-ttu-id="4dfbf-113">内容</span><span class="sxs-lookup"><span data-stu-id="4dfbf-113">Contents</span></span>  
  
-   <span data-ttu-id="4dfbf-114">目标</span><span class="sxs-lookup"><span data-stu-id="4dfbf-114">Objectives</span></span>  
  
-   <span data-ttu-id="4dfbf-115">概述</span><span class="sxs-lookup"><span data-stu-id="4dfbf-115">Overview</span></span>  
  
-   <span data-ttu-id="4dfbf-116">步骤摘要</span><span class="sxs-lookup"><span data-stu-id="4dfbf-116">Summary of Steps</span></span>  
  
-   <span data-ttu-id="4dfbf-117">步骤 1 – 创建简单的 ASP.NET Web 窗体应用程序，并启用重播检测</span><span class="sxs-lookup"><span data-stu-id="4dfbf-117">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Replay Detection</span></span>  
  
-   <span data-ttu-id="4dfbf-118">步骤 2 - 测试解决方案</span><span class="sxs-lookup"><span data-stu-id="4dfbf-118">Step 2 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="4dfbf-119">目标</span><span class="sxs-lookup"><span data-stu-id="4dfbf-119">Objectives</span></span>  
  
-   <span data-ttu-id="4dfbf-120">创建一个简单的 ASP.NET 应用程序，该应用程序使用标识和访问工具中的 WIF 和开发 STS</span><span class="sxs-lookup"><span data-stu-id="4dfbf-120">Create a simple ASP.NET application that uses WIF and the Development STS from the Identity and Access Tool</span></span>  
  
-   <span data-ttu-id="4dfbf-121">启用令牌重播检测并验证其是否正常运行</span><span class="sxs-lookup"><span data-stu-id="4dfbf-121">Enable token replay detection and verify that it is working</span></span>  
  
## <a name="overview"></a><span data-ttu-id="4dfbf-122">概述</span><span class="sxs-lookup"><span data-stu-id="4dfbf-122">Overview</span></span>  
 <span data-ttu-id="4dfbf-123">客户端尝试向具有客户端已使用的 STS 令牌的信赖方进行身份验证时，出现重播攻击。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-123">A replay attack occurs when a client attempts to authenticate to a relying party with an STS token that the client has already used.</span></span> <span data-ttu-id="4dfbf-124">为防止这种攻击，WIF 包含以前用过的 STS 令牌的重播检测缓存。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-124">To help prevent this attack, WIF contains a replay detection cache of previously used STS tokens.</span></span> <span data-ttu-id="4dfbf-125">启用后，重播检测会检查传入请求的令牌，并验证此令牌以前是否已使用过。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-125">When enabled, replay detection checks the token of the incoming request and verifies whether or not the token has been previously used.</span></span> <span data-ttu-id="4dfbf-126">如果该令牌已使用过，则会拒绝请求，并引发 <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> 异常。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-126">If the token has been used already, the request is refused and a <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> exception is thrown.</span></span>  
  
 <span data-ttu-id="4dfbf-127">以下步骤演示启用重播检测所需的配置更改。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-127">The following steps demonstrate the configuration changes required to enable replay detection.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="4dfbf-128">步骤摘要</span><span class="sxs-lookup"><span data-stu-id="4dfbf-128">Summary of Steps</span></span>  
  
-   <span data-ttu-id="4dfbf-129">步骤 1 – 创建简单的 ASP.NET Web 窗体应用程序，并启用重播检测</span><span class="sxs-lookup"><span data-stu-id="4dfbf-129">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Replay Detection</span></span>  
  
-   <span data-ttu-id="4dfbf-130">步骤 2 - 测试解决方案</span><span class="sxs-lookup"><span data-stu-id="4dfbf-130">Step 2 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application-and-enable-replay-detection"></a><span data-ttu-id="4dfbf-131">步骤 1 – 创建简单的 ASP.NET Web 窗体应用程序，并启用重播检测</span><span class="sxs-lookup"><span data-stu-id="4dfbf-131">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Replay Detection</span></span>  
 <span data-ttu-id="4dfbf-132">此步骤将创建新的 ASP.NET Web 窗体应用程序并修改 Web.config 文件以启用重播检测。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-132">In this step, you will create a new ASP.NET Web Forms application and modify the *Web.config* file to enable replay detection.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="4dfbf-133">创建一个简单 ASP.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="4dfbf-133">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="4dfbf-134">启动 Visual Studio，然后依次单击“文件”、“新建”和“项目”。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-134">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="4dfbf-135">在“新建项目”窗口中，单击“ASP.NET Web 窗体应用程序”。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-135">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="4dfbf-136">在“名称”中，输入 `TestApp`，然后按“确定”。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-136">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4.  <span data-ttu-id="4dfbf-137">在“解决方案资源管理器”下，右键单击“TestApp”项目，然后选择“标识和访问”。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-137">Right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
5.  <span data-ttu-id="4dfbf-138">“标识和访问”窗口随即出现。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-138">The **Identity and Access** window appears.</span></span> <span data-ttu-id="4dfbf-139">在“提供程序”下，选择“使用本地开发 STS 测试应用程序”，然后单击“应用”。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-139">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
6.  <span data-ttu-id="4dfbf-140">将以下 \<tokenReplayDetection> 元素添加至 Web.config 配置文件，并紧跟在 \<system.identityModel> 元素和 \<identityConfiguration> 元素之后，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4dfbf-140">Add the following **\<tokenReplayDetection>** element to the *Web.config* configuration file immediately following the **\<system.identityModel>** and **\<identityConfiguration>** elements, like shown:</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration>  
            <tokenReplayDetection enabled="true"/>  
    ```  
  
## <a name="step-2--test-your-solution"></a><span data-ttu-id="4dfbf-141">步骤 2 - 测试解决方案</span><span class="sxs-lookup"><span data-stu-id="4dfbf-141">Step 2 – Test Your Solution</span></span>  
 <span data-ttu-id="4dfbf-142">此步骤将测试已启用 WIF 的 ASP.NET 应用程序，以验证是否已启用重播检测。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-142">In this step, you will test your WIF-enabled ASP.NET application to verify that replay detection has been enabled.</span></span>  
  
#### <a name="to-test-your-wif-enabled-aspnet-application-for-replay-detection"></a><span data-ttu-id="4dfbf-143">测试已启用 WIF 的 ASP.NET 应用程序，以进行重播检测</span><span class="sxs-lookup"><span data-stu-id="4dfbf-143">To test your WIF-enabled ASP.NET application for replay detection</span></span>  
  
1.  <span data-ttu-id="4dfbf-144">按 F5 键运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-144">Run the solution by pressing the **F5** key.</span></span> <span data-ttu-id="4dfbf-145">应显示默认 ASP.NET 主页，且你会通过用户名 Terry （这是由开发 STS 返回的默认用户名）进行自动身份验证。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-145">You should be presented with the default ASP.NET Home Page and automatically authenticated with the username *Terry*, which is the default user that is returned by the Development STS.</span></span>  
  
2.  <span data-ttu-id="4dfbf-146">按浏览器“返回”按钮。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-146">Press the browser’s **Back** button.</span></span> <span data-ttu-id="4dfbf-147">“/”应用程序页应显示服务器错误，描述为：ID1062: 已检测到重播: 令牌: “System.IdentityModel.Tokens.SamlSecurityToken”，后跟 AssertionId 和颁发者。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-147">You should be presented with a **Server Error in ‘/’ Application** page with the following description: *ID1062: Replay has been detected for: Token: 'System.IdentityModel.Tokens.SamlSecurityToken'*, followed by an *AssertionId* and an *Issuer*.</span></span>  
  
     <span data-ttu-id="4dfbf-148">会出现此错误页，因为检测到令牌重播时引发 <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> 类型异常。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-148">You are seeing this error page because an exception of type <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> was thrown when the token replay was detected.</span></span> <span data-ttu-id="4dfbf-149">出现此错误的原因是第一次提供令牌时，你尝试重新发送初始 POST 请求。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-149">This error occurs because you are attempting to re-send the initial POST request when the token was first presented.</span></span> <span data-ttu-id="4dfbf-150">对于服务器的后续请求，“返回”按钮不会引起此行为。</span><span class="sxs-lookup"><span data-stu-id="4dfbf-150">The **Back** button will not cause this behavior on subsequent requests to the server.</span></span>
