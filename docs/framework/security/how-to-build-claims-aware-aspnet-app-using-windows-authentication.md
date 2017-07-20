---
title: "如何：使用 Windows 身份验证生成声明感知 ASP.NET 应用程序 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 11c53d9d-d34a-44b4-8b5e-22e3eaeaee93
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# 如何：使用 Windows 身份验证生成声明感知 ASP.NET 应用程序
## 适用于  
  
-   Microsoft® Windows®标识基础\(WIF\)  
  
-   ASP.NET® Web窗体  
  
## 摘要  
 本帮助主题提供创建使用Windows身份验证的简单声明感知ASP.NET Web窗体应用程序提供了详细的分步过程。  它说明如何测试应用程序还提供命令验证存在声明使用Windows身份验证时，那么，当用户登录。  
  
## 内容  
  
-   用途  
  
-   概述  
  
-   步骤摘要  
  
-   步骤1 \-创建一个简单的ASP.NET Web窗体应用程序  
  
-   步骤2 \-使用Windows身份验证，ASP.NET配置Web到声明的窗体应用程序  
  
-   步骤3 \-测试您的解决方案  
  
## 用途  
  
-   使用Windows身份验证，该控件配置为要求的ASP.NET Web窗体应用程序  
  
-   测试ASP.NET Web窗体应用程序以查看其是否正常工作  
  
## 概述  
 .NET 4.5中，WIF及其基于要求的权限包括为framework的一部分。  以前，因此，如果要从ASP.NET用户的声明，需要安装WIF，然后转换为接口访问主体对象例如 `Thread.CurrentPrincipal` 或 `HttpContext.Current.User`。  现在，声明由这些主体对象自动提供服务。  
  
 因为Windows凭据验证的所有用户就自动具有声明与它们关联，Windows身份验证受益于.NET 4.5的WIF的中。  您可以开始使用这些声明立即在使用Windows身份验证的ASP.NET应用程序，因为此帮助主题演示。  
  
## 步骤摘要  
  
-   步骤1 \-创建一个简单的ASP.NET Web窗体应用程序  
  
-   步骤2 \-使用Windows身份验证，ASP.NET配置Web到声明的窗体应用程序  
  
-   步骤3 \-测试您的解决方案  
  
## 步骤1 \-创建一个简单的ASP.NET Web窗体应用程序  
 在此步骤中，您将创建一个新ASP.NET Web窗体应用程序。  
  
#### 创建一个简单的ASP.NET应用程序  
  
1.  启动Visual Studio，然后单击 **文件**、 **新建**然后 **项目**。  
  
2.  在 **新建项目** 窗口中，单击 **ASP.NET Web窗体应用程序**。  
  
3.  在 **名称**，输入 `TestApp` 并按 **确定**。  
  
4.  在 **TestApp** 创建项目之后，请单击它在 **解决方案资源管理器**。  项目的属性将出现在 **属性** 窗格中 **解决方案资源管理器**下。  设置 **Windows 身份验证** 属性设置为 **已启用**。  
  
    > [!WARNING]
    >  默认情况下Windows身份验证在新的ASP.NET应用程序禁用，因此，必须手动启用它。  
  
## 步骤2 \-使用Windows身份验证，ASP.NET配置Web到声明的窗体应用程序  
 此步骤将添加配置条目添加到 *Web.config* 配置文件并修改 *Default.aspx* 文件显示帐户的声明信息。  
  
#### 使用Windows身份验证，该控件配置为要求的ASP.NET应用程序  
  
1.  在 **TestApp** 项目的 *Default.aspx文件*，用以下代码替换现有标记:  
  
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
  
     此步骤将一个GridView控件将填充Windows身份验证检索的声明的 *Default.aspx页*。  
  
2.  保存 *Default.aspx* 文件，然后打开其代码隐藏文件名为 *Default.aspx.cs*。  用下面的代码替换现有的代码:  
  
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
  
     上面的代码将显示有关验证的用户的声明。  
  
3.  若要更改应用程序的身份验证类型，请修改 **\<authentication\>** 块在项目的根 *Web.config文件的* **\<system.web\>** 部分，使其只包含以下配置:  
  
    ```  
    <authentication mode="Windows" />  
    ```  
  
4.  最后，修改 **\<authorization\>** 块在同一个 *Web.config文件的* 节 **\<system.web\>** 强制身份验证:  
  
    ```  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    ```  
  
## 步骤3 \-测试您的解决方案  
 此步骤将测试ASP.NET Web窗体应用程序，并验证是否存在声明，当用户登录使用Windows身份验证。  
  
#### 使用Windows身份验证，测试对声明的ASP.NET Web窗体应用程序  
  
1.  按 **F5** 生成并运行该应用程序。  您应关注与 *Default.aspx，并且，*如果您的Windows帐户名\(包括域名\)应已经显示为页的右上角的验证的用户。  页的内容应包含查询结果从您的Windows帐户检索的声明。