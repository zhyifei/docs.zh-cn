---
title: "如何：使用 WIF 生成声明感知 ASP.NET Web 窗体应用程序 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: efb264dd-f47b-49a9-85ee-9f45d4425765
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# 如何：使用 WIF 生成声明感知 ASP.NET Web 窗体应用程序
## 适用于  
  
-   Microsoft® Windows®标识基础\(WIF\)  
  
-   ASP.NET® Web窗体  
  
## 摘要  
 本帮助主题提供创建简单的声明感知ASP.NET Web窗体应用程序提供了详细的分步过程。  它说明如何测试对联合的身份验证的成功实现简单的声明感知ASP.NET Web窗体应用程序还提供命令。  本帮助主题没有创建的安全标记服务\(STS\)详细说明，并假定您已配置了STS。  
  
## 内容  
  
-   用途  
  
-   步骤摘要  
  
-   步骤1 \-创建一个简单的ASP.NET Web窗体应用程序  
  
-   步骤2 \-配置ASP.NET Web到基于声明的身份验证的窗体应用程序  
  
-   步骤3 \-测试您的解决方案  
  
## 用途  
  
-   配置ASP.NET Web到基于声明的身份验证的窗体应用程序  
  
-   测试成功的声明感知ASP.NET Web窗体应用程序  
  
## 步骤摘要  
  
-   步骤1 \-创建简单的ASP.NET Web窗体应用程序  
  
-   步骤2 \-配置ASP.NET Web到联合的身份验证的窗体应用程序  
  
-   步骤3 \-测试您的解决方案  
  
## 步骤1 \-创建一个简单的ASP.NET Web窗体应用程序  
 在此步骤中，您将创建一个新ASP.NET Web窗体应用程序。  
  
#### 创建一个简单的ASP.NET应用程序  
  
1.  启动Visual Studio并单击 **文件**、 **新建**然后 **项目**。  
  
2.  在 **新建项目** 窗口中，单击 **ASP.NET Web窗体应用程序**。  
  
3.  在 **名称**，输入 `TestApp` 并按 **确定**。  
  
## 步骤2 \-配置ASP.NET Web到基于声明的身份验证的窗体应用程序  
 此步骤将添加配置条目添加到ASP.NET Web窗体应用程序 *Web.config* 配置文件使其声明感知。  
  
#### 配置为基于声明的身份验证的ASP.NET应用程序  
  
1.  添加以下配置节项添加 **\<configuration\>** 到起始元素后的 *Web.config* 配置文件:  
  
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
  
4.  添加定义联合的身份验证模块的一个 **\<system.webServer\>** 元素。  请注意 *此时该* 属性必须为 **\<configSections\>** 项的 *PublicKeyToken* 属性前面添加的相同:  
  
    ```  
    <system.webServer>  
      <modules>  
        <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
        <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      </modules>  
    </system.webServer>  
    ```  
  
5.  添加以下Windows标识基础相关的配置项并确保您的ASP.NET应用程序的URL和端口号与 **\<audienceUris\>** 项、 **\<wsFederation\>** 元素的 **字段** 属性和 **\<wsFederation\>** 元素的 **答案** 属性的值。  还要确保 **颁发机构** 值适合您的安全标记服务\(STS\) URL。  
  
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
  
6.  添加对 [System.IdentityModel](assetId:///System.IdentityModel?qualifyHint=False&amp;autoUpgrade=True) 程序集。  
  
7.  生成解决方案确定存在错误。  
  
## 步骤3 \-测试您的解决方案  
 此步骤将测试配置的ASP.NET Web窗体应用程序对基于声明的身份验证。  若要执行基本测试，您将添加代码以在安全标记服务发出的标记的显示声明\(STS\)。  
  
#### 若要测试您的ASP.NET Web窗体对基于声明的身份验证的应用程序  
  
1.  打开 **Default.aspx** 文件在 **TestApp** 项目之下并用以下标记替换为现有标记:  
  
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
  
2.  保存 **Default.aspx**，则文件名为 **Default.aspx.cs**稍后再打开其代码。  
  
    > [!NOTE]
    >  **Default.aspx.cs** 可以在 **Default.aspx** 下隐藏在解决方案资源管理器中。  如果 **Default.aspx.cs** 不可见，请单击展开 **Default.aspx** 在该三角形在其旁边。  
  
3.  用下面的代码替换该 **Default.aspx.cs** **Page\_Load** 方案中的代码:  
  
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
  
4.  保存 **Default.aspx.cs**，生成解决方案。  
  
5.  解决方案按 **F5** 键来运行。  
  
6.  您应关注与显示在标记中声明问题可由安全标记服务的页。