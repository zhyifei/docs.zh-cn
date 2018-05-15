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
ms.openlocfilehash: a04d531433273328c2d8eb0c5ef614f08c33952a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a><span data-ttu-id="a29b3-102">如何：在 ToolStrip 控件中创建切换按钮</span><span class="sxs-lookup"><span data-stu-id="a29b3-102">How to: Create Toggle Buttons in ToolStrip Controls</span></span>
<span data-ttu-id="a29b3-103">当用户单击切换按钮时，它显示为凹陷并保留凹陷外观，直到用户单击按钮再次。</span><span class="sxs-lookup"><span data-stu-id="a29b3-103">When a user clicks a toggle button, it appears sunken and retains the sunken appearance until the user clicks the button again.</span></span>  
  
### <a name="to-create-a-toggling-toolstripbutton"></a><span data-ttu-id="a29b3-104">若要创建切换 ToolStripButton</span><span class="sxs-lookup"><span data-stu-id="a29b3-104">To create a toggling ToolStripButton</span></span>  
  
-   <span data-ttu-id="a29b3-105">使用如下面的代码示例的代码。</span><span class="sxs-lookup"><span data-stu-id="a29b3-105">Use code such as the following code example.</span></span> <span data-ttu-id="a29b3-106">此代码假定你的窗体包含<xref:System.Windows.Forms.ToolStrip>控件，并且其<xref:System.Windows.Forms.ToolStrip.Items%2A>集合包含<xref:System.Windows.Forms.ToolStripButton>调用`toolStripButton1`。</span><span class="sxs-lookup"><span data-stu-id="a29b3-106">This code assumes that your form contains a <xref:System.Windows.Forms.ToolStrip> control, and that its <xref:System.Windows.Forms.ToolStrip.Items%2A> collection contains a <xref:System.Windows.Forms.ToolStripButton> called `toolStripButton1`.</span></span> <span data-ttu-id="a29b3-107">它还假定你具有事件处理程序调用`toolStripButton1_CheckedChanged`。</span><span class="sxs-lookup"><span data-stu-id="a29b3-107">It also assumes that you have an event handler called `toolStripButton1_CheckedChanged`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a29b3-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="a29b3-108">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripButton>  
 [<span data-ttu-id="a29b3-109">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="a29b3-109">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
