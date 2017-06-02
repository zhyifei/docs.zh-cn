---
title: "在 .NET Framework 4.5 安装期间减少系统重新启动 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - ".NET Framework, 减少系统重新启动"
  - "安装 [.NET Framework]"
  - "安装 .NET Framework"
ms.assetid: 7aa8cb72-dee9-4716-ac54-b17b9ae8218f
caps.latest.revision: 18
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 18
---
# 在 .NET Framework 4.5 安装期间减少系统重新启动
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 安装程序使用 [重新启动管理器r](http://go.microsoft.com/fwlink/?LinkId=231425)来防止安装期间的可能系统重启。  如果您的应用程序安装程序安装 .NET framework，它可以与“重新启动管理器”进行交互，以利用此功能的。  有关详细信息，请参阅[如何：获取 .NET Framework 4.5 安装程序的进度](../../../docs/framework/deployment/how-to-get-progress-from-the-dotnet-installer.md)。  
  
## 重新启动的原因  
 如果安装 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 时使用 .NET Framework 4 应用程序，则要求重新启动系统。  这是因为 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 会替换 .NET Framework 4 文件，并且安装期间需要这些文件可用。  在很多情况下，通过抢先式检测和关闭正在使用的 .NET Framework 4 应用程序可以阻止重新启动。  但是，有些系统应用程序不应关闭。  在这些情况下，重新启动是无法避免的。  
  
## 最终用户体验  
 执行 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 的完整安装的最终用户有机会避免系统重新启动，如果该安装程序检测到 .NET Framework 4 应用程序正在使用中。  消息列出所有正在运行的 .NET framework 4 应用程序并提供在安装之前关闭这些应用程序的选项。  如果用户进行确认，这些应用程序将通过安装程序关闭，并且避免了系统重新启动。  如果用户在一段时间内不响应该消息，则安装将继续而不关闭任何应用程序。  
  
 如果“重新启动管理器”检测到需要系统重新启动的情形，即使在正运行的应用程序已关闭的情况下，也不会显示消息。  
  
 ![“关闭应用程序”对话框](../../../docs/framework/deployment/media/closeapplicationdialog.png "CloseApplicationDialog")  
提示关闭正在使用的 .NET Framework 应用程序  
  
## 使用已链接的安装程序  
 如果要使用您的应用程序重新发布 .NET framework，但要使用您自己的安装程序和 UI，则您可以将（链接）.NET framework 安装进程包含到您的安装过程中。  有关链接安装的更多信息，请参见 [部署指南（针对开发人员）](../../../docs/framework/deployment/deployment-guide-for-developers.md)。  若要在已链接安装中减少系统重启，.NET Framework 安装程序将提供带要关闭的应用程序列表的安装程序。  您的安装程序必须通过消息框之类的用户界面向用户提供此信息、获取用户的响应，然后将响应传回 .NET Framework 安装程序。  对于链接的安装程序的示例，请参见文章 [如何：获取 .NET Framework 4.5 安装程序的进度](../../../docs/framework/deployment/how-to-get-progress-from-the-dotnet-installer.md)。  
  
 如果使用的是链接的安装程序，但是不想为关闭应用程序提供您自己的消息框，则在链接 .NET Framework 安装程序时可以使用命令行上的 `/showrmui` 和 `/passive` 选项。  在一起使用这些选项时，如果关闭应用程序以避免重启系统，则安装程序将显示用于关闭这些应用程序的消息框。  此消息框在被动模式作为完整的用户界面下有相同的行为。  有关 .NET Framework 可再发行组件的完整命令行选项集合，请参见 [部署指南（针对开发人员）](../../../docs/framework/deployment/deployment-guide-for-developers.md)。  
  
## 请参阅  
 [部署](../../../docs/framework/deployment/net-framework-and-applications.md)   
 [部署指南（针对开发人员）](../../../docs/framework/deployment/deployment-guide-for-developers.md)   
 [如何：获取 .NET Framework 4.5 安装程序的进度](../../../docs/framework/deployment/how-to-get-progress-from-the-dotnet-installer.md)