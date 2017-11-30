---
title: "Windows 窗体中的鼠标捕获"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8004b05ea25341a142bfcfd9ae812ee3bebd6d5b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="mouse-capture-in-windows-forms"></a>Windows 窗体中的鼠标捕获
*鼠标捕获*指控制所采用的所有鼠标输入的命令。 当控件已捕获鼠标时，它会接收鼠标输入，指示在其边框内为指针。  
  
## <a name="setting-mouse-capture"></a>设置鼠标捕获  
 Windows 窗体中捕获了鼠标是由该控件在用户按鼠标按钮控件，并当用户释放鼠标按钮时由该控件中释放鼠标时。  
  
 <xref:System.Windows.Forms.Control.Capture%2A>属性<xref:System.Windows.Forms.Control>类指定控件是否已捕获鼠标。 若要确定当控件失去鼠标捕获，处理<xref:System.Windows.Forms.Control.MouseCaptureChanged>事件。  
  
 只有前台窗口可以捕获鼠标。 当后台窗口尝试捕获鼠标时，窗口只接收的消息时发生鼠标指针位于窗口的可见部分的鼠标事件。 此外，即使前景窗口已捕获鼠标，用户仍可以单击另一个窗口，使其变为前台。 当将鼠标捕获时，键盘快捷方式执行操作无法工作。  
  
## <a name="see-also"></a>另请参阅  
 [Windows 窗体应用程序中的鼠标输入](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
