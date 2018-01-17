---
title: "属性更改事件"
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
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ad22d77043f00ab0caaa6d8b08b6b0a9eef1fed5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="property-changed-events"></a>属性更改事件
如果您希望控件名为的属性时发送通知*PropertyName*更改，定义一个名为*PropertyName* `Changed`和一个名为方法`On` *PropertyName* `Changed`引发事件。 Windows 窗体中的命名约定是追加单词*Changed*到属性的名称。 属性更改事件的关联的事件委托类型是<xref:System.EventHandler>，是事件数据类型<xref:System.EventArgs>。 基类<xref:System.Windows.Forms.Control>定义很多属性更改事件，如<xref:System.Windows.Forms.Control.BackColorChanged>， <xref:System.Windows.Forms.Control.BackgroundImageChanged>， <xref:System.Windows.Forms.Control.FontChanged>， <xref:System.Windows.Forms.Control.LocationChanged>，和其他人。 有关事件的背景信息，请参阅[事件](../../../../docs/standard/events/index.md)和[Windows 窗体控件中的事件](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)。  
  
 属性更改事件非常有用，因为它们允许使用者的控件附加对更改做出响应的事件处理程序。 如果你的控件需要响应它引发属性更改事件，重写相应`On` *PropertyName* `Changed`而不是将委托附加到事件的方法。 通过更新其他属性或重新绘制的部分或全部其绘图图面，控件通常响应属性更改事件。  
  
 下面的示例演示如何`FlashTrackBar`自定义控件的响应它继承自属性更改事件的某些<xref:System.Windows.Forms.Control>。 有关完整的示例，请参阅[如何： 创建 Windows 窗体控件，显示进度](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)。  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a>请参阅  
 [事件](../../../../docs/standard/events/index.md)  
 [Windows 窗体控件中的事件](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [Windows 窗体控件中的属性](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
