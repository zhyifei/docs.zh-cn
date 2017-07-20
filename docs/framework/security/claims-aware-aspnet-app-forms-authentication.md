---
title: "如何：使用基于表单的身份验证生成声明感知 ASP.NET 应用程序 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 98a3e029-1a9b-4e0c-b5d0-29d3f23f5b15
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# 如何：使用基于表单的身份验证生成声明感知 ASP.NET 应用程序
## 适用于  
  
-   Microsoft® Windows®标识基础\(WIF\)  
  
-   ASP.NET® Web窗体  
  
## 摘要  
 本帮助主题提供创建使用forms身份验证的简单声明感知ASP.NET Web窗体应用程序提供了详细的分步过程。  它说明如何测试应用程序还提供命令验证存在声明，当用户登录使用forms身份验证时。  
  
## 内容  
  
-   用途  
  
-   概述  
  
-   步骤摘要  
  
-   步骤1 \-创建一个简单的ASP.NET Web窗体应用程序  
  
-   步骤2 \-使用forms身份验证，ASP.NET配置Web到声明的窗体应用程序  
  
-   步骤3 \-测试您的解决方案  
  
## 用途  
  
-   使用forms身份验证，该控件配置为要求的ASP.NET Web窗体应用程序  
  
-   测试ASP.NET Web窗体应用程序以查看其是否正常工作  
  
## 概述  
 .NET 4.5中，WIF及其基于要求的权限包括为framework的一部分。  以前，因此，如果要从ASP.NET用户的声明，需要安装WIF，然后转换为接口访问主体对象例如 `Thread.CurrentPrincipal` 或 `HttpContext.Current.User`。  现在，声明由这些主体对象自动提供服务。  
  
 因为forms身份验证的所有用户就自动具有声明与它们关联，forms身份验证受益于.NET 4.5的WIF的中。  您可以开始使用这些声明立即在使用forms身份验证的ASP.NET应用程序，因为此帮助主题演示。  
  
## 步骤摘要  
  
-   步骤1 \-创建一个简单的ASP.NET Web窗体应用程序  
  
-   步骤2 \-使用forms身份验证，ASP.NET配置Web到声明的窗体应用程序  
  
-   步骤3 \-测试您的解决方案  
  
## 步骤1 \-创建一个简单的ASP.NET Web窗体应用程序  
 在此步骤中，您将创建一个新ASP.NET Web窗体应用程序。  
  
#### 创建一个简单的ASP.NET应用程序  
  
1.  启动Visual Studio并单击 **文件**、 **新建**然后 **项目**。  
  
2.  在 **新建项目** 窗口中，单击 **ASP.NET Web窗体应用程序**。  
  
3.  在 **名称**，输入 `TestApp` 并按 **确定**。  
  
## 步骤2 \-使用forms身份验证，ASP.NET配置Web到声明的窗体应用程序  
 此步骤将添加配置条目添加到 *Web.config* 配置文件并编辑 *Default.aspx* 文件以显示帐户的声明信息。  
  
#### 使用forms身份验证，该控件配置为要求的ASP.NET应用程序  
  
1.  在 *Default.aspx文件* 中，用以下代码替换现有标记:  
  
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
  
     此步骤将一个GridView控件将填充forms身份验证检索的声明的 *Default.aspx页*。  
  
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
  
                if (claimsPrincipal != null)  
                {  
                    this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                    this.ClaimsGridView.DataBind();  
                }  
            }  
        }  
    }  
    ```  
  
     上面的代码将显示有关验证的用户的声明，其中包括forms身份验证来标识用户。  
  
## 步骤3 \-测试您的解决方案  
 此步骤将测试ASP.NET Web窗体应用程序，并验证是否存在声明，当用户登录使用forms身份验证。  
  
#### 使用forms身份验证，测试对声明的ASP.NET Web窗体应用程序  
  
1.  按 **F5** 生成并运行该应用程序。  您应关注与 *Default.aspx，*具有 **注册** 和 **登录** 链接在页的右上角。  单击**“注册”**。  
  
2.  在 **注册** 页中，创建一个用户帐户，然后单击 **注册**。  使用forms身份验证，您的帐户，将会创建，并将自动登录。  
  
3.  将重定向到主页后，您应看到在包含 **颁发机构**、 **OriginalIssuer**、 **类型**、有关您的帐户的 **值**和 **ValueType** 声明信息的 **您的声明** 标题下的表。