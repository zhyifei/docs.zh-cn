---
title: 如何：使控件在运行时不可见
ms.date: 03/30/2017
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
ms.openlocfilehash: 06283a93c3b88d2febc1d64797139eee62661b42
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201645"
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a>如何：使控件在运行时不可见
有些的时候您可能想要创建在运行时是不可见的用户控件。 例如，警报时钟控件可能不可见警报已响起时除外。 这很容易实现： 设置<xref:System.Windows.Forms.Control.Visible%2A>属性。 如果<xref:System.Windows.Forms.Control.Visible%2A>属性是`true`，控件将显示正常。 如果`false`，将隐藏控件。 尽管可能仍会在控件中的代码运行时不可见，则将不能与通过用户界面控件进行交互。 如果你想要创建的不可见控件，仍会响应用户输入 （例如鼠标单击），则应创建透明控件。 有关详细信息，请参阅[使控件拥有透明背景](how-to-give-your-control-a-transparent-background.md)。  
  
### <a name="to-make-your-control-invisible-at-run-time"></a>若要使控件在运行时不可见  
  
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
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Control.Visible%2A>
- [使用 .NET Framework 开发自定义 Windows 窗体控件](developing-custom-windows-forms-controls.md)
- [如何：使控件拥有透明背景](how-to-give-your-control-a-transparent-background.md)
