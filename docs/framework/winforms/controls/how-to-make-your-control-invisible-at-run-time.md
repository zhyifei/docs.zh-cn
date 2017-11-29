---
title: "如何：使控件在运行时不可见"
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
- controls [Windows Forms], making invisible at run time
- invisible controls
- user controls [Windows Forms], invisible
- custom controls [Windows Forms], invisible
- run time [Windows Forms], making controls invisible
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 310750df0786eb07158909eb5e322369d157d1cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a>如何：使控件在运行时不可见
有的时候你可能想要创建用户控件在运行时不可见。 例如，用作闹钟控件可能除响警报时不可见。 这很容易实现通过设置<xref:System.Windows.Forms.Control.Visible%2A>属性。 如果<xref:System.Windows.Forms.Control.Visible%2A>属性是`true`，控件将显示为正常。 如果`false`，控件将被隐藏。 尽管在控件中的代码可能继续运行时不可见的你将不能与通过用户界面控件进行交互。 如果你想要创建的不可见的控件，仍可响应用户输入 （例如，鼠标单击），则应创建一个透明的控件。 有关详细信息，请参阅[使控件拥有透明背景](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)。  
  
### <a name="to-make-your-control-invisible-at-run-time"></a>要使控件在运行时不可见  
  
1.  将 <xref:System.Windows.Forms.Control.Visible%2A> 属性设置为 `false`。  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
    ```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.Control.Visible%2A>  
 [使用 .NET Framework 开发自定义 Windows 窗体控件](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [如何：为控件设置透明背景](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)
