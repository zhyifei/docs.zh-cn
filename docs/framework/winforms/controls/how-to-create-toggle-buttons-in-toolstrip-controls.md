---
title: 如何：在 ToolStrip 控件中创建切换按钮
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
ms.openlocfilehash: 21da5564bfeec01d448c23d3e734bdd16fc1566b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64666435"
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a>如何：在 ToolStrip 控件中创建切换按钮
当用户单击切换按钮时，它显示凹下外观，并将保留凹下外观，直到用户单击按钮再次。  
  
### <a name="to-create-a-toggling-toolstripbutton"></a>若要创建切换 ToolStripButton  
  
- 使用如下面的代码示例的代码。 此代码假定你的窗体包含<xref:System.Windows.Forms.ToolStrip>控件，并且其<xref:System.Windows.Forms.ToolStrip.Items%2A>集合包含<xref:System.Windows.Forms.ToolStripButton>调用`toolStripButton1`。 它还假定您有事件处理程序调用`toolStripButton1_CheckedChanged`。  
  
    ```vb  
    toolStripButton1.CheckOnClick = True  
    toolStripButton1.CheckedChanged AddressOf _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
    ```csharp  
    toolStripButton1.CheckOnClick = true;  
    toolStripButton1.CheckedChanged += new _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.ToolStripButton>
- [ToolStrip 控件概述](toolstrip-control-overview-windows-forms.md)
