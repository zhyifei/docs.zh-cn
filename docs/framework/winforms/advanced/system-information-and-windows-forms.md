---
title: "系统信息和 Windows 窗体"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- domain names [Windows Forms], retrieving
- SystemInformation class [Windows Forms]
- user names [Windows Forms], retrieving
- system information [Windows Forms]
ms.assetid: 30cf43a3-8cb2-4ff3-862b-6c34576616a8
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6657556ffb49c19e6ffc3ef5462de341a93112b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="system-information-and-windows-forms"></a>系统信息和 Windows 窗体
有时很必要收集有关你的应用程序在运行以便在你的代码做出的决策的计算机的信息。 例如，你可能必须才适用时连接到特定网络域; 函数在这种情况下，你需要一种方法来确定的域和禁用该函数，如果域不存在。  
  
 Windows 窗体应用程序可以使用<xref:System.Windows.Forms.SystemInformation>类以在运行时确定大量有关计算机的操作。 下面的示例演示如何使用<xref:System.Windows.Forms.SystemInformation>类检索<xref:System.Windows.Forms.SystemInformation.UserName%2A>和<xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:  
  
```vb  
Dim User As String = Windows.Forms.SystemInformation.UserName  
Dim Domain As String = Windows.Forms.SystemInformation.UserDomainName  
  
MessageBox.Show("Good morning " & User & ". You are connected to " _  
& Domain)  
```  
  
```csharp  
string User = SystemInformation.UserName;  
string Domain = SystemInformation.UserDomainName;  
  
MessageBox.Show("Good morning " + User + ". You are connected to " _  
+ Domain)  
```  
  
 所有成员<xref:System.Windows.Forms.SystemInformation>类是只读的; 您无法修改用户的设置。 有 100 多个成员的类，从连接到计算机的监视器数目返回的所有内容的信息 (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) 到 Windows 资源管理器中的图标的间距 (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A>和<xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>)。  
  
 一些更有用的成员<xref:System.Windows.Forms.SystemInformation>类包括<xref:System.Windows.Forms.SystemInformation.ComputerName%2A>， <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>， <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>，和<xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.SystemInformation>  
 [Windows 窗体中的电源管理](../../../../docs/framework/winforms/advanced/power-management-in-windows-forms.md)
