---
title: "如何：启用令牌重播检测 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5a9f5771-f5f6-4100-8501-406aa20d731a
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# 如何：启用令牌重播检测
## 适用于  
  
-   Microsoft® Windows®标识基础\(WIF\)  
  
-   ASP.NET® Web窗体  
  
## 摘要  
 本帮助主题提供启用在使用WIF的ASP.NET应用程序的标记重播检测提供详细分步过程。  它说明如何测试应用程序还提供命令验证标记重播检测启用。  本帮助主题没有创建的安全标记服务\(STS\)详细说明和使用随标识和Access工具的开发STS。  出于测试目的开发STS不执行实际身份验证并在只。  您需要安装标识和访问工具完成本帮助主题。  它可以从以下位置下载: [标识和Access工具](http://go.microsoft.com/fwlink/?LinkID=245849)  
  
## 内容  
  
-   用途  
  
-   概述  
  
-   步骤摘要  
  
-   步骤1 \-创建一个简单的ASP.NET Web窗体应用程序并启用重播检测  
  
-   步骤2 \-测试您的解决方案  
  
## 用途  
  
-   创建使用WIF和开发从标识的STS的简单ASP.NET应用程序并访问工具  
  
-   启用标记重播检测并验证它是否  
  
## 概述  
 重播攻击时，会发生客户端尝试验证到与客户端已使用的STS标记中的某个依赖方。  为了防止出现这种攻击，WIF包含重播检测缓存以前使用过的STS标记。  当启用，重播检测检查传入的请求的标记并验证是否已使用过该标记。  如果已使用该标记，请求拒绝，并 <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> 引发异常。  
  
 以下步骤演示了的配置更改启用重播检测。  
  
## 步骤摘要  
  
-   步骤1 \-创建一个简单的ASP.NET Web窗体应用程序并启用重播检测  
  
-   步骤2 \-测试您的解决方案  
  
## 步骤1 \-创建一个简单的ASP.NET Web窗体应用程序并启用重播检测  
 在此步骤中，您将创建一个新ASP.NET Web窗体应用程序并修改 *Web.config文件* 以启用重播检测。  
  
#### 创建一个简单的ASP.NET应用程序  
  
1.  启动Visual Studio并单击 **文件**、 **新建**然后 **项目**。  
  
2.  在 **新建项目** 窗口中，单击 **ASP.NET Web窗体应用程序**。  
  
3.  在 **名称**，输入 `TestApp` 并按 **确定**。  
  
4.  右击 **TestApp** 项。**解决方案资源管理器**下，然后选择 **身份认证和访问**。  
  
5.  **身份认证和访问** 将出现窗口。  在 **提供程序**，选择下的 **测试您的本地开发STS的应用程序**，然后单击 **应用**。  
  
6.  添加以下 **\<tokenReplayDetection\>** 元素到 *Web.config* 配置文件 **\<system.identityModel\>** 和 **\<identityConfiguration\>** 元素后的配置文件，如下所示：  
  
    ```  
    <system.identityModel>  
        <identityConfiguration>  
            <tokenReplayDetection enabled=”true”/>  
    ```  
  
## 步骤2 \-测试您的解决方案  
 在此步骤中，您将测试您的WIF启用ASP.NET应用程序中重播检测已启用。  
  
#### 测试对重播检测的WIF启用的ASP.NET应用程序  
  
1.  解决方案按 **F5** 键来运行。  您应关注与默认ASP.NET主页并自动验证使用用户名 *terry*，这是默认用户开发STS返回。  
  
2.  按浏览器的 **返回** 按钮。  您应关注与下面描述的 **在“\/”的服务器错误的应用程序** 页面：*ID1062: 重播检测到: 标记: “System.IdentityModel.Tokens.SamlSecurityToken”*，后跟 *AssertionId* 和 *颁发者*。  
  
     您将看到该错误页，因为类型 <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> 的已引发异常，在检测到标记重播。  此错误，因为您尝试重新发送初始POST请求，在首次存在该标记。  **返回** 按钮不会导致在后续请求的此行为到服务器。