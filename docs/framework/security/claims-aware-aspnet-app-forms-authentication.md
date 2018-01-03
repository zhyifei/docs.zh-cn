---
title: "如何：使用基于表单的身份验证生成声明感知 ASP.NET 应用程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98a3e029-1a9b-4e0c-b5d0-29d3f23f5b15
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: f4977a40d440ca45a3130fb1b06e0b286a2ab2f6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-build-claims-aware-aspnet-application-using-forms-based-authentication"></a><span data-ttu-id="346f7-102">如何：使用基于表单的身份验证生成声明感知 ASP.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="346f7-102">How To: Build Claims-Aware ASP.NET Application Using Forms-Based Authentication</span></span>
## <a name="applies-to"></a><span data-ttu-id="346f7-103">适用于</span><span class="sxs-lookup"><span data-stu-id="346f7-103">Applies To</span></span>  
  
-   <span data-ttu-id="346f7-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="346f7-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="346f7-105">ASP.NET® Web 窗体</span><span class="sxs-lookup"><span data-stu-id="346f7-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="346f7-106">摘要</span><span class="sxs-lookup"><span data-stu-id="346f7-106">Summary</span></span>  
 <span data-ttu-id="346f7-107">本操作说明提供了创建使用 Forms 身份验证的简单声明感知 ASP.NET Web 窗体应用程序的详细分步程序。</span><span class="sxs-lookup"><span data-stu-id="346f7-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application that uses Forms authentication.</span></span> <span data-ttu-id="346f7-108">它还提供关于如何测试应用程序以验证用户使用 Forms 身份验证登录时是否呈现声明的说明。</span><span class="sxs-lookup"><span data-stu-id="346f7-108">It also provides instructions for how to test the application to verify that claims are presented when a user signs in with Forms authentication.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="346f7-109">内容</span><span class="sxs-lookup"><span data-stu-id="346f7-109">Contents</span></span>  
  
-   <span data-ttu-id="346f7-110">目标</span><span class="sxs-lookup"><span data-stu-id="346f7-110">Objectives</span></span>  
  
-   <span data-ttu-id="346f7-111">概述</span><span class="sxs-lookup"><span data-stu-id="346f7-111">Overview</span></span>  
  
-   <span data-ttu-id="346f7-112">步骤摘要</span><span class="sxs-lookup"><span data-stu-id="346f7-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="346f7-113">步骤 1 – 创建简单的 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="346f7-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="346f7-114">步骤 2 – 为使用 Forms 身份验证的声明配置 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="346f7-114">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>  
  
-   <span data-ttu-id="346f7-115">步骤 3 - 测试你的解决方案</span><span class="sxs-lookup"><span data-stu-id="346f7-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="346f7-116">目标</span><span class="sxs-lookup"><span data-stu-id="346f7-116">Objectives</span></span>  
  
-   <span data-ttu-id="346f7-117">为使用 Forms 身份验证的声明配置 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="346f7-117">Configure an ASP.NET Web Forms application for claims using Forms authentication</span></span>  
  
-   <span data-ttu-id="346f7-118">测试 ASP.NET Web 窗体应用程序，了解它是否正常工作</span><span class="sxs-lookup"><span data-stu-id="346f7-118">Test the ASP.NET Web Forms application to see if it is working properly</span></span>  
  
## <a name="overview"></a><span data-ttu-id="346f7-119">概述</span><span class="sxs-lookup"><span data-stu-id="346f7-119">Overview</span></span>  
 <span data-ttu-id="346f7-120">在 .NET 4.5 中，已将 WIF 及其基于声明的授权作为 Framework 的重要组成部分包括在内。</span><span class="sxs-lookup"><span data-stu-id="346f7-120">In .NET 4.5, WIF and its claims-based authorization have been included as an integral part of the Framework.</span></span> <span data-ttu-id="346f7-121">以前，如果想要来自 ASP.NET 用户的声明，需要安装 WIF，然后将接口转换为如 `Thread.CurrentPrincipal` 或 `HttpContext.Current.User` 的主体对象。</span><span class="sxs-lookup"><span data-stu-id="346f7-121">Previously, if you wanted claims from an ASP.NET user, you were required to install WIF, and then cast interfaces to Principal objects such as `Thread.CurrentPrincipal` or `HttpContext.Current.User`.</span></span> <span data-ttu-id="346f7-122">现在，声明由这些主体对象自动提供。</span><span class="sxs-lookup"><span data-stu-id="346f7-122">Now, claims are served automatically by these Principal objects.</span></span>  
  
 <span data-ttu-id="346f7-123">Forms 身份验证已因包括在 .NET 4.5 中而获益，因为所有通过窗体进行身份验证的用户都自动具有与他们相关的声明。</span><span class="sxs-lookup"><span data-stu-id="346f7-123">Forms authentication has benefited from WIF’s inclusion in .NET 4.5 because all users authenticated by Forms automatically have claims associated with them.</span></span> <span data-ttu-id="346f7-124">如本操作说明所示，可在使用 Forms 身份验证的 ASP.NET 应用程序中立即开始使用这些声明。</span><span class="sxs-lookup"><span data-stu-id="346f7-124">You can begin using these claims immediately in an ASP.NET application that uses Forms authentication, as this How-To demonstrates.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="346f7-125">步骤摘要</span><span class="sxs-lookup"><span data-stu-id="346f7-125">Summary of Steps</span></span>  
  
-   <span data-ttu-id="346f7-126">步骤 1 – 创建简单的 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="346f7-126">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="346f7-127">步骤 2 – 为使用 Forms 身份验证的声明配置 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="346f7-127">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>  
  
-   <span data-ttu-id="346f7-128">步骤 3 - 测试你的解决方案</span><span class="sxs-lookup"><span data-stu-id="346f7-128">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="346f7-129">步骤 1 – 创建简单的 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="346f7-129">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="346f7-130">在此步骤中，将创建一个新的 ASP.NET Web 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="346f7-130">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="346f7-131">创建一个简单 ASP.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="346f7-131">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="346f7-132">启动 Visual Studio，然后依次单击“文件”、“新建”和“项目”。</span><span class="sxs-lookup"><span data-stu-id="346f7-132">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="346f7-133">在“新建项目”窗口中，单击“ASP.NET Web 窗体应用程序”。</span><span class="sxs-lookup"><span data-stu-id="346f7-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="346f7-134">在“名称”中，输入 `TestApp`，然后按“确定”。</span><span class="sxs-lookup"><span data-stu-id="346f7-134">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="346f7-135">步骤 2 – 为使用 Forms 身份验证的声明配置 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="346f7-135">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>  
 <span data-ttu-id="346f7-136">在此步骤中，将向“Web.config”配置文件添加一个配置项并编辑“Default.aspx”文件，以便显示帐户的声明信息。</span><span class="sxs-lookup"><span data-stu-id="346f7-136">In this step you will add a configuration entry to the *Web.config* configuration file and edit the *Default.aspx* file to display claims information for an account.</span></span>  
  
#### <a name="to-configure-aspnet-application-for-claims-using-forms-authentication"></a><span data-ttu-id="346f7-137">为使用 Forms 身份验证的声明配置 ASP.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="346f7-137">To configure ASP.NET application for claims using Forms authentication</span></span>  
  
1.  <span data-ttu-id="346f7-138">在“Default.aspx”文件中，将现有标记替换为以下内容：</span><span class="sxs-lookup"><span data-stu-id="346f7-138">In the *Default.aspx* file, replace the existing markup with the following:</span></span>  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
        <p>  
            This page displays the claims associated with a Forms authenticated user.          
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
  
     <span data-ttu-id="346f7-139">此步骤将向“Default.aspx”页添加 GridView 控件，该页将填充从 Forms 身份验证检索的声明。</span><span class="sxs-lookup"><span data-stu-id="346f7-139">This step adds a GridView control to your *Default.aspx* page that will be populated with the claims retrieved from Forms authentication.</span></span>  
  
2.  <span data-ttu-id="346f7-140">保存 Default.aspx 文件，然后打开名为 Default.aspx.cs 的代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="346f7-140">Save the *Default.aspx* file, then open its code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="346f7-141">将现有代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="346f7-141">Replace the existing code with the following:</span></span>  
  
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
  
                if (claimsPrincipal != null)  
                {  
                    this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                    this.ClaimsGridView.DataBind();  
                }  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="346f7-142">以上代码将显示有关已通过身份验证的用户（包括由 Forms 身份验证标识的用户）的声明。</span><span class="sxs-lookup"><span data-stu-id="346f7-142">The above code will display claims about an authenticated user, including users identified by Forms authentication.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="346f7-143">步骤 3 - 测试你的解决方案</span><span class="sxs-lookup"><span data-stu-id="346f7-143">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="346f7-144">此步骤中将测试 ASP.NET Web 窗体应用程序，并验证用户使用 Forms 身份验证登录时是否呈现声明。</span><span class="sxs-lookup"><span data-stu-id="346f7-144">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Forms authentication.</span></span>  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="346f7-145">为使用 Forms 身份验证的声明测试 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="346f7-145">To test your ASP.NET Web Forms application for claims using Forms authentication</span></span>  
  
1.  <span data-ttu-id="346f7-146">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="346f7-146">Press **F5** to build and run the application.</span></span> <span data-ttu-id="346f7-147">将显示“Default.aspx”，其页面右上角具有“注册”和“登录”链接。</span><span class="sxs-lookup"><span data-stu-id="346f7-147">You should be presented with *Default.aspx*, which has **Register** and **Log in** links in the top right of the page.</span></span> <span data-ttu-id="346f7-148">单击“注册”。</span><span class="sxs-lookup"><span data-stu-id="346f7-148">Click **Register**.</span></span>  
  
2.  <span data-ttu-id="346f7-149">在“注册”页上，创建用户帐户，然后单击“注册”。</span><span class="sxs-lookup"><span data-stu-id="346f7-149">On the **Register** page, create a user account, and then click **Register**.</span></span> <span data-ttu-id="346f7-150">将使用 Forms 身份验证创建帐户，并将使你自动登录。</span><span class="sxs-lookup"><span data-stu-id="346f7-150">Your account will be created using Forms authentication, and you will be automatically signed in.</span></span>  
  
3.  <span data-ttu-id="346f7-151">已重定向到主页后，将看到一个位于标题“你的声明”下方的表格，它包含有关帐户的“颁发者”、“原始颁发者”、“类型”、“值”和“值类型”声明信息。</span><span class="sxs-lookup"><span data-stu-id="346f7-151">After you have been redirected to the home page, you should see a table beneath the **Your Claims** heading that includes the **Issuer**, **OriginalIssuer**, **Type**, **Value**, and **ValueType** claims information about your account.</span></span>
