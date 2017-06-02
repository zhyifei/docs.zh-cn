---
title: "下载验证颁发者名称注册表包 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
caps.latest.revision: 3
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 3
---
# 下载验证颁发者名称注册表包
本主题讨论了如何在项目中下载和使用验证颁发者名称注册表 \(VINR\)。  
  
## 下载验证颁发者名称注册表  
 VINR 可用作 NuGet 程序包，可将必要的程序集和引用添加到项目。  如果您还没有安装 NuGet，请转到 [nuget.org](http://nuget.org) 进行安装。  您可看到扩展的版本历史记录，方法是在 NuGet 上访问其页面：[NuGet 上的 Microsoft 验证问题名称注册表](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)  
  
#### 使用程序包管理器 GUI 下载验证颁发者名称注册表  
  
1.  在 Visual Studio 中，在**解决方案资源管理器**中右击您的项目，然后选择**管理 NuGet 程序包**。  
  
2.  在 **管理 NuGet 程序包** 窗口，单击搜索框并输入 `ValidatingIssuerNameRegistry` 并按 **Enter**。  
  
3.  从结果窗格中，单击第一个结果的**安装**按钮。  
  
4.  将要下载程序包。  在添加到您的项目之前会显示许可证验收对话框。  如果您同意许可条款，请单击“我接受”。  
  
5.  将下载并添加最新 VINR 程序集到项目中。  
  
#### 使用程序包管理器控制台下载验证颁发者名称注册表  
  
1.  在 Visual Studio 中，依次点击**工具**、**库程序包管理器**和 **程序包管理器控件台**。  
  
2.  显示**程序包管理器控制台**。  输入以下文本并按下 **Enter**：  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry  
    ```  
  
3.  将下载并添加最新 VINR 程序集到项目中。