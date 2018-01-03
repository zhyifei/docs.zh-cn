---
title: "如何：使用 WIF 生成声明感知 ASP.NET Web 窗体应用程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: efb264dd-f47b-49a9-85ee-9f45d4425765
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 70d503448946b60f1d6b63bf850d8d62fb63acc2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-build-claims-aware-aspnet-web-forms-application-using-wif"></a><span data-ttu-id="e408b-102">如何：使用 WIF 生成声明感知 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="e408b-102">How To: Build Claims-Aware ASP.NET Web Forms Application Using WIF</span></span>
## <a name="applies-to"></a><span data-ttu-id="e408b-103">适用于</span><span class="sxs-lookup"><span data-stu-id="e408b-103">Applies To</span></span>  
  
-   <span data-ttu-id="e408b-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="e408b-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="e408b-105">ASP.NET® Web 窗体</span><span class="sxs-lookup"><span data-stu-id="e408b-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="e408b-106">摘要</span><span class="sxs-lookup"><span data-stu-id="e408b-106">Summary</span></span>  
 <span data-ttu-id="e408b-107">本操作说明提供了创建简单的声明感知 ASP.NET Web 窗体应用程序的详细分步过程。</span><span class="sxs-lookup"><span data-stu-id="e408b-107">This How-To provides detailed step-by-step procedures for creating simple claims-aware ASP.NET Web Forms application.</span></span> <span data-ttu-id="e408b-108">还提供关于如何测试简单声明感知 ASP.NET Web 窗体应用程序以确保成功实现联合身份验证的说明。</span><span class="sxs-lookup"><span data-stu-id="e408b-108">It also provides instructions for how to test the simple claims-aware ASP.NET Web Forms application for successful implementation of federated authentication.</span></span> <span data-ttu-id="e408b-109">本操作说明不包括如何创建安全令牌服务 (STS) 的详细说明，且假定你已配置 STS。</span><span class="sxs-lookup"><span data-stu-id="e408b-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and assumes you have already configured an STS.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="e408b-110">内容</span><span class="sxs-lookup"><span data-stu-id="e408b-110">Contents</span></span>  
  
-   <span data-ttu-id="e408b-111">目标</span><span class="sxs-lookup"><span data-stu-id="e408b-111">Objectives</span></span>  
  
-   <span data-ttu-id="e408b-112">步骤摘要</span><span class="sxs-lookup"><span data-stu-id="e408b-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="e408b-113">步骤 1 – 创建简单的 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="e408b-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="e408b-114">第 2 步 – 为基于声明的身份验证配置 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="e408b-114">Step 2 – Configure ASP.NET Web Forms Application for Claims-Based Authentication</span></span>  
  
-   <span data-ttu-id="e408b-115">步骤 3 - 测试你的解决方案</span><span class="sxs-lookup"><span data-stu-id="e408b-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="e408b-116">目标</span><span class="sxs-lookup"><span data-stu-id="e408b-116">Objectives</span></span>  
  
-   <span data-ttu-id="e408b-117">为基于声明的身份验证配置 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="e408b-117">Configure ASP.NET Web Forms application for claims-based authentication</span></span>  
  
-   <span data-ttu-id="e408b-118">测试成功的声明感知 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="e408b-118">Test successful claims-aware ASP.NET Web Forms application</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="e408b-119">步骤摘要</span><span class="sxs-lookup"><span data-stu-id="e408b-119">Summary of Steps</span></span>  
  
-   <span data-ttu-id="e408b-120">步骤 1 – 创建简单的 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="e408b-120">Step 1 – Create Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="e408b-121">步骤 2 – 为联合身份验证配置 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="e408b-121">Step 2 – Configure ASP.NET Web Forms Application for Federated Authentication</span></span>  
  
-   <span data-ttu-id="e408b-122">步骤 3 - 测试你的解决方案</span><span class="sxs-lookup"><span data-stu-id="e408b-122">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="e408b-123">步骤 1 – 创建简单的 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="e408b-123">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="e408b-124">在此步骤中，将创建一个新的 ASP.NET Web 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="e408b-124">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="e408b-125">创建一个简单 ASP.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="e408b-125">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="e408b-126">启动 Visual Studio，然后依次单击“文件”、“新建”和“项目”。</span><span class="sxs-lookup"><span data-stu-id="e408b-126">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="e408b-127">在“新建项目”窗口中，单击“ASP.NET Web 窗体应用程序”。</span><span class="sxs-lookup"><span data-stu-id="e408b-127">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="e408b-128">在“名称”中，输入 `TestApp`，然后按“确定”。</span><span class="sxs-lookup"><span data-stu-id="e408b-128">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-based-authentication"></a><span data-ttu-id="e408b-129">第 2 步 – 为基于声明的身份验证配置 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="e408b-129">Step 2 – Configure ASP.NET Web Forms Application for Claims-Based Authentication</span></span>  
 <span data-ttu-id="e408b-130">在此步骤中，将配置条目添加到 ASP.NET Web 窗体应用程序的 Web.config 配置文件中，以使其可感知声明。</span><span class="sxs-lookup"><span data-stu-id="e408b-130">In this step you will add configuration entries to the *Web.config* configuration file of your ASP.NET Web Forms application to make it claims-aware.</span></span>  
  
#### <a name="to-configure-aspnet-application-for-claims-based-authentication"></a><span data-ttu-id="e408b-131">为基于声明的身份验证配置 ASP.NET Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="e408b-131">To configure ASP.NET application for claims-based authentication</span></span>  
  
1.  <span data-ttu-id="e408b-132">将以下配置节条目紧随添加到 Web.config 配置文件中的 \<configuration> 起始元素后：</span><span class="sxs-lookup"><span data-stu-id="e408b-132">Add the following configuration section entries to the *Web.config* configuration file immediately after the **\<configuration>** opening element:</span></span>  
  
    ```xml  
    <configSections>  
      <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
      <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2.  <span data-ttu-id="e408b-133">添加 \<location> 元素，用于启用对应用程序的联合元数据的访问权限：</span><span class="sxs-lookup"><span data-stu-id="e408b-133">Add a **\<location>** element that enables access to the application’s federation metadata:</span></span>  
  
    ```xml  
    <location path="FederationMetadata">  
      <system.web>  
        <authorization>  
          <allow users="*" />  
        </authorization>  
      </system.web>  
    </location>  
    ```  
  
3.  <span data-ttu-id="e408b-134">在 \<system.web> 元素内添加以下配置条目以拒绝用户、禁用本机身份验证并启用 WIF 来管理身份验证。</span><span class="sxs-lookup"><span data-stu-id="e408b-134">Add the following configuration entries within the **\<system.web>** elements to deny users, disable native authentication, and enable WIF to manage authentication.</span></span>  
  
    ```xml  
    <authorization>  
      <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4.  <span data-ttu-id="e408b-135">添加 \<system.webServer> 元素，用于为联合身份验证定义模块。</span><span class="sxs-lookup"><span data-stu-id="e408b-135">Add a **\<system.webServer>** element that defines the modules for federated authentication.</span></span> <span data-ttu-id="e408b-136">请注意，PublicKeyToken 特性必须与之前为 \<configSections > 条目添加的 PublicKeyToken 特性相同：</span><span class="sxs-lookup"><span data-stu-id="e408b-136">Note that the *PublicKeyToken* attribute must be the same as the *PublicKeyToken* attribute for the **\<configSections>** entries added earlier:</span></span>  
  
    ```xml  
    <system.webServer>  
      <modules>  
        <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
        <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      </modules>  
    </system.webServer>  
    ```  
  
5.  <span data-ttu-id="e408b-137">添加以下 Windows Identity Foundation 相关配置条目，并确保 ASP.NET 应用程序的 URL 和端口号与 \<audienceUris> 条目、\<wsFederation> 元素的“realm”特性和 \<wsFederation> 元素的“reply”特性中的值相匹配。</span><span class="sxs-lookup"><span data-stu-id="e408b-137">Add the following Windows Identity Foundation related configuration entries and ensure that your ASP.NET application’s URL and port number match the values in the **\<audienceUris>** entry, **realm** attribute of the **\<wsFederation>** element, and the **reply** attribute of the **\<wsFederation>** element.</span></span> <span data-ttu-id="e408b-138">还需确保“issuer”值与安全令牌服务 (STS) URL 相适应。</span><span class="sxs-lookup"><span data-stu-id="e408b-138">Also ensure that the **issuer** value fits your Security Token Service (STS) URL.</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration>  
            <audienceUris>  
                <add value="http://localhost:28503/" />  
            </audienceUris>  
            <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
                <trustedIssuers>  
                    <add thumbprint="1234567890ABCDEFGHIJKLMNOPQRSTUVWXYZ1234" name="YourSTSName" />  
                </trustedIssuers>   
            </issuerNameRegistry>  
            <certificateValidation certificateValidationMode="None" />  
        </identityConfiguration>  
    </system.identityModel>  
    <system.identityModel.services>  
        <federationConfiguration>  
            <cookieHandler requireSsl="false" />  
            <wsFederation passiveRedirectEnabled="true" issuer="http://localhost:13922/wsFederationSTS/Issue" realm="http://localhost:28503/" reply="http://localhost:28503/" requireHttps="false" />  
        </federationConfiguration>  
    </system.identityModel.services>  
    ```  
  
6.  <span data-ttu-id="e408b-139">将引用添加到 <xref:System.IdentityModel> 程序集。</span><span class="sxs-lookup"><span data-stu-id="e408b-139">Add reference to the <xref:System.IdentityModel> assembly.</span></span>  
  
7.  <span data-ttu-id="e408b-140">编译此解决方案，确保没有任何错误。</span><span class="sxs-lookup"><span data-stu-id="e408b-140">Compile the solution to make sure there are no errors.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="e408b-141">步骤 3 - 测试你的解决方案</span><span class="sxs-lookup"><span data-stu-id="e408b-141">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="e408b-142">在此步骤中，将测试为基于声明的身份验证配置的 ASP.NET Web 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="e408b-142">In this step you will test your ASP.NET Web Forms application configured for claims-based authentication.</span></span> <span data-ttu-id="e408b-143">若要执行基本测试，需添加用于在安全令牌服务 (STS) 颁发的令牌中显示声明的代码。</span><span class="sxs-lookup"><span data-stu-id="e408b-143">To perform a basic test, you will add code that displays claims in the token issued by the Security Token Service (STS).</span></span>  
  
#### <a name="to-test-your-aspnet-web-form-application-for-claims-based-authentication"></a><span data-ttu-id="e408b-144">为基于声明的身份验证测试 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="e408b-144">To test your ASP.NET Web Form application for claims-based authentication</span></span>  
  
1.  <span data-ttu-id="e408b-145">打开 TestApp 项目下的 Default.aspx 文件，并将现有标记替换为以下标记：</span><span class="sxs-lookup"><span data-stu-id="e408b-145">Open the **Default.aspx** file under the **TestApp** project and replace its existing markup with the following markup:</span></span>  
  
    ```  
    %@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
    <!DOCTYPE html>  
  
    <html>  
    <head id="Head1" runat="server">  
        <title></title>  
    </head>  
    <body>  
        <h1><asp:label ID="signedIn" runat="server" /></h1>  
        <asp:label ID="claimType" runat="server" />  
        <asp:label ID="claimValue" runat="server" />  
        <asp:label ID="claimValueType" runat="server" />  
        <asp:label ID="claimSubjectName" runat="server" />  
        <asp:label ID="claimIssuer" runat="server" />  
    </body>  
    </html>  
    ```  
  
2.  <span data-ttu-id="e408b-146">保存 Default.aspx 文件，然后打开名为 Default.aspx.cs 的代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="e408b-146">Save **Default.aspx**, and then open its code behind file named **Default.aspx.cs**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e408b-147">在解决方案资源管理器中，Default.aspx.cs 文件可能隐藏在 Default.aspx 文件下。</span><span class="sxs-lookup"><span data-stu-id="e408b-147">**Default.aspx.cs** may be hidden beneath **Default.aspx** in Solution Explorer.</span></span> <span data-ttu-id="e408b-148">如果 Default.aspx.cs 文件不可见，请单击文件旁边的三角形，展开 Default.aspx。</span><span class="sxs-lookup"><span data-stu-id="e408b-148">If **Default.aspx.cs** is not visible, expand **Default.aspx** by clicking on the triangle next to it.</span></span>  
  
3.  <span data-ttu-id="e408b-149">将 Default.aspx.cs 的 Page_Load 方法中的现有代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="e408b-149">Replace the existing code in the **Page_Load** method of **Default.aspx.cs** with the following code:</span></span>  
  
    ```csharp  
    using System;  
    using System.IdentityModel;  
    using System.Security.Claims;  
    using System.Threading;  
    using System.Web.UI;  
  
    namespace TestApp  
    {  
        public partial class _Default : System.Web.UI.Page  
        {  
            protected void Page_Load(object sender, EventArgs e)  
            {  
                ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
                if (claimsPrincipal != null)  
                {  
                    signedIn.Text = "You are signed in.";  
  
                    foreach (Claim claim in claimsPrincipal.Claims)  
                    {  
                        claimType.Text = claim.Type;  
                        claimValue.Text = claim.Value;  
                        claimValueType.Text = claim.ValueType;  
                        claimSubjectName.Text = claim.Subject.Name;  
                        claimIssuer.Text = claim.Issuer;  
                    }  
                }  
                else  
                {  
                    signedIn.Text = "You are not signed in.";  
                }  
            }  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="e408b-150">保存 Default.aspx.cs，并生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="e408b-150">Save **Default.aspx.cs**, and build the solution.</span></span>  
  
5.  <span data-ttu-id="e408b-151">按 F5 键运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="e408b-151">Run the solution by pressing the **F5** key.</span></span>  
  
6.  <span data-ttu-id="e408b-152">应当会看到在安全令牌服务颁发给你的令牌中显示声明的页面。</span><span class="sxs-lookup"><span data-stu-id="e408b-152">You should be presented with the page that displays the claims in the token that was issued to you by the Security Token Service.</span></span>
