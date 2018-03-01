---
title: "如何： 获取所有 Windows 应用程序中"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- window objects [WPF], getting
ms.assetid: f120f06e-993b-4a97-9657-af0d1986981f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fdb1baad8b779b6ef0443a05e5f6575b552b1c19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-all-windows-in-an-application"></a>如何： 获取所有 Windows 应用程序中
此示例演示如何获取所有<xref:System.Windows.Window>应用程序中的对象。  
  
## <a name="example"></a>示例  
 每个实例化<xref:System.Windows.Window>对象时，是否可见，会自动添加到由管理的窗口引用的集合<xref:System.Windows.Application>，和从公开<xref:System.Windows.Application.Windows%2A>。  
  
 你可以枚举<xref:System.Windows.Application.Windows%2A>获取使用下面的代码的所有实例化的 windows:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
