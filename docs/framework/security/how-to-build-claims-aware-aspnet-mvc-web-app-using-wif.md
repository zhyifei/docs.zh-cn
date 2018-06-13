---
title: 如何：使用 WIF 生成声明感知 ASP.NET MVC Web 应用程序
ms.date: 03/30/2017
ms.assetid: 0efb76bc-9f7b-4afe-be1c-2a57c917010b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 146724f31e1d09f09f94d102366539dc79ddfe02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33399144"
---
# <a name="how-to-build-claims-aware-aspnet-mvc-web-application-using-wif"></a><span data-ttu-id="6ccc2-102">如何：使用 WIF 生成声明感知 ASP.NET MVC Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="6ccc2-102">How To: Build Claims-Aware ASP.NET MVC Web Application Using WIF</span></span>
## <a name="applies-to"></a><span data-ttu-id="6ccc2-103">适用于</span><span class="sxs-lookup"><span data-stu-id="6ccc2-103">Applies To</span></span>  
  
-   <span data-ttu-id="6ccc2-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="6ccc2-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="6ccc2-105">ASP.NET® MVC</span><span class="sxs-lookup"><span data-stu-id="6ccc2-105">ASP.NET® MVC</span></span>  
  
## <a name="summary"></a><span data-ttu-id="6ccc2-106">总结</span><span class="sxs-lookup"><span data-stu-id="6ccc2-106">Summary</span></span>  
 <span data-ttu-id="6ccc2-107">本操作说明提供了创建简单的声明感知 ASP.NET MVC Web 应用程序的详细分步过程。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-107">This How-To provides detailed step-by-step procedures for creating simple claims-aware ASP.NET MVC web application.</span></span> <span data-ttu-id="6ccc2-108">还提供关于如何测试简单的声明感知 ASP.NET MVC Web 应用程序以确保成功实现基于声明的身份验证的说明。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-108">It also provides instructions how to test the simple claims-aware ASP.NET MVC web application for successful implementation of claims-based authentication.</span></span> <span data-ttu-id="6ccc2-109">本操作说明不包括如何创建安全令牌服务 (STS) 的详细说明，且假定你已配置 STS。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and assumes you have already configured an STS.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="6ccc2-110">内容</span><span class="sxs-lookup"><span data-stu-id="6ccc2-110">Contents</span></span>  
  
-   <span data-ttu-id="6ccc2-111">目标</span><span class="sxs-lookup"><span data-stu-id="6ccc2-111">Objectives</span></span>  
  
-   <span data-ttu-id="6ccc2-112">步骤摘要</span><span class="sxs-lookup"><span data-stu-id="6ccc2-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="6ccc2-113">步骤 1 – 创建简单的 ASP.NET MVC 应用程序</span><span class="sxs-lookup"><span data-stu-id="6ccc2-113">Step 1 – Create Simple ASP.NET MVC Application</span></span>  
  
-   <span data-ttu-id="6ccc2-114">步骤 2 – 为基于声明的身份验证配置 ASP.NET MVC 应用程序</span><span class="sxs-lookup"><span data-stu-id="6ccc2-114">Step 2 – Configure ASP.NET MVC Application for Claims-Based Authentication</span></span>  
  
-   <span data-ttu-id="6ccc2-115">步骤 3 - 测试你的解决方案</span><span class="sxs-lookup"><span data-stu-id="6ccc2-115">Step 3 – Test Your Solution</span></span>  
  
-   <span data-ttu-id="6ccc2-116">相关项</span><span class="sxs-lookup"><span data-stu-id="6ccc2-116">Related Items</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="6ccc2-117">目标</span><span class="sxs-lookup"><span data-stu-id="6ccc2-117">Objectives</span></span>  
  
-   <span data-ttu-id="6ccc2-118">为基于声明的身份验证配置 ASP.NET MVC Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="6ccc2-118">Configure ASP.NET MVC web application for claims-based authentication</span></span>  
  
-   <span data-ttu-id="6ccc2-119">测试成功的声明感知 ASP.NET MVC Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="6ccc2-119">Test successful claims-aware ASP.NET MVC web application</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="6ccc2-120">步骤摘要</span><span class="sxs-lookup"><span data-stu-id="6ccc2-120">Summary of Steps</span></span>  
  
-   <span data-ttu-id="6ccc2-121">步骤 1 – 创建简单的 ASP.NET MVC 应用程序</span><span class="sxs-lookup"><span data-stu-id="6ccc2-121">Step 1 – Create Simple ASP.NET MVC Application</span></span>  
  
-   <span data-ttu-id="6ccc2-122">步骤 2 – 为基于声明的身份验证配置 ASP.NET MVC 应用程序</span><span class="sxs-lookup"><span data-stu-id="6ccc2-122">Step 2 – Configure ASP.NET MVC Application for Claims-Based Authentication</span></span>  
  
-   <span data-ttu-id="6ccc2-123">步骤 3 - 测试你的解决方案</span><span class="sxs-lookup"><span data-stu-id="6ccc2-123">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-simple-aspnet-mvc-application"></a><span data-ttu-id="6ccc2-124">步骤 1 – 创建简单的 ASP.NET MVC 应用程序</span><span class="sxs-lookup"><span data-stu-id="6ccc2-124">Step 1 – Create Simple ASP.NET MVC Application</span></span>  
 <span data-ttu-id="6ccc2-125">在此步骤中，将创建一个新的 ASP.NET MVC 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-125">In this step, you will create a new ASP.NET MVC application.</span></span>  
  
#### <a name="to-create-simple-aspnet-mvc-application"></a><span data-ttu-id="6ccc2-126">创建简单的 ASP.NET MVC 应用程序</span><span class="sxs-lookup"><span data-stu-id="6ccc2-126">To create simple ASP.NET MVC application</span></span>  
  
1.  <span data-ttu-id="6ccc2-127">启动 Visual Studio，然后依次单击“文件”、“新建”和“项目”。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-127">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="6ccc2-128">在“新建项目”窗口中，单击“ASP.NET MVC 3 Web 应用程序”。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-128">In the **New Project** window, click **ASP.NET MVC 3 Web Application**.</span></span>  
  
3.  <span data-ttu-id="6ccc2-129">在“名称”中，输入 `TestApp`，然后按“确定”。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-129">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4.  <span data-ttu-id="6ccc2-130">在“新建 ASP.NET MVC 3 项目”对话框中，从可用模板中选择“Internet 应用程序”，确保将“视图引擎”设置为“Razor”，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-130">In the **New ASP.NET MVC 3 Project** dialog, select **Internet Application** from the available templates, ensure **View Engine** is set to **Razor**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="6ccc2-131">打开新建项目时，右键单击“解决方案资源管理器”中的“TestApp”项目，然后选择“属性面板”选项。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-131">When the new project opens, right-click the **TestApp** project in **Solution Explorer** and select the **Properties** option.</span></span>  
  
6.  <span data-ttu-id="6ccc2-132">在项目的属性页上，单击左侧的“Web”选项卡，并确保选择了“使用本地 IIS Web 服务器”选项。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-132">On the project’s properties page, click on the **Web** tab on the left and ensure that the **Use Local IIS Web Server** option is selected.</span></span>  
  
## <a name="step-2--configure-aspnet-mvc-application-for-claims-based-authentication"></a><span data-ttu-id="6ccc2-133">步骤 2 – 为基于声明的身份验证配置 ASP.NET MVC 应用程序</span><span class="sxs-lookup"><span data-stu-id="6ccc2-133">Step 2 – Configure ASP.NET MVC Application for Claims-Based Authentication</span></span>  
 <span data-ttu-id="6ccc2-134">在此步骤中，将配置条目添加到 ASP.NET MVC Web 应用程序的 Web.config 配置文件中，以使其可感知声明。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-134">In this step you will add configuration entries to the *Web.config* configuration file of your ASP.NET MVC web application to make it claims-aware.</span></span>  
  
#### <a name="to-configure-aspnet-mvc-application-for-claims-based-authentication"></a><span data-ttu-id="6ccc2-135">为基于声明的身份验证配置 ASP.NET MVC 应用程序</span><span class="sxs-lookup"><span data-stu-id="6ccc2-135">To configure ASP.NET MVC application for claims-based authentication</span></span>  
  
1.  <span data-ttu-id="6ccc2-136">将以下配置节定义添加到 Web.config 配置文件。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-136">Add the following configuration section definitions to the *Web.config* configuration file.</span></span> <span data-ttu-id="6ccc2-137">它们定义 Windows Identity Foundation 所需的配置节。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-137">These define configuration sections required by Windows Identity Foundation.</span></span> <span data-ttu-id="6ccc2-138">将定义紧随添加在 \<configuration> 起始元素后：</span><span class="sxs-lookup"><span data-stu-id="6ccc2-138">Add the definitions immediately after the **\<configuration>** opening element:</span></span>  
  
    ```xml  
    <configSections>  
        <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
        <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2.  <span data-ttu-id="6ccc2-139">添加 \<location> 元素，用于启用对应用程序的联合元数据的访问权限：</span><span class="sxs-lookup"><span data-stu-id="6ccc2-139">Add a **\<location>** element that enables access to the application’s federation metadata:</span></span>  
  
    ```xml  
    <location path="FederationMetadata">  
        <system.web>  
            <authorization>  
                <allow users="*" />  
            </authorization>  
        </system.web>  
    </location>  
    ```  
  
3.  <span data-ttu-id="6ccc2-140">在 \<system.web> 元素内添加以下配置条目以拒绝用户、禁用本机身份验证并启用 WIF 来管理身份验证。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-140">Add the following configuration entries within the **\<system.web>** elements to deny users, disable native authentication, and enable WIF to manage authentication.</span></span>  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4.  <span data-ttu-id="6ccc2-141">添加以下 Windows Identity Foundation 相关配置条目，并确保 ASP.NET 应用程序的 URL 和端口号与 \<audienceUris> 条目、\<wsFederation> 元素的“realm”特性和 \<wsFederation> 元素的“reply”特性中的值相匹配。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-141">Add the following Windows Identity Foundation related configuration entries and ensure that your ASP.NET application’s URL and port number match the values in the **\<audienceUris>** entry, **realm** attribute of the **\<wsFederation>** element, and the **reply** attribute of the **\<wsFederation>** element.</span></span> <span data-ttu-id="6ccc2-142">还需确保“issuer”值与安全令牌服务 (STS) URL 相适应。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-142">Also ensure that the **issuer** value fits your Security Token Service (STS) URL.</span></span>  
  
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
  
5.  <span data-ttu-id="6ccc2-143">将引用添加到 <xref:System.IdentityModel> 程序集。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-143">Add reference to the <xref:System.IdentityModel> assembly.</span></span>  
  
6.  <span data-ttu-id="6ccc2-144">编译此解决方案，确保没有任何错误。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-144">Compile the solution to make sure there are errors.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="6ccc2-145">步骤 3 - 测试你的解决方案</span><span class="sxs-lookup"><span data-stu-id="6ccc2-145">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="6ccc2-146">在此步骤中，将测试为基于声明的身份验证配置的 ASP.NET MVC Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-146">In this step you will test your ASP.NET MVC web application configured for claims-based authentication.</span></span> <span data-ttu-id="6ccc2-147">若要执行基本测试，需添加用于在安全令牌服务 (STS) 颁发的令牌中显示声明的简单代码。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-147">To perform basic test you will add simple code that displays claims in the token issued by the Security Token Service (STS).</span></span>  
  
#### <a name="to-test-your-aspnet-mvc-application-for-claims-based-authentication"></a><span data-ttu-id="6ccc2-148">为基于声明的身份验证测试 ASP.NET MVC 应用程序</span><span class="sxs-lookup"><span data-stu-id="6ccc2-148">To test your ASP.NET MVC application for claims-based authentication</span></span>  
  
1.  <span data-ttu-id="6ccc2-149">在“解决方案资源管理器”中，展开 Controllers 文件夹，并在编辑器中打开 HomeController.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-149">In the **Solution Explorer**, expand the **Controllers** folder and open *HomeController.cs* file in the editor.</span></span> <span data-ttu-id="6ccc2-150">将以下代码添加到 Index 方法中：</span><span class="sxs-lookup"><span data-stu-id="6ccc2-150">Add the following code to the **Index** method:</span></span>  
  
    ```csharp  
    public ActionResult Index()  
    {  
        ViewBag.ClaimsIdentity = Thread.CurrentPrincipal.Identity;  
  
        return View();  
    }  
    ```  
  
2.  <span data-ttu-id="6ccc2-151">在“解决方案资源管理器”中，依次展开 Views 和 Home 文件夹，然后在编辑器中打开 Index.cshtml 文件。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-151">In the **Solution Explorer** expand **Views** and then **Home** folders and open *Index.cshtml* file in the editor.</span></span> <span data-ttu-id="6ccc2-152">删除其内容并添加以下标记：</span><span class="sxs-lookup"><span data-stu-id="6ccc2-152">Delete its contents and add the following markup:</span></span>  
  
    ```html  
    @{  
        ViewBag.Title = "Home Page";  
    }  
  
    <h2>Welcome: @ViewBag.ClaimsIdentity.Name</h2>  
    <h3>Values from Identity</h3>  
    <table>  
        <tr>  
            <th>  
                IsAuthenticated   
            </th>  
            <td>  
                @ViewBag.ClaimsIdentity.IsAuthenticated   
            </td>  
        </tr>  
        <tr>  
            <th>  
                Name   
            </th>          
            <td>  
                @ViewBag.ClaimsIdentity.Name  
            </td>          
        </tr>  
    </table>  
    <h3>Claims from ClaimsIdentity</h3>  
    <table>  
        <tr>  
            <th>  
                Claim Type  
            </th>  
            <th>  
                Claim Value  
            </th>  
            <th>  
                Value Type  
            </th>  
            <th>  
                Subject Name  
            </th>          
            <th>  
                Issuer Name  
            </th>          
        </tr>  
            @foreach (System.Security.Claims.Claim claim in ViewBag.ClaimsIdentity.Claims ) {  
        <tr>  
            <td>  
                @claim.Type  
            </td>  
            <td>  
                @claim.Value  
            </td>  
            <td>  
                @claim.ValueType  
            </td>  
            <td>  
                @claim.Subject.Name  
            </td>  
            <td>  
                @claim.Issuer  
            </td>  
        </tr>  
    }  
    </table>  
    ```  
  
3.  <span data-ttu-id="6ccc2-153">按 F5 键运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-153">Run the solution by pressing the **F5** key.</span></span>  
  
4.  <span data-ttu-id="6ccc2-154">应当会看到在安全令牌服务颁发给你的令牌中显示声明的页面。</span><span class="sxs-lookup"><span data-stu-id="6ccc2-154">You should be presented with the page that displays the claims in the token that was issued to you by Security Token Service.</span></span>  
  
## <a name="related-items"></a><span data-ttu-id="6ccc2-155">相关项</span><span class="sxs-lookup"><span data-stu-id="6ccc2-155">Related Items</span></span>  
  
-   [<span data-ttu-id="6ccc2-156">如何：使用 WIF 生成声明感知 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="6ccc2-156">How To: Build Claims-Aware ASP.NET Web Forms Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)
