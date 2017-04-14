---
title: "如何：转换传入声明 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2831d514-d9d8-4200-9192-954bb6da1126
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# 如何：转换传入声明
## 适用于  
  
-   Microsoft® Windows®标识基础\(WIF\)  
  
-   ASP.NET® Web窗体  
  
## 摘要  
 本帮助主题提供创建一个简单的声明感知ASP.NET Web窗体应用程序和转换传入的声明提供更详细的分步过程。  它说明如何测试应用程序还提供命令验证存在转换的声明，当应用程序运行时。  
  
## 内容  
  
-   用途  
  
-   概述  
  
-   步骤摘要  
  
-   步骤1 \-创建一个简单的ASP.NET Web窗体应用程序  
  
-   步骤2 \-使用自定义ClaimsAuthenticationManager，实现声明转换  
  
-   步骤3 \-测试您的解决方案  
  
## 用途  
  
-   配置为基于声明的身份验证的ASP.NET Web窗体应用程序  
  
-   通过添加控制器角色声明转换传入的声明  
  
-   测试ASP.NET Web窗体应用程序以查看其是否正常工作  
  
## 概述  
 WIF显示允许用户修改声明名为 <xref:System.Security.Claims.ClaimsAuthenticationManager> 的选件类，它们提供给一个依赖方\(RP\)应用程序。  <xref:System.Security.Claims.ClaimsAuthenticationManager> 为任务分离可用于身份验证和foundation应用程序代码之间的。  下面的示例演示如何将一个角色。有关在能由RP需要传入的 <xref:System.Security.Claims.ClaimsPrincipal>。  
  
## 步骤摘要  
  
-   步骤1 \-创建一个简单的ASP.NET Web窗体应用程序  
  
-   步骤2 \-使用自定义ClaimsAuthenticationManager，实现声明转换  
  
-   步骤3 \-测试您的解决方案  
  
## 步骤1 \-创建一个简单的ASP.NET Web窗体应用程序  
 在此步骤中，您将创建一个新ASP.NET Web窗体应用程序。  
  
#### 创建一个简单的ASP.NET应用程序  
  
1.  启动Visual Studio在高的模式下启动internet explorer。  
  
2.  在Visual Studio中，单击 **文件**，单击 **新建**，然后单击 **项目**。  
  
3.  在 **新建项目** 窗口中，单击 **ASP.NET Web窗体应用程序**。  
  
4.  在 **名称**，输入 `TestApp` 并按 **确定**。  
  
5.  右击 **TestApp** 项。**解决方案资源管理器**下，然后选择 **身份认证和访问**。  
  
6.  **身份认证和访问** 将出现窗口。  在 **提供程序**，选择下的 **测试您的本地开发STS的应用程序**，然后单击 **应用**。  
  
7.  在 *Default.aspx文件* 中，用下面的代码替换现有标记，然后保存文件:  
  
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
  
8.  打开代码隐藏文件名为 *Default.aspx.cs之后。* 用下面的代码替换现有代码，然后保存文件:  
  
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
  
## 步骤2 \-使用自定义ClaimsAuthenticationManager，实现声明转换  
 此步骤将重写在 <xref:System.Security.Claims.ClaimsAuthenticationManager> 选件类的默认功能添加管理员角色。传入的主体。  
  
#### 使用自定义ClaimsAuthenticationManager，实现声明转换  
  
1.  在Visual Studio中，右击该解决方案，单击 **添加**，然后单击 **新建项目**。  
  
2.  在 **添加新项目** 窗口中，从 **visual C\#** 模板中选择 **类库** 列表中，输入 `ClaimsTransformation`，然后按 **确定**。  新项目在解决方案文件夹中创建。  
  
3.  右击" **引用** 在 **ClaimsTransformation** 项目下的，然后单击 **添加引用**。  
  
4.  在 **引用管理器** 窗口中，选择" **System.IdentityModel**，然后单击 **确定**。  
  
5.  打开 **Class1.cs**，或者，如果不存在，右击 **ClaimsTransformation**，单击 **添加**，然后单击 **类别…**  
  
6.  将以下using指令添加到代码文件:  
  
    ```csharp  
    using System.Security.Claims;  
    using System.Security.Principal;  
    ```  
  
7.  添加以下选件类的代码文件中的和方法。  
  
    > [!WARNING]
    >  下面的代码仅供演示使用;确保验证您在成品代码所需的权限。  
  
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
  
8.  保存文件并生成 **ClaimsTransformation** 项目。  
  
9. 在您的 **TestApp** ASP.NET项目，请右击该引用，然后单击 **添加引用**。  
  
10. 在 **引用管理器** 窗口中，从左侧菜单中选择 **解决方案**，从填充的选项中选择 **ClaimsTransformation**，然后单击 **确定**。  
  
11. 在根 **Web.config** 文件，定位到 **\<system.identityModel\>** 项。  在 **\<identityConfiguration\>** 元素中，添加下面的行并保存文件:  
  
    ```  
    <claimsAuthenticationManager type="ClaimsTransformation.ClaimsTransformationModule, ClaimsTransformation" />  
    ```  
  
## 步骤3 \-测试您的解决方案  
 此步骤将测试ASP.NET Web窗体应用程序，并验证是否存在声明，当用户登录使用forms身份验证。  
  
#### 使用forms身份验证，测试对声明的ASP.NET Web窗体应用程序  
  
1.  按 **F5** 生成并运行该应用程序。  您应关注与 *Default.aspx。*  
  
2.  在 *Default.aspx页*，您应看到在包含 **颁发机构**、 **OriginalIssuer**、 **类型**、有关您的帐户的 **值**和 **ValueType** 声明信息的 **您的声明** 标题下的表。  应保持存在最后一行:  
  
    ||||||  
    |-|-|-|-|-|  
    |本地授权|本地授权|http:\/\/schemas.microsoft.com\/ws\/2008\/06\/identity\/claims\/role|Admin|http:\/\/www.w3.org\/2001\/XMLSchema\#string|