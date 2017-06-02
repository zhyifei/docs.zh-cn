---
title: "如何：使用 WIF 显示登录状态 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4d1174e4-5397-4962-9a5f-3b1ad7b3fc14
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# 如何：使用 WIF 显示登录状态
## 适用于  
  
-   Microsoft® Windows® 标识基础 \(WIF\) 4.5  
  
-   ASP.NET® Web 窗体  
  
## 摘要  
 本主题描述如何以 WIF 启用 ASP.NET 应用程序的登录状态。  WIF 为使应用提供机制声明感知和管理的身份验证和授权应用程序资源。  
  
## 内容  
  
-   概述  
  
-   步骤摘要  
  
-   步骤 1 \- 安装标识并访问扩展  
  
-   步骤 2 \- 创建关系方 ASP.NET 应用程序  
  
-   步骤 3 \- 使本地开发 STS 验证用户  
  
-   步骤 4 \- 显示登录状态修改 ASP.NET 应用程序  
  
-   步骤 5 \- 测试 WIF 在 ASP.NET 应用程序和之间的集成  
  
## 概述  
 本主题演示如何创建一个简单的应用程序使用和声明感知 WIF 如何轻松显示是否用户登录。  以下步骤使用附带标识并访问 Visual Studio 扩展的本地开发 STS。  本地开发 STS 用于测试和开发环境利用提供集成声明简单的方法为应用程序。  不应使用生产环境中，因为它不执行实际身份验证，并且不需要这些凭据。  但是，实际使用身份验证，如下面的步骤所需代码相同一种尚未投产使用的应用程序。  
  
## 步骤摘要  
  
-   步骤 1 \- 安装标识并访问扩展  
  
-   步骤 2 \- 创建关系方 ASP.NET 应用程序  
  
-   步骤 3 \- 使本地开发 STS 验证用户  
  
-   步骤 4 \- 显示登录状态修改 ASP.NET 应用程序  
  
-   步骤 5 \- 测试 WIF 在 ASP.NET 应用程序和之间的集成  
  
## 步骤 1 \- 安装标识并访问扩展  
 此步骤描述如何配置标识和访问扩展到 Visual Studio 2012。  此自动化扩展配置应用程序进程的 STS 通信终结点。  
  
#### 安装和访问标识扩展  
  
1.  在高的模式启动 Visual Studio 为管理员。  
  
2.  在 Visual Studio 中，单击 **工具** 然后单击 **扩展管理器**。  **扩展管理器** 窗口。  
  
3.  在 **扩展管理器**中，从左侧 **联机扩展** 单击菜单，然后选择 **Visual Studio 库**。  
  
4.  在 **Extension Manager** 的右上角搜索 *身份认证和访问*。  
  
5.  **身份认证和访问** 项会出现在搜索结果。  单击它，然后单击 **下载**。  
  
6.  **下载并安装** 对话框。  如果授予许可条款，请单击 **安装**。  
  
7.  **身份认证和访问** 在扩展安装完成时，请重新启动在管理员模式的 Visual Studio。  
  
## 步骤 2 \- 创建关系方 ASP.NET 应用程序  
 此步骤说明如何创建与集成 WIF 的关系方 ASP.NET Web 窗体应用程序。  
  
#### 创建一个简单的 ASP.NET 应用程序  
  
1.  启动 Visual Studio 并单击 **文件**，**新建**和 **项目**。  
  
2.  在 **新建项目** 窗口中，单击 **ASP.NET Web 窗体应用程序**。  
  
3.  在 **名称**中，键入 `TestApp` 并按 **确定**。  
  
## 步骤 3 \- 使本地开发 STS 验证用户  
 此步骤描述如何在应用程序的本地开发 STS。  使用 Visual Studio 中，标识和访问本地扩展的开发 STS 启用。  
  
#### 在 ASP.NET 应用程序的本地开发 STS  
  
1.  在 Visual Studio 中，右击 **TestApp** 项目下的 **解决方案资源管理器**，然后选择 **身份认证和访问**。  
  
2.  **身份认证和访问** 窗口。  在 **提供程序**下，选择 **测试与本地开发 STS 的应用程序**，然后单击 **应用**。  
  
## 步骤 4 \- 显示登录状态修改 ASP.NET 应用程序  
 此步骤说明如何修改 ASP.NET 应用程序中动态显示当前用户是否登录。  一旦 STS 提供程序配置，WIF 处理传入的声明。  现在需要配置应用程序代码演示身份验证的结果。  
  
#### 若要查看中登录状态  
  
1.  在 Visual Studio 中，打开 **Default.aspx** 文件。**TestApp** 项目下。  
  
2.  用下面的标记替换 **Default.aspx** 文件中的现有标记：  
  
    ```  
    <%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
    <!DOCTYPE html>  
  
    <html>  
    <head runat="server">  
        <title>Logged In Status</title>  
    </head>  
    <body>  
        <asp:label ID="myLabel" runat="server" />  
    </body>  
    </html>  
    ```  
  
3.  保存 **Default.aspx**，该文件名为 **Default.aspx.cs**后再打开其代码。  
  
    > [!NOTE]
    >  **Default.aspx.cs** 可以在"解决方案资源管理器"的 **Default.aspx** 中隐藏。  如果 **Default.aspx.cs** 不可见，请单击展开 **Default.aspx** 在中它旁边的三角形  
  
4.  用下面的代码替换 **Default.aspx.cs** 中的现有代码：  
  
    ```csharp  
    using System;  
    using System.Web.UI;  
    using System.Security.Claims;  
  
    namespace TestApp  
    {  
        protected void Page_Load(object sender, EventArgs e)  
        {  
            ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
            if (claimsPrincipal != null)  
            {  
                myLabel.Text = "You are signed in.";  
            }  
            else  
            {  
                myLabel.Text = "You are not signed in.";  
            }  
        }  
    }  
    ```  
  
5.  保存 **Default.aspx.cs**，并生成应用程序。  
  
## 步骤 5 \- 测试 WIF 在 ASP.NET 应用程序和之间的集成  
 此步骤介绍如何测试。WIF 应用程序和 ASP.NET 之间的集成。  
  
#### WIF 和 ASP.NET 之间的集成测试。  
  
1.  在 Visual Studio 中，按 **F5** 开始调试应用程序。  如果错误没有找到，新的浏览器窗口中打开。  
  
2.  您可能注意浏览器提示会将请求重定向到 STS，然后打开 Default.aspx 页。  WIF 如果正确配置，您应会看到站点显示以下文本：**“您已登录”**。