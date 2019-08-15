---
title: 如何：使用设计器在 Windows 窗体 ListView 控件中启用平铺视图
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: 8a45a8a484bd373f53585b1b113a51e59b30fca2
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040354"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="ceb96-102">如何：使用设计器在 Windows 窗体 ListView 控件中启用平铺视图</span><span class="sxs-lookup"><span data-stu-id="ceb96-102">How to: Enable Tile View in a Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="ceb96-103">使用<xref:System.Windows.Forms.ListView>控件的磁贴视图功能, 可以在图形和文本信息之间提供视觉平衡。</span><span class="sxs-lookup"><span data-stu-id="ceb96-103">The tile view feature of the <xref:System.Windows.Forms.ListView> control enables you to provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="ceb96-104">磁贴视图中，为项目显示的文本信息与为详细信息视图定义的列信息相同。</span><span class="sxs-lookup"><span data-stu-id="ceb96-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="ceb96-105">平铺视图函数与<xref:System.Windows.Forms.ListView>控件中的分组或插入标记功能结合在一起。</span><span class="sxs-lookup"><span data-stu-id="ceb96-105">Tile view functions in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>

 <span data-ttu-id="ceb96-106">磁贴视图使用 32 x 32 图标和几行文本, 如下图所示。</span><span class="sxs-lookup"><span data-stu-id="ceb96-106">The tile view uses a 32 x 32 icon and several lines of text, as shown in the following image.</span></span>

 <span data-ttu-id="ceb96-107">![ListView 控件中的平铺视图](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "磁贴视图图标和文本")</span><span class="sxs-lookup"><span data-stu-id="ceb96-107">![Tile View in a ListView Control](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Tile view icons and text")</span></span>

 <span data-ttu-id="ceb96-108">利用磁贴视图属性和方法, 您可以指定要为每个项显示的列字段, 以及共同控制平铺视图窗口中所有项的大小和外观。</span><span class="sxs-lookup"><span data-stu-id="ceb96-108">Tile view properties and methods enable you to specify which column fields to display for each item, and to collectively control the size and appearance of all items within a tile view window.</span></span> <span data-ttu-id="ceb96-109">为清楚起见, 磁贴中的第一行文本始终是项的名称;不能更改它。</span><span class="sxs-lookup"><span data-stu-id="ceb96-109">For clarity, the first line of text in a tile is always the item's name; it cannot be changed.</span></span>

 <span data-ttu-id="ceb96-110">下面的过程需要一个**Windows 应用程序**项目, 该项目具有<xref:System.Windows.Forms.ListView>包含控件的窗体。</span><span class="sxs-lookup"><span data-stu-id="ceb96-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="ceb96-111">有关设置此类项目的信息, 请参阅[如何:创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)以及[如何:将控件添加到](how-to-add-controls-to-windows-forms.md)Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="ceb96-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ceb96-112">当应用程序调用 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 方法时，磁贴视图仅适用于 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ceb96-112">The tile view is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ceb96-113">在早期的操作系统上，任何与磁贴视图相关的代码都不起作用，且 <xref:System.Windows.Forms.ListView> 控件将显示在大图标视图中。</span><span class="sxs-lookup"><span data-stu-id="ceb96-113">On earlier operating systems, any code related to the tile view has no effect, and the <xref:System.Windows.Forms.ListView> control displays in the large icon view.</span></span> <span data-ttu-id="ceb96-114">有关详细信息，请参阅 <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="ceb96-114">For more information, see <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span></span>

## <a name="to-set-tile-view-in-the-designer"></a><span data-ttu-id="ceb96-115">在设计器中设置磁贴视图</span><span class="sxs-lookup"><span data-stu-id="ceb96-115">To set tile view in the designer</span></span>

1. <span data-ttu-id="ceb96-116">在 Visual Studio 中, 选择<xref:System.Windows.Forms.ListView>窗体上的控件。</span><span class="sxs-lookup"><span data-stu-id="ceb96-116">In Visual Studio, select the <xref:System.Windows.Forms.ListView> control on your form.</span></span>

2. <span data-ttu-id="ceb96-117">在 "**属性**" 窗口中, <xref:System.Windows.Forms.ListView.View%2A>选择属性, 然后选择 "**磁贴**"。</span><span class="sxs-lookup"><span data-stu-id="ceb96-117">In the **Properties** window, select the <xref:System.Windows.Forms.ListView.View%2A> property and choose **Tile**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ceb96-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="ceb96-118">See also</span></span>

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [<span data-ttu-id="ceb96-119">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="ceb96-119">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
