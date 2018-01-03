---
title: "如何：转换传入声明"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2831d514-d9d8-4200-9192-954bb6da1126
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 1f736554cd50a5ca2bd45dfab2f41ba672601f29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-transform-incoming-claims"></a><span data-ttu-id="f9c7a-102">如何：转换传入声明</span><span class="sxs-lookup"><span data-stu-id="f9c7a-102">How To: Transform Incoming Claims</span></span>
## <a name="applies-to"></a><span data-ttu-id="f9c7a-103">适用于</span><span class="sxs-lookup"><span data-stu-id="f9c7a-103">Applies To</span></span>  
  
-   <span data-ttu-id="f9c7a-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="f9c7a-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="f9c7a-105">ASP.NET® Web 窗体</span><span class="sxs-lookup"><span data-stu-id="f9c7a-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="f9c7a-106">摘要</span><span class="sxs-lookup"><span data-stu-id="f9c7a-106">Summary</span></span>  
 <span data-ttu-id="f9c7a-107">本指南提供了创建简单的声明感知 ASP.NET Web 窗体应用程序和转换传入声明的详细分步过程。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application and transforming incoming claims.</span></span> <span data-ttu-id="f9c7a-108">它还提供关于如何测试应用程序的说明，以便验证当应用程序运行时是否呈现已转换声明。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-108">It also provides instructions for how to test the application to verify that transformed claims are presented when the application is run.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="f9c7a-109">内容</span><span class="sxs-lookup"><span data-stu-id="f9c7a-109">Contents</span></span>  
  
-   <span data-ttu-id="f9c7a-110">目标</span><span class="sxs-lookup"><span data-stu-id="f9c7a-110">Objectives</span></span>  
  
-   <span data-ttu-id="f9c7a-111">概述</span><span class="sxs-lookup"><span data-stu-id="f9c7a-111">Overview</span></span>  
  
-   <span data-ttu-id="f9c7a-112">步骤摘要</span><span class="sxs-lookup"><span data-stu-id="f9c7a-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="f9c7a-113">步骤 1 – 创建简单的 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="f9c7a-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="f9c7a-114">步骤 2 – 使用自定义 ClaimsAuthenticationManager 实现声明转换</span><span class="sxs-lookup"><span data-stu-id="f9c7a-114">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>  
  
-   <span data-ttu-id="f9c7a-115">步骤 3 - 测试你的解决方案</span><span class="sxs-lookup"><span data-stu-id="f9c7a-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="f9c7a-116">目标</span><span class="sxs-lookup"><span data-stu-id="f9c7a-116">Objectives</span></span>  
  
-   <span data-ttu-id="f9c7a-117">配置 ASP.NET Web 窗体应用程序实现基于声明的身份验证</span><span class="sxs-lookup"><span data-stu-id="f9c7a-117">Configure an ASP.NET Web Forms application for claims-based authentication</span></span>  
  
-   <span data-ttu-id="f9c7a-118">通过添加管理员角色声明转换传入声明</span><span class="sxs-lookup"><span data-stu-id="f9c7a-118">Transform incoming claims by adding an Administrator role claim</span></span>  
  
-   <span data-ttu-id="f9c7a-119">测试 ASP.NET Web 窗体应用程序，了解它是否正常工作</span><span class="sxs-lookup"><span data-stu-id="f9c7a-119">Test the ASP.NET Web Forms application to see if it is working properly</span></span>  
  
## <a name="overview"></a><span data-ttu-id="f9c7a-120">概述</span><span class="sxs-lookup"><span data-stu-id="f9c7a-120">Overview</span></span>  
 <span data-ttu-id="f9c7a-121">WIF 公开名为 <xref:System.Security.Claims.ClaimsAuthenticationManager> 的类，使用户在声明呈现给信赖方 (RP) 应用程序之前能够进行修改。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-121">WIF exposes a class named <xref:System.Security.Claims.ClaimsAuthenticationManager> that enables users to modify claims before they are presented to a relying party (RP) application.</span></span> <span data-ttu-id="f9c7a-122"><xref:System.Security.Claims.ClaimsAuthenticationManager> 可用于分离身份验证和基础应用程序代码之间的问题。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-122">The <xref:System.Security.Claims.ClaimsAuthenticationManager> is useful for separation of concerns between authentication and the underlying application code.</span></span> <span data-ttu-id="f9c7a-123">以下示例演示如何在传入的 <xref:System.Security.Claims.ClaimsPrincipal> 中向声明添加 RP 可能需要的角色。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-123">The example below demonstrates how to add a role to the claims in the incoming <xref:System.Security.Claims.ClaimsPrincipal> that may be required by the RP.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="f9c7a-124">步骤摘要</span><span class="sxs-lookup"><span data-stu-id="f9c7a-124">Summary of Steps</span></span>  
  
-   <span data-ttu-id="f9c7a-125">步骤 1 – 创建简单的 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="f9c7a-125">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="f9c7a-126">步骤 2 – 使用自定义 ClaimsAuthenticationManager 实现声明转换</span><span class="sxs-lookup"><span data-stu-id="f9c7a-126">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>  
  
-   <span data-ttu-id="f9c7a-127">步骤 3 - 测试你的解决方案</span><span class="sxs-lookup"><span data-stu-id="f9c7a-127">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="f9c7a-128">步骤 1 – 创建简单的 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="f9c7a-128">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="f9c7a-129">在此步骤中，将创建一个新的 ASP.NET Web 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-129">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="f9c7a-130">创建一个简单 ASP.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="f9c7a-130">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="f9c7a-131">以管理员身份在提升模式下启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-131">Start Visual Studio in elevated mode as administrator.</span></span>  
  
2.  <span data-ttu-id="f9c7a-132">在 Visual Studio 中，单击“文件”，再单击“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-132">In Visual Studio, click **File**, click **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="f9c7a-133">在“新建项目”窗口中，单击“ASP.NET Web 窗体应用程序”。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
4.  <span data-ttu-id="f9c7a-134">在“名称”中，输入 `TestApp`，然后按“确定”。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-134">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
5.  <span data-ttu-id="f9c7a-135">在“解决方案资源管理器”下，右键单击“TestApp”项目，然后选择“标识和访问”。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-135">Right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
6.  <span data-ttu-id="f9c7a-136">“标识和访问”窗口随即出现。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-136">The **Identity and Access** window appears.</span></span> <span data-ttu-id="f9c7a-137">在“提供程序”下，选择“使用本地开发 STS 测试应用程序”，然后单击“应用”。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-137">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
7.  <span data-ttu-id="f9c7a-138">在 Default.aspx 文件中，将现有标记替换为以下内容，然后保存文件：</span><span class="sxs-lookup"><span data-stu-id="f9c7a-138">In the *Default.aspx* file, replace the existing markup with the following, then save the file:</span></span>  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true"  
        CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
          <h3>Your Claims</h3>  
        <p>  
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">  
                <AlternatingRowStyle BackColor="White" />  
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />  
            </asp:GridView>  
        </p>  
    </asp:Content>  
    ```  
  
8.  <span data-ttu-id="f9c7a-139">打开名为 Default.aspx.cs 的代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-139">Open the code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="f9c7a-140">用以下内容替换现有代码，然后保存文件：</span><span class="sxs-lookup"><span data-stu-id="f9c7a-140">Replace the existing code with the following, then save the file:</span></span>  
  
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
  
## <a name="step-2--implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a><span data-ttu-id="f9c7a-141">步骤 2 – 使用自定义 ClaimsAuthenticationManager 实现声明转换</span><span class="sxs-lookup"><span data-stu-id="f9c7a-141">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>  
 <span data-ttu-id="f9c7a-142">此步骤将覆盖 <xref:System.Security.Claims.ClaimsAuthenticationManager> 类中的默认功能，向传入主体添加管理员角色。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-142">In this step you will override default functionality in the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to add an Administrator role to the incoming Principal.</span></span>  
  
#### <a name="to-implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a><span data-ttu-id="f9c7a-143">使用自定义 ClaimsAuthenticationManager 实现声明转换</span><span class="sxs-lookup"><span data-stu-id="f9c7a-143">To implement claims transformation using a custom ClaimsAuthenticationManager</span></span>  
  
1.  <span data-ttu-id="f9c7a-144">在 Visual Studio 中，右键单击解决方案，单击“添加”，然后单击“新建项目”。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-144">In Visual Studio, right-click the on the solution, click **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="f9c7a-145">在“添加新建项目”窗口中从“Visual C#”模板列表选择“类库”，输入 `ClaimsTransformation`，然后按“确定”。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-145">In the **Add New Project** window, select **Class Library** from the **Visual C#** templates list, enter `ClaimsTransformation`, and then press **OK**.</span></span> <span data-ttu-id="f9c7a-146">系统将在你的解决方案文件夹中创建新项目。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-146">The new project will be created in your solution folder.</span></span>  
  
3.  <span data-ttu-id="f9c7a-147">在“ClaimsTransformation”项目下右键单击“引用”，然后单击“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-147">Right-click on **References** under the **ClaimsTransformation** project, and then click **Add Reference**.</span></span>  
  
4.  <span data-ttu-id="f9c7a-148">在“引用管理器”窗口选择“System.IdentityModel”，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-148">In the **Reference Manager** window, select **System.IdentityModel**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="f9c7a-149">打开“Class1.cs”或若它不存在，右键单击“ClaimsTransformation”，再依次单击“添加”、“类…”</span><span class="sxs-lookup"><span data-stu-id="f9c7a-149">Open **Class1.cs**, or if it doesn’t exist, right-click **ClaimsTransformation**, click **Add**, then click **Class…**</span></span>  
  
6.  <span data-ttu-id="f9c7a-150">使用指令将以下内容添加到代码文件：</span><span class="sxs-lookup"><span data-stu-id="f9c7a-150">Add the following using directives to the code file:</span></span>  
  
    ```csharp  
    using System.Security.Claims;  
    using System.Security.Principal;  
    ```  
  
7.  <span data-ttu-id="f9c7a-151">在代码文件中添加以下类和方法。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-151">Add the following class and method in the code file.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="f9c7a-152">以下代码仅用于演示目的；请确保验证了生产代码中的预期权限。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-152">The following code is for demonstration purposes only; make sure that you verify your intended permissions in production code.</span></span>  
  
    ```csharp  
    public class ClaimsTransformationModule : ClaimsAuthenticationManager  
    {  
        public override ClaimsPrincipal Authenticate(string resourceName, ClaimsPrincipal incomingPrincipal)  
        {  
            if (incomingPrincipal != null && incomingPrincipal.Identity.IsAuthenticated == true)  
            {  
               ((ClaimsIdentity)incomingPrincipal.Identity).AddClaim(new Claim(ClaimTypes.Role, "Admin"));  
            }  
  
            return incomingPrincipal;  
        }  
    }  
    ```  
  
8.  <span data-ttu-id="f9c7a-153">保存文件并生成 ClaimsTransformation 项目。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-153">Save the file and build the **ClaimsTransformation** project.</span></span>  
  
9. <span data-ttu-id="f9c7a-154">在 TestApp ASP.NET 项目中，右键单击“引用”，然后单击“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-154">In your **TestApp** ASP.NET project, right-click on References, and then click **Add Reference**.</span></span>  
  
10. <span data-ttu-id="f9c7a-155">在“引用管理器”窗口中从左侧菜单选择“解决方案”，然后从填充选项中选择“ClaimsTransformation”，再单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-155">In the **Reference Manager** window, select **Solution** from the left menu, select **ClaimsTransformation** from the populated options, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="f9c7a-156">在根目录 Web.config 文件中，导航到 \<system.identityModel> 条目。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-156">In the root **Web.config** file, navigate to the **\<system.identityModel>** entry.</span></span> <span data-ttu-id="f9c7a-157">在 \<identityConfiguration> 元素内，添加以下行并保存文件：</span><span class="sxs-lookup"><span data-stu-id="f9c7a-157">Within the **\<identityConfiguration>** elements, add the following line and save the file:</span></span>  
  
    ```xml  
    <claimsAuthenticationManager type="ClaimsTransformation.ClaimsTransformationModule, ClaimsTransformation" />  
    ```  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="f9c7a-158">步骤 3 - 测试你的解决方案</span><span class="sxs-lookup"><span data-stu-id="f9c7a-158">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="f9c7a-159">此步骤中将测试 ASP.NET Web 窗体应用程序，并验证用户使用 Forms 身份验证登录时是否呈现声明。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-159">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Forms authentication.</span></span>  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="f9c7a-160">为使用 Forms 身份验证的声明测试 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="f9c7a-160">To test your ASP.NET Web Forms application for claims using Forms authentication</span></span>  
  
1.  <span data-ttu-id="f9c7a-161">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-161">Press **F5** to build and run the application.</span></span> <span data-ttu-id="f9c7a-162">将看到 Default.aspx。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-162">You should be presented with *Default.aspx*.</span></span>  
  
2.  <span data-ttu-id="f9c7a-163">在 Default.aspx 页，在“你的声明”标题下应看到一个表格，包括有关帐户的颁发者、原始颁发者、类型、值以及值类型声明信息。</span><span class="sxs-lookup"><span data-stu-id="f9c7a-163">On the *Default.aspx* page, you should see a table beneath the **Your Claims** heading that includes the **Issuer**, **OriginalIssuer**, **Type**, **Value**, and **ValueType** claims information about your account.</span></span> <span data-ttu-id="f9c7a-164">最后一行应以下面的方式显示：</span><span class="sxs-lookup"><span data-stu-id="f9c7a-164">The last row should be presented in the following way:</span></span>  
  
    ||||||  
    |-|-|-|-|-|  
    |<span data-ttu-id="f9c7a-165">本地机构</span><span class="sxs-lookup"><span data-stu-id="f9c7a-165">LOCAL AUTHORITY</span></span>|<span data-ttu-id="f9c7a-166">本地机构</span><span class="sxs-lookup"><span data-stu-id="f9c7a-166">LOCAL AUTHORITY</span></span>|<span data-ttu-id="f9c7a-167">http://schemas.microsoft.com/ws/2008/06/identity/claims/role</span><span class="sxs-lookup"><span data-stu-id="f9c7a-167">http://schemas.microsoft.com/ws/2008/06/identity/claims/role</span></span>|<span data-ttu-id="f9c7a-168">管理</span><span class="sxs-lookup"><span data-stu-id="f9c7a-168">Admin</span></span>|<span data-ttu-id="f9c7a-169">http://www.w3.org/2001/XMLSchema#string</span><span class="sxs-lookup"><span data-stu-id="f9c7a-169">http://www.w3.org/2001/XMLSchema#string</span></span>|
