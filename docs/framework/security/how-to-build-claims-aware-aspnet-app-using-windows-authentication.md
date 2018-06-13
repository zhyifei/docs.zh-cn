---
title: 如何：使用 Windows 身份验证生成声明感知 ASP.NET 应用程序
ms.date: 03/30/2017
ms.assetid: 11c53d9d-d34a-44b4-8b5e-22e3eaeaee93
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 2a5dbec2e92d32e45bc0271de04f8c6403f67f90
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33399790"
---
# <a name="how-to-build-claims-aware-aspnet-application-using-windows-authentication"></a><span data-ttu-id="e433b-102">如何：使用 Windows 身份验证生成声明感知 ASP.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="e433b-102">How To: Build Claims-Aware ASP.NET Application Using Windows Authentication</span></span>
## <a name="applies-to"></a><span data-ttu-id="e433b-103">适用于</span><span class="sxs-lookup"><span data-stu-id="e433b-103">Applies To</span></span>  
  
-   <span data-ttu-id="e433b-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="e433b-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="e433b-105">ASP.NET® Web 窗体</span><span class="sxs-lookup"><span data-stu-id="e433b-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="e433b-106">总结</span><span class="sxs-lookup"><span data-stu-id="e433b-106">Summary</span></span>  
 <span data-ttu-id="e433b-107">本操作说明提供了创建使用 Windows 身份验证的简单声明感知 ASP.NET Web 窗体应用程序的详细分步过程。</span><span class="sxs-lookup"><span data-stu-id="e433b-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application that uses Windows authentication.</span></span> <span data-ttu-id="e433b-108">还提供关于如何测试应用程序以验证用户使用 Windows 身份验证登录时是否呈现声明的说明。</span><span class="sxs-lookup"><span data-stu-id="e433b-108">It also provides instructions for how to test the application to verify that claims are presented when a user signs in using Windows authentication.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="e433b-109">内容</span><span class="sxs-lookup"><span data-stu-id="e433b-109">Contents</span></span>  
  
-   <span data-ttu-id="e433b-110">目标</span><span class="sxs-lookup"><span data-stu-id="e433b-110">Objectives</span></span>  
  
-   <span data-ttu-id="e433b-111">概述</span><span class="sxs-lookup"><span data-stu-id="e433b-111">Overview</span></span>  
  
-   <span data-ttu-id="e433b-112">步骤摘要</span><span class="sxs-lookup"><span data-stu-id="e433b-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="e433b-113">步骤 1 – 创建简单的 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="e433b-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="e433b-114">步骤 2 – 为使用 Windows 身份验证的声明配置 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="e433b-114">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Windows Authentication</span></span>  
  
-   <span data-ttu-id="e433b-115">步骤 3 - 测试你的解决方案</span><span class="sxs-lookup"><span data-stu-id="e433b-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="e433b-116">目标</span><span class="sxs-lookup"><span data-stu-id="e433b-116">Objectives</span></span>  
  
-   <span data-ttu-id="e433b-117">为使用 Windows 身份验证的声明配置 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="e433b-117">Configure an ASP.NET Web Forms application for claims using Windows authentication</span></span>  
  
-   <span data-ttu-id="e433b-118">测试 ASP.NET Web 窗体应用程序，了解它是否正常工作</span><span class="sxs-lookup"><span data-stu-id="e433b-118">Test the ASP.NET Web Forms application to see if it is working properly</span></span>  
  
## <a name="overview"></a><span data-ttu-id="e433b-119">概述</span><span class="sxs-lookup"><span data-stu-id="e433b-119">Overview</span></span>  
 <span data-ttu-id="e433b-120">在 .NET 4.5 中，已将 WIF 及其基于声明的授权作为 Framework 的重要组成部分包括在内。</span><span class="sxs-lookup"><span data-stu-id="e433b-120">In .NET 4.5, WIF and its claims-based authorization have been included as an integral part of the Framework.</span></span> <span data-ttu-id="e433b-121">以前，如果想要来自 ASP.NET 用户的声明，需要安装 WIF，然后将接口转换为如 `Thread.CurrentPrincipal` 或 `HttpContext.Current.User` 的主体对象。</span><span class="sxs-lookup"><span data-stu-id="e433b-121">Previously, if you wanted claims from an ASP.NET user, you were required to install WIF, and then cast interfaces to Principal objects such as `Thread.CurrentPrincipal` or `HttpContext.Current.User`.</span></span> <span data-ttu-id="e433b-122">现在，声明由这些主体对象自动提供。</span><span class="sxs-lookup"><span data-stu-id="e433b-122">Now, claims are served automatically by these Principal objects.</span></span>  
  
 <span data-ttu-id="e433b-123">Windows 身份验证受益于 .NET 4.5 对 WIF 的纳入，因为所有通过 Windows 凭据进行身份验证的用户会自动拥有与之关联的声明。</span><span class="sxs-lookup"><span data-stu-id="e433b-123">Windows authentication has benefited from WIF’s inclusion in .NET 4.5 because all users authenticated by Windows credentials automatically have claims associated with them.</span></span> <span data-ttu-id="e433b-124">如本操作说明所示，可在使用 Windows 身份验证的 ASP.NET 应用程序中开始立即使用这些声明。</span><span class="sxs-lookup"><span data-stu-id="e433b-124">You can begin using these claims immediately in an ASP.NET application that uses Windows authentication, as this How-To demonstrates.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="e433b-125">步骤摘要</span><span class="sxs-lookup"><span data-stu-id="e433b-125">Summary of Steps</span></span>  
  
-   <span data-ttu-id="e433b-126">步骤 1 – 创建简单的 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="e433b-126">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="e433b-127">步骤 2 – 为使用 Windows 身份验证的声明配置 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="e433b-127">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Windows Authentication</span></span>  
  
-   <span data-ttu-id="e433b-128">步骤 3 - 测试你的解决方案</span><span class="sxs-lookup"><span data-stu-id="e433b-128">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="e433b-129">步骤 1 – 创建简单的 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="e433b-129">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="e433b-130">在此步骤中，将创建一个新的 ASP.NET Web 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="e433b-130">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="e433b-131">创建一个简单 ASP.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="e433b-131">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="e433b-132">启动 Visual Studio，然后依次单击“文件”、“新建”和“项目”。</span><span class="sxs-lookup"><span data-stu-id="e433b-132">Start Visual Studio, then click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="e433b-133">在“新建项目”窗口中，单击“ASP.NET Web 窗体应用程序”。</span><span class="sxs-lookup"><span data-stu-id="e433b-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="e433b-134">在“名称”中，输入 `TestApp`，然后按“确定”。</span><span class="sxs-lookup"><span data-stu-id="e433b-134">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4.  <span data-ttu-id="e433b-135">创建 TestApp 项目后，在“解决方案资源管理器”中单击它。</span><span class="sxs-lookup"><span data-stu-id="e433b-135">After the **TestApp** project has been created, click on it in **Solution Explorer**.</span></span> <span data-ttu-id="e433b-136">项目的属性会在“解决方案资源管理器”下的“属性面板”窗格中显示。</span><span class="sxs-lookup"><span data-stu-id="e433b-136">The project’s properties will appear in the **Properties** pane below **Solution Explorer**.</span></span> <span data-ttu-id="e433b-137">将“Windows 身份验证”属性设置为“启用”。</span><span class="sxs-lookup"><span data-stu-id="e433b-137">Set the **Windows Authentication** property to **Enabled**.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="e433b-138">新的 ASP.NET 应用程序中默认禁用 Windows 身份验证，因此必须手动启用它。</span><span class="sxs-lookup"><span data-stu-id="e433b-138">Windows authentication is disabled by default in new ASP.NET applications, so you must manually enable it.</span></span>  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-windows-authentication"></a><span data-ttu-id="e433b-139">步骤 2 – 为使用 Windows 身份验证的声明配置 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="e433b-139">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Windows Authentication</span></span>  
 <span data-ttu-id="e433b-140">在此步骤中，将配置条目添加到 Web.config 配置文件，并修改 Default.aspx 文件以显示帐户的声明信息。</span><span class="sxs-lookup"><span data-stu-id="e433b-140">In this step you will add a configuration entry to the *Web.config* configuration file and modify the *Default.aspx* file to display claims information for an account.</span></span>  
  
#### <a name="to-configure-aspnet-application-for-claims-using-windows-authentication"></a><span data-ttu-id="e433b-141">为使用 Windows 身份验证的声明配置 ASP.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="e433b-141">To configure ASP.NET application for claims using Windows authentication</span></span>  
  
1.  <span data-ttu-id="e433b-142">在 TestApp 项目的 Default.aspx 文件中，将现有标记替换为以下内容：</span><span class="sxs-lookup"><span data-stu-id="e433b-142">In the **TestApp** project’s *Default.aspx* file, replace the existing markup with the following:</span></span>  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true"  
        CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
        <p>  
            This page displays the claims associated with a Windows authenticated user.          
        </p>  
        <h3>Your Claims</h3>  
        <p>  
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">  
                <AlternatingRowStyle BackColor="White" />  
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />  
            </asp:GridView>  
        </p>  
    </asp:Content>  
    ```  
  
     <span data-ttu-id="e433b-143">此步骤将 GridView 控件添加到“Default.aspx”页，该页将填充从 Windows 身份验证中检索的声明。</span><span class="sxs-lookup"><span data-stu-id="e433b-143">This step adds a GridView control to your *Default.aspx* page that will be populated with the claims retrieved from Windows authentication.</span></span>  
  
2.  <span data-ttu-id="e433b-144">保存 Default.aspx 文件，然后打开名为 Default.aspx.cs 的代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="e433b-144">Save the *Default.aspx* file, then open its code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="e433b-145">将现有代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="e433b-145">Replace the existing code with the following:</span></span>  
  
    ```csharp  
    using System;  
    using System.Web.UI;  
    using System.Security.Claims;  
  
    namespace TestApp  
    {  
        public partial class _Default : Page  
        {  
            protected void Page_Load(object sender, EventArgs e)  
            {  
                ClaimsPrincipal claimsPrincipal = Page.User as ClaimsPrincipal;  
                this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                this.ClaimsGridView.DataBind();  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="e433b-146">上方的代码将显示有关已经过身份验证的用户的声明。</span><span class="sxs-lookup"><span data-stu-id="e433b-146">The above code will display claims about an authenticated user.</span></span>  
  
3.  <span data-ttu-id="e433b-147">若要更改应用程序的身份验证类型，请修改项目的 Web.config 根文件的 \<system.web> 节中的 \<authentication> 块，使其只包括以下配置条目：</span><span class="sxs-lookup"><span data-stu-id="e433b-147">To change the application’s authentication type, modify the **\<authentication>** block in the **\<system.web>** section of the project’s root *Web.config* file so that it only includes the following configuration entry:</span></span>  
  
    ```xml  
    <authentication mode="Windows" />  
    ```  
  
4.  <span data-ttu-id="e433b-148">最后，修改同一 Web.config 文件的 \<system.web> 节中的 \<authorization> 块以强制身份验证：</span><span class="sxs-lookup"><span data-stu-id="e433b-148">Finally, modify the **\<authorization>** block in the **\<system.web>** section of the same *Web.config* file to force authentication:</span></span>  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    ```  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="e433b-149">步骤 3 - 测试你的解决方案</span><span class="sxs-lookup"><span data-stu-id="e433b-149">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="e433b-150">此步骤中将测试 ASP.NET Web 窗体应用程序，并验证用户使用 Windows 身份验证登录时是否呈现声明。</span><span class="sxs-lookup"><span data-stu-id="e433b-150">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Windows authentication.</span></span>  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-windows-authentication"></a><span data-ttu-id="e433b-151">为使用 Windows 身份验证的声明测试 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="e433b-151">To test your ASP.NET Web Forms application for claims using Windows authentication</span></span>  
  
1.  <span data-ttu-id="e433b-152">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="e433b-152">Press **F5** to build and run the application.</span></span> <span data-ttu-id="e433b-153">应当会显示 Default.aspx，且你的 Windows 帐户名（包括域名）应在页面的右上角显示为已经过身份验证的用户。</span><span class="sxs-lookup"><span data-stu-id="e433b-153">You should be presented with *Default.aspx*, and your Windows account name (including domain name) should already appear as the authenticated user in the top right of the page.</span></span> <span data-ttu-id="e433b-154">页面内容应包括一个表，其中填充有从你的 Windows 帐户检索的声明。</span><span class="sxs-lookup"><span data-stu-id="e433b-154">The page’s content should include a table filled with claims retrieved from your Windows account.</span></span>
