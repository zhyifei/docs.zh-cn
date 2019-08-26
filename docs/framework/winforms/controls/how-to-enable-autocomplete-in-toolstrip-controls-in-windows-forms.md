---
title: 如何：在 Windows 窗体中的 ToolStrip 控件中启用自动完成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoComplete [Windows Forms], examples
- toolbars [Windows Forms], AutoComplete
- examples [Windows Forms], toolbars
- AutoComplete [Windows Forms], enabling in toolbars
- ToolStripComboBox class [Windows Forms], examples
- ToolStrip control [Windows Forms], AutoComplete
ms.assetid: fd66d085-1af1-45d4-930a-cde944da2e16
ms.openlocfilehash: 301f1b156bbaee5c5f7be95e972ee1ebaa83777f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963616"
---
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a>如何：在 Windows 窗体中的 ToolStrip 控件中启用自动完成
以下过程将<xref:System.Windows.Forms.ToolStripLabel> <xref:System.Windows.Forms.ToolStripComboBox>和结合使用, 以便显示项目列表, 如最近访问的网站。 如果用户键入的字符与列表中某个项的第一个字符相匹配, 则会立即显示该项。  
  
> [!NOTE]
> 自动完成功能的`ToolStrip`工作方式与使用传统控件<xref:System.Windows.Forms.ComboBox> (如和<xref:System.Windows.Forms.TextBox>) 的方法相同。  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a>在 ToolStrip 控件中启用自动完成  
  
1. 创建一个<xref:System.Windows.Forms.ToolStrip>控件并向其中添加项。  
  
    ```vb  
    ToolStrip1 = New System.Windows.Forms.ToolStrip  
    ToolStrip1.Items.AddRange(New System.Windows.Forms.ToolStripItem()_  
        {ToolStripLabel1, ToolStripComboBox1})  
    ```  
  
    ```csharp  
    toolStrip1 = new System.Windows.Forms.ToolStrip();  
    toolStrip1.Items.AddRange(new System.Windows.Forms.ToolStripItem[]   
        {toolStripLabel1, toolStripComboBox1});  
    ```  
  
2. 将标签的<xref:System.Windows.Forms.ToolStripItemOverflow.Never> 属性和组合框设置为,以使列表始终可用,而不考虑窗<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>体的大小。  
  
    ```vb  
    ToolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ToolStripComboBox1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    toolStripComboBox1.Overflow = System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
3. 向<xref:System.Windows.Forms.ToolStripComboBox>控件的 Items 集合添加单词。  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4. 将组合框的<xref:System.Windows.Forms.AutoCompleteMode.Append>属性设置为。<xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A>  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5. 将组合框的<xref:System.Windows.Forms.AutoCompleteSource.ListItems>属性设置为。<xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A>  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
    ```  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripLabel>
- <xref:System.Windows.Forms.ToolStripComboBox>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>
- [ToolStrip 控件概述](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 控件体系结构](toolstrip-control-architecture.md)
- [ToolStrip 技术摘要](toolstrip-technology-summary.md)
