---
title: "如何： 返回对话框结果"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5f8133ffa7be9cb4e0600fc2681402d5e0f7471c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-return-a-dialog-box-result"></a>如何： 返回对话框结果
此示例演示如何检索一个窗口，通过调用打开的对话框结果<xref:System.Windows.Window.ShowDialog%2A>。  
  
## <a name="example"></a>示例  
 在对话框关闭之前，其<xref:System.Windows.Window.DialogResult%2A>属性应设置与<xref:System.Nullable%601> <xref:System.Boolean> ，该值指示用户如何关闭对话框。 此值由返回<xref:System.Windows.Window.ShowDialog%2A>以允许客户端代码，以确定如何关闭对话框中，因此，如何处理的结果。  
  
> [!NOTE]
>  <xref:System.Windows.Window.DialogResult%2A>当通过调用来打开窗口时才可以设置<xref:System.Windows.Window.ShowDialog%2A>。  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 调用<xref:System.Windows.Window.ShowDialog%2A>需要有权使用所有窗口和不受限制的用户输入的事件。
