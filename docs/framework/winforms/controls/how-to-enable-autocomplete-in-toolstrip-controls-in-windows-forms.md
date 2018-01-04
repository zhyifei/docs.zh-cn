---
title: "如何：在 Windows 窗体的 ToolStrip 控件中启用自动完成"
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
- AutoComplete [Windows Forms], examples
- toolbars [Windows Forms], AutoComplete
- examples [Windows Forms], toolbars
- AutoComplete [Windows Forms], enabling in toolbars
- ToolStripComboBox class [Windows Forms], examples
- ToolStrip control [Windows Forms], AutoComplete
ms.assetid: fd66d085-1af1-45d4-930a-cde944da2e16
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7bbae29cea265fbc4cd92213066198b3f721c01d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a><span data-ttu-id="6f69a-102">如何：在 Windows 窗体的 ToolStrip 控件中启用自动完成</span><span class="sxs-lookup"><span data-stu-id="6f69a-102">How to: Enable AutoComplete in ToolStrip Controls in Windows Forms</span></span>
<span data-ttu-id="6f69a-103">以下过程将合并<xref:System.Windows.Forms.ToolStripLabel>与<xref:System.Windows.Forms.ToolStripComboBox>，拉方式显示如在最近的项，列表访问的网站。</span><span class="sxs-lookup"><span data-stu-id="6f69a-103">The following procedure combines a <xref:System.Windows.Forms.ToolStripLabel> with a <xref:System.Windows.Forms.ToolStripComboBox> that can be dropped down to show a list of items, such as recently visited Web sites.</span></span> <span data-ttu-id="6f69a-104">如果用户键入的字符相匹配的其中一个列表中项的第一个字符，将立即显示项。</span><span class="sxs-lookup"><span data-stu-id="6f69a-104">If the user types a character that matches the first character of one of the items in the list, the item is immediately displayed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f69a-105">自动完成配合`ToolStrip`中相同的方式，它如可与传统控件的控件<xref:System.Windows.Forms.ComboBox>和<xref:System.Windows.Forms.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="6f69a-105">Automatic completion works with `ToolStrip` controls in the same way that it works with traditional controls such as <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.TextBox>.</span></span>  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a><span data-ttu-id="6f69a-106">若要启用自动完成在 ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="6f69a-106">To enable AutoComplete in a ToolStrip control</span></span>  
  
1.  <span data-ttu-id="6f69a-107">创建<xref:System.Windows.Forms.ToolStrip>控制并向其添加项。</span><span class="sxs-lookup"><span data-stu-id="6f69a-107">Create a <xref:System.Windows.Forms.ToolStrip> control and add items to it.</span></span>  
  
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
  
2.  <span data-ttu-id="6f69a-108">设置<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>属性标签和组合框<xref:System.Windows.Forms.ToolStripItemOverflow.Never>以便列表始终可用而不考虑窗体的大小。</span><span class="sxs-lookup"><span data-stu-id="6f69a-108">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the label and the combo box to <xref:System.Windows.Forms.ToolStripItemOverflow.Never> so that the list is always available regardless of the form's size.</span></span>  
  
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
  
3.  <span data-ttu-id="6f69a-109">将字添加到项集合的<xref:System.Windows.Forms.ToolStripComboBox>控件。</span><span class="sxs-lookup"><span data-stu-id="6f69a-109">Add words to the Items collection of the <xref:System.Windows.Forms.ToolStripComboBox> control.</span></span>  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4.  <span data-ttu-id="6f69a-110">设置<xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A>属性的组合框<xref:System.Windows.Forms.AutoCompleteMode.Append>。</span><span class="sxs-lookup"><span data-stu-id="6f69a-110">Set the <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> property of the combo box to <xref:System.Windows.Forms.AutoCompleteMode.Append>.</span></span>  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5.  <span data-ttu-id="6f69a-111">设置<xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A>属性的组合框<xref:System.Windows.Forms.AutoCompleteSource.ListItems>。</span><span class="sxs-lookup"><span data-stu-id="6f69a-111">Set the <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> property of the combo box to <xref:System.Windows.Forms.AutoCompleteSource.ListItems>.</span></span>  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6f69a-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f69a-112">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripLabel>  
 <xref:System.Windows.Forms.ToolStripComboBox>  
 <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>  
 <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>  
 [<span data-ttu-id="6f69a-113">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="6f69a-113">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="6f69a-114">ToolStrip 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="6f69a-114">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="6f69a-115">ToolStrip 技术摘要</span><span class="sxs-lookup"><span data-stu-id="6f69a-115">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
