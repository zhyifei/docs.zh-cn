---
title: "Windows 窗体控件中的事件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e568dd7fadea8af399a63aa95347f368b4e13a54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="events-in-windows-forms-controls"></a>Windows 窗体控件中的事件
Windows 窗体控件继承来自多个六十事件<xref:System.Windows.Forms.Control?displayProperty=nameWithType>。 其中包括<xref:System.Windows.Forms.Control.Paint>事件，这会导致要绘制的控件，如显示一个窗口，与相关的事件<xref:System.Windows.Forms.Control.Resize>和<xref:System.Windows.Forms.Control.Layout>事件和低级别的鼠标和键盘事件。 某些低级别事件合成通过<xref:System.Windows.Forms.Control>到语义事件<xref:System.Windows.Forms.Control.Click>和<xref:System.Windows.Forms.Control.DoubleClick>。 有关继承的事件的详细信息，请参阅<xref:System.Windows.Forms.Control>。  
  
 如果自定义控件需要重写继承事件功能，请重写继承的 `On`*EventName* 方法，而不附加委托。 如果不熟悉 .NET Framework 中的事件模型，请参阅[从组件引发事件](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0)。  
  
## <a name="see-also"></a>另请参阅  
 [重写 OnPaint 方法](../../../../docs/framework/winforms/controls/overriding-the-onpaint-method.md)  
 [处理用户输入](../../../../docs/framework/winforms/controls/handling-user-input.md)  
 [定义事件](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [事件](../../../../docs/standard/events/index.md)
