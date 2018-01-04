---
title: "如何：将控件添加到选项卡页"
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
- cpp
helpviewer_keywords:
- TabPage control
- tab controls [Windows Forms], tab order
- tab pages [Windows Forms], adding controls
ms.assetid: b092532e-7346-469f-b9a1-897f9bea4fb7
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e37a336ece07ae51d45446d5754a52eac113505d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-control-to-a-tab-page"></a><span data-ttu-id="6c571-102">如何：将控件添加到选项卡页</span><span class="sxs-lookup"><span data-stu-id="6c571-102">How to: Add a Control to a Tab Page</span></span>
<span data-ttu-id="6c571-103">你可以使用 Windows 窗体<xref:System.Windows.Forms.TabControl>若要在以组织方式中显示其他控件。</span><span class="sxs-lookup"><span data-stu-id="6c571-103">You can use the Windows Forms <xref:System.Windows.Forms.TabControl> to display other controls in an organized fashion.</span></span> <span data-ttu-id="6c571-104">以下过程说明如何将按钮添加到第一个选项卡。有关将图标添加到选项卡页的标签部分的信息，请参阅[如何： 更改 Windows 窗体 TabControl 的外观](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)。</span><span class="sxs-lookup"><span data-stu-id="6c571-104">The following procedure shows how to add a button to the first tab. For information about adding an icon to the label part of a tab page, see [How to: Change the Appearance of the Windows Forms TabControl](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span></span>  
  
### <a name="to-add-a-control-programmatically"></a><span data-ttu-id="6c571-105">以编程方式添加控件</span><span class="sxs-lookup"><span data-stu-id="6c571-105">To add a control programmatically</span></span>  
  
1.  <span data-ttu-id="6c571-106">使用<xref:System.Windows.Forms.Control.ControlCollection.Add%2A>方法返回的集合<xref:System.Windows.Forms.Control.Controls%2A>属性<xref:System.Windows.Forms.TabPage>:</span><span class="sxs-lookup"><span data-stu-id="6c571-106">Use the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.Control.Controls%2A> property of <xref:System.Windows.Forms.TabPage>:</span></span>  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6c571-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c571-107">See Also</span></span>  
 [<span data-ttu-id="6c571-108">TabControl 控件</span><span class="sxs-lookup"><span data-stu-id="6c571-108">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="6c571-109">TabControl 控件概述</span><span class="sxs-lookup"><span data-stu-id="6c571-109">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="6c571-110">如何：更改 Windows 窗体 TabControl 控件的外观</span><span class="sxs-lookup"><span data-stu-id="6c571-110">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)  
 [<span data-ttu-id="6c571-111">如何：禁用选项卡页</span><span class="sxs-lookup"><span data-stu-id="6c571-111">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="6c571-112">如何：使用 Windows 窗体 TabControl 控件添加和删除选项卡</span><span class="sxs-lookup"><span data-stu-id="6c571-112">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
