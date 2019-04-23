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
ms.openlocfilehash: e688e9a220e6c82caa2d107589b5ca9a1e59e72b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091247"
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a><span data-ttu-id="27a24-102">如何：在 ToolStrip 控件中创建切换按钮</span><span class="sxs-lookup"><span data-stu-id="27a24-102">How to: Create Toggle Buttons in ToolStrip Controls</span></span>
<span data-ttu-id="27a24-103">当用户单击切换按钮时，它显示凹下外观，并将保留凹下外观，直到用户单击按钮再次。</span><span class="sxs-lookup"><span data-stu-id="27a24-103">When a user clicks a toggle button, it appears sunken and retains the sunken appearance until the user clicks the button again.</span></span>  
  
### <a name="to-create-a-toggling-toolstripbutton"></a><span data-ttu-id="27a24-104">若要创建切换 ToolStripButton</span><span class="sxs-lookup"><span data-stu-id="27a24-104">To create a toggling ToolStripButton</span></span>  
  
-   <span data-ttu-id="27a24-105">使用如下面的代码示例的代码。</span><span class="sxs-lookup"><span data-stu-id="27a24-105">Use code such as the following code example.</span></span> <span data-ttu-id="27a24-106">此代码假定你的窗体包含<xref:System.Windows.Forms.ToolStrip>控件，并且其<xref:System.Windows.Forms.ToolStrip.Items%2A>集合包含<xref:System.Windows.Forms.ToolStripButton>调用`toolStripButton1`。</span><span class="sxs-lookup"><span data-stu-id="27a24-106">This code assumes that your form contains a <xref:System.Windows.Forms.ToolStrip> control, and that its <xref:System.Windows.Forms.ToolStrip.Items%2A> collection contains a <xref:System.Windows.Forms.ToolStripButton> called `toolStripButton1`.</span></span> <span data-ttu-id="27a24-107">它还假定您有事件处理程序调用`toolStripButton1_CheckedChanged`。</span><span class="sxs-lookup"><span data-stu-id="27a24-107">It also assumes that you have an event handler called `toolStripButton1_CheckedChanged`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="27a24-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="27a24-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStripButton>
- [<span data-ttu-id="27a24-109">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="27a24-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
