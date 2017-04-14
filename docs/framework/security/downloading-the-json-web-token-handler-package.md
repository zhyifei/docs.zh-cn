---
title: "下载 JSON Web 标记处理程序包 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
caps.latest.revision: 3
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 3
---
# 下载 JSON Web 标记处理程序包
本主题讨论了如何在项目中下载和使用 JSON Web 标记处理程序。  
  
## 下载 JSON Web 标记处理程序  
 JSON Web 标记处理程序扩展可用作 NuGet 程序包，其将必要的程序集和引用添加到您的项目。  如果您还没有安装 NuGet，请转到 [nuget.org](http://nuget.org) 进行安装。  您可看到扩展的版本历史记录，方法是在 NuGet 上访问其页面：[NuGet 上的 JSON Web 标记处理程序](http://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)  
  
#### 使用程序包管理器 GUI 下载 JSON Web 标记处理程序  
  
1.  在 Visual Studio 中，在**解决方案资源管理器**中右击您的项目，然后选择**管理 NuGet 程序包**。  
  
2.  在 **管理 NuGet 程序包** 窗口，单击搜索框并输入 `JWT Token Handler` 并按 **Enter**。  
  
3.  从结果窗格中，单击第一个结果的**安装**按钮。  
  
4.  将要下载程序包。  在添加到您的项目之前会显示许可证验收对话框。  如果您同意许可条款，请单击“我接受”。  
  
5.  将下载并添加最新 JSON Web 标记处理程序集到项目中。  
  
#### 使用程序包管理器控制台下载 JSON Web 标记处理程序  
  
1.  在 Visual Studio 中，依次点击**工具**、**库程序包管理器**和 **程序包管理器控件台**。  
  
2.  显示**程序包管理器控制台**。  输入以下文本并按下 **Enter**：  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.Jwt  
    ```  
  
3.  将下载并添加最新 JSON Web 标记处理程序集到项目中。