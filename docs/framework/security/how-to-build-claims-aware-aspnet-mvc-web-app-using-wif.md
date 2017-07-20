---
title: "如何：使用 WIF 生成声明感知 ASP.NET MVC Web 应用程序 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0efb76bc-9f7b-4afe-be1c-2a57c917010b
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# 如何：使用 WIF 生成声明感知 ASP.NET MVC Web 应用程序
## 适用于  
  
-   Microsoft® Windows®标识基础\(WIF\)  
  
-   ASP.NET® MVC  
  
## 摘要  
 本帮助主题提供创建简单的声明感知ASP.NET MVC  Web 应用程序提供详细分步过程。  它还提供有关如何测试基于声明的身份验证的成功实现简单的声明感知ASP.NET MVC  Web 应用程序。  本帮助主题没有创建的安全标记服务\(STS\)详细说明，并假定您已配置了STS。  
  
## 内容  
  
-   用途  
  
-   步骤摘要  
  
-   步骤1 \-创建简单ASP.NET MVC应用程序  
  
-   步骤2 \-配置对基于声明的身份验证的ASP.NET MVC应用程序  
  
-   步骤3 \-测试您的解决方案  
  
-   相关项  
  
## 用途  
  
-   配置ASP.NET MVC基于声明的身份验证的 Web 应用程序  
  
-   测试成功的声明感知ASP.NET MVC  Web 应用程序  
  
## 步骤摘要  
  
-   步骤1 \-创建简单ASP.NET MVC应用程序  
  
-   步骤2 \-配置对基于声明的身份验证的ASP.NET MVC应用程序  
  
-   步骤3 \-测试您的解决方案  
  
## 步骤1 \-创建简单ASP.NET MVC应用程序  
 在此步骤中，您将创建一个新ASP.NET MVC应用程序。  
  
#### 创建简单ASP.NET MVC应用程序  
  
1.  启动Visual Studio并单击 **文件**、 **新建**然后 **项目**。  
  
2.  在 **新建项目** 窗口中，单击 **ASP.NET MVC 3  Web 应用程序**。  
  
3.  在 **名称**，输入 `TestApp` 并按 **确定**。  
  
4.  在 **新ASP.NET MVC 3项目** 对话框中，选择 **Internet 应用程序** 从可用模板，确保 **视图引擎** 设置为 **razor**，然后单击 **确定**。  
  
5.  在新项目中打开时，请右击该 **解决方案资源管理器** 的 **TestApp** 项目并选择 **属性** 选项。  
  
6.  在项目的属性页上，单击 **Web** 选项在左侧并确保 **使用本地 IIS Web 服务器** 选项。  
  
## 步骤2 \-配置对基于声明的身份验证的ASP.NET MVC应用程序  
 此步骤将添加配置条目添加到ASP.NET MVC  Web 应用程序 *Web.config* 配置文件使其声明感知。  
  
#### 配置为基于声明的身份验证的ASP.NET MVC应用程序  
  
1.  添加以下配置节定义添加到 *Web.config* 配置文件。  这些定义Windows标识基础所需的配置节。  添加在 **\<configuration\>** 开放式元素的后面定义:  
  
    ```xml  
    <configSections>  
        <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
        <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2.  添加启用对应用程序的联邦元数据访问的一个 **\<location\>** 元素:  
  
    ```xml  
    <location path="FederationMetadata">  
        <system.web>  
            <authorization>  
                <allow users="*" />  
            </authorization>  
        </system.web>  
    </location>  
    ```  
  
3.  将 **\<system.web\>** 元素中的以下配置条目拒绝用户，禁用本机身份验证，并使WIF管理身份验证。  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4.  添加以下Windows标识基础相关的配置项并确保您的ASP.NET应用程序的URL和端口号与 **\<audienceUris\>** 项、 **\<wsFederation\>** 元素的 **字段** 属性和 **\<wsFederation\>** 元素的 **答案** 属性的值。  还要确保 **颁发机构** 值适合您的安全标记服务\(STS\) URL。  
  
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
  
5.  添加对 [System.IdentityModel](assetId:///System.IdentityModel?qualifyHint=False&amp;autoUpgrade=True) 程序集。  
  
6.  生成解决方案确定存在错误。  
  
## 步骤3 \-测试您的解决方案  
 此步骤将测试配置的ASP.NET MVC  Web 应用程序基于声明的身份验证的。  若要执行基本的测试将添加简单的代码在安全标记服务发出的标记的显示声明\(STS\)。  
  
#### 测试对基于声明的身份验证的ASP.NET MVC应用程序  
  
1.  在 **解决方案资源管理器**，展开 **控制器** 文件夹并在编辑器中打开 *HomeController.cs文件*。  将以下代码添加到 **索引** 方法:  
  
    ```csharp  
    public ActionResult Index()  
    {  
        ViewBag.ClaimsIdentity = Thread.CurrentPrincipal.Identity;  
  
        return View();  
    }  
  
    ```  
  
2.  在 **解决方案资源管理器** 展开 **视图** 然后 **主页** 文件夹并在编辑器中打开 *Index.cshtml文件*。  删除其内容并添加以下标记:  
  
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
  
3.  解决方案按 **F5** 键来运行。  
  
4.  您应关注与显示在标记中声明问题可由安全标记服务的页。  
  
## 相关项  
  
-   [如何：使用 WIF 生成声明感知 ASP.NET Web 窗体应用程序](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)