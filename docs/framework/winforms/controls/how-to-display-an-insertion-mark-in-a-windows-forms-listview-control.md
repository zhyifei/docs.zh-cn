---
title: 如何：在 Windows 窗体 ListView 控件中显示插入标记
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ListView control [Windows Forms], drag operations
- graphics [Windows Forms], insertion marks
- drop and drag [Windows Forms], insertion marks
- insertion marks
ms.assetid: 88d0a15b-25fd-4dc3-a685-297351311940
ms.openlocfilehash: f3dff351052eaaf70737c6410c1367ab568f6fd0
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586519"
---
# <a name="how-to-display-an-insertion-mark-in-a-windows-forms-listview-control"></a><span data-ttu-id="d7061-102">如何：在 Windows 窗体 ListView 控件中显示插入标记</span><span class="sxs-lookup"><span data-stu-id="d7061-102">How to: Display an Insertion Mark in a Windows Forms ListView Control</span></span>
<span data-ttu-id="d7061-103"><xref:System.Windows.Forms.ListView> 控件的插入标记向用户显示拖动项将插入的位置。</span><span class="sxs-lookup"><span data-stu-id="d7061-103">The insertion mark in the <xref:System.Windows.Forms.ListView> control shows users the point where dragged items will be inserted.</span></span> <span data-ttu-id="d7061-104">当用户将某项拖至两个其他项之间的位置时，插入标记会显示该项的预计新位置。</span><span class="sxs-lookup"><span data-stu-id="d7061-104">When a user drags an item to a point between two other items, the insertion mark shows the item's expected new location.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7061-105">当应用程序调用 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 方法时，插入标记功能则仅在 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] 中可用。</span><span class="sxs-lookup"><span data-stu-id="d7061-105">The insertion mark feature is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d7061-106">在早期的操作系统中，与插入标记相关的任何代码都不会有影响，并且插入标记也不会出现。</span><span class="sxs-lookup"><span data-stu-id="d7061-106">On earlier operating systems, any code relating to the insertion mark has no effect and the insertion mark will not appear.</span></span> <span data-ttu-id="d7061-107">有关详细信息，请参阅 <xref:System.Windows.Forms.ListViewInsertionMark>。</span><span class="sxs-lookup"><span data-stu-id="d7061-107">For more information, see <xref:System.Windows.Forms.ListViewInsertionMark>.</span></span>  
  
 <span data-ttu-id="d7061-108">下图显示一个插入标记：</span><span class="sxs-lookup"><span data-stu-id="d7061-108">The following image shows an insertion mark:</span></span>  
  
 <span data-ttu-id="d7061-109">![显示 ListView 插入标记的屏幕截图。](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "ListViewInsertion")</span><span class="sxs-lookup"><span data-stu-id="d7061-109">![Screenshot that shows a ListView insertion mark.](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "ListViewInsertion")</span></span>  
  
 <span data-ttu-id="d7061-110">下面的代码示例显示如何使用此功能。</span><span class="sxs-lookup"><span data-stu-id="d7061-110">The following code example demonstrates how to use this feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7061-111">示例</span><span class="sxs-lookup"><span data-stu-id="d7061-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d7061-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="d7061-112">Compiling the Code</span></span>  
 <span data-ttu-id="d7061-113">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="d7061-113">This example requires:</span></span>  
  
- <span data-ttu-id="d7061-114">对 System 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="d7061-114">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7061-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7061-115">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewInsertionMark>
- [<span data-ttu-id="d7061-116">ListView 控件</span><span class="sxs-lookup"><span data-stu-id="d7061-116">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="d7061-117">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="d7061-117">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="d7061-118">演练：在 Windows 窗体中执行拖放操作</span><span class="sxs-lookup"><span data-stu-id="d7061-118">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](../advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)
