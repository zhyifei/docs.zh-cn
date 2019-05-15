---
title: 如何：在 Windows 窗体 ListView 控件中启用平铺视图
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tile view feature
- tiling
- Windows Forms, controls
- ListView control [Windows Forms], tile view
ms.assetid: c20e67a3-2d94-413d-9fcf-ecbd0fe251da
ms.openlocfilehash: bd152d19567806cf1cc7b1b38d9a3c0e47d2a960
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591682"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control"></a><span data-ttu-id="c5d32-102">如何：在 Windows 窗体 ListView 控件中启用平铺视图</span><span class="sxs-lookup"><span data-stu-id="c5d32-102">How to: Enable Tile View in a Windows Forms ListView Control</span></span>
<span data-ttu-id="c5d32-103">使用 <xref:System.Windows.Forms.ListView> 控件的磁贴视图功能，可以在图形和文本信息之间提供一种视觉平衡。</span><span class="sxs-lookup"><span data-stu-id="c5d32-103">With the tile view feature of the <xref:System.Windows.Forms.ListView> control, you can provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="c5d32-104">磁贴视图中，为项目显示的文本信息与为详细信息视图定义的列信息相同。</span><span class="sxs-lookup"><span data-stu-id="c5d32-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="c5d32-105">磁贴视图与 <xref:System.Windows.Forms.ListView> 控件中的分组或插入标记功能配合使用。</span><span class="sxs-lookup"><span data-stu-id="c5d32-105">Tile view works in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 <span data-ttu-id="c5d32-106">磁贴视图使用 32 x 32 像素的图标和若干行文本，如以下图像中所示。</span><span class="sxs-lookup"><span data-stu-id="c5d32-106">The tile view uses a 32 x 32 pixel icon and several lines of text, as shown in the following images.</span></span>  
  
 <span data-ttu-id="c5d32-107">![使用平铺视图的 ListView 控件中](./media/how-to-enable-tile-view-in-a-windows-forms-listview-control/tile-view-in-listview-control.gif "磁贴视图图标和文本")</span><span class="sxs-lookup"><span data-stu-id="c5d32-107">![Tile View in a ListView Control](./media/how-to-enable-tile-view-in-a-windows-forms-listview-control/tile-view-in-listview-control.gif "Tile view icons and text")</span></span>  
 
 <span data-ttu-id="c5d32-108">若要启用磁贴视图，请将 <xref:System.Windows.Forms.ListView.View%2A> 属性设置为 <xref:System.Windows.Forms.View.Tile>。</span><span class="sxs-lookup"><span data-stu-id="c5d32-108">To enable tile view, set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Tile>.</span></span> <span data-ttu-id="c5d32-109">可以通过设置 <xref:System.Windows.Forms.ListView.TileSize%2A> 属性来调整平铺大小，并通过调整 <xref:System.Windows.Forms.ListView.Columns%2A> 集合，来调整磁贴中显示的文本行数。</span><span class="sxs-lookup"><span data-stu-id="c5d32-109">You can adjust the size of the tiles by setting the <xref:System.Windows.Forms.ListView.TileSize%2A> property, and the number of text lines displayed in the tile by adjusting the <xref:System.Windows.Forms.ListView.Columns%2A> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5d32-110">当应用程序调用 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 方法时，磁贴视图仅适用于 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c5d32-110">The tile view is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c5d32-111">在早期的操作系统上，任何与磁贴视图相关的代码都不起作用，且 <xref:System.Windows.Forms.ListView> 控件将显示在大图标视图中。</span><span class="sxs-lookup"><span data-stu-id="c5d32-111">On earlier operating systems, any code related to the tile view has no effect, and the <xref:System.Windows.Forms.ListView> control displays in the large icon view.</span></span> <span data-ttu-id="c5d32-112">有关详细信息，请参阅 <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="c5d32-112">For more information, see <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-set-tile-view-programmatically"></a><span data-ttu-id="c5d32-113">若要以编程方式设置磁贴视图</span><span class="sxs-lookup"><span data-stu-id="c5d32-113">To set tile view programmatically</span></span>  
  
1. <span data-ttu-id="c5d32-114">使用 <xref:System.Windows.Forms.ListView> 控件的 <xref:System.Windows.Forms.View> 枚举。</span><span class="sxs-lookup"><span data-stu-id="c5d32-114">Use the <xref:System.Windows.Forms.View> enumeration of the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
    ```vb  
    ListView1.View = View.Tile  
    ```  
  
    ```csharp  
    listView1.View = View.Tile;  
    ```  
  
## <a name="example"></a><span data-ttu-id="c5d32-115">示例</span><span class="sxs-lookup"><span data-stu-id="c5d32-115">Example</span></span>  
 <span data-ttu-id="c5d32-116">以下完整的代码示例演示了修改磁贴以显示三行文本的磁贴视图。</span><span class="sxs-lookup"><span data-stu-id="c5d32-116">The following complete code example demonstrates Tile view with tiles modified to show three lines of text.</span></span> <span data-ttu-id="c5d32-117">已经调整了磁贴大小，以防止自动换行。</span><span class="sxs-lookup"><span data-stu-id="c5d32-117">The tile size has been adjusted to prevent line-wrapping.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CPP/listviewtilingexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CS/listviewtilingexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/VB/listviewtilingexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c5d32-118">编译代码</span><span class="sxs-lookup"><span data-stu-id="c5d32-118">Compiling the Code</span></span>  
 <span data-ttu-id="c5d32-119">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="c5d32-119">This example requires:</span></span>  
  
- <span data-ttu-id="c5d32-120">对 System 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="c5d32-120">References to the System and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="c5d32-121">在执行文件相同的目录中的一个名为 book.ico 的图标文件。</span><span class="sxs-lookup"><span data-stu-id="c5d32-121">An icon file named book.ico in the same directory as the executable file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5d32-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5d32-122">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [<span data-ttu-id="c5d32-123">ListView 控件</span><span class="sxs-lookup"><span data-stu-id="c5d32-123">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="c5d32-124">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="c5d32-124">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
