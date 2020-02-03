---
title: 使用设计器在 ListView 控件中启用磁贴视图
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: a0429efaab14995ab1e3f3b0dfd91db61de72fbf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745800"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="4b397-102">如何：使用设计器在 Windows 窗体 ListView 控件中启用平铺视图</span><span class="sxs-lookup"><span data-stu-id="4b397-102">How to: Enable Tile View in a Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="4b397-103">利用 <xref:System.Windows.Forms.ListView> 控件的磁贴视图功能，可以在图形和文本信息之间提供视觉平衡。</span><span class="sxs-lookup"><span data-stu-id="4b397-103">The tile view feature of the <xref:System.Windows.Forms.ListView> control enables you to provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="4b397-104">磁贴视图中，为项目显示的文本信息与为详细信息视图定义的列信息相同。</span><span class="sxs-lookup"><span data-stu-id="4b397-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="4b397-105">平铺视图函数与 <xref:System.Windows.Forms.ListView> 控件中的分组或插入标记功能结合在一起。</span><span class="sxs-lookup"><span data-stu-id="4b397-105">Tile view functions in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>

 <span data-ttu-id="4b397-106">磁贴视图使用 32 x 32 图标和几行文本，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="4b397-106">The tile view uses a 32 x 32 icon and several lines of text, as shown in the following image.</span></span>

 <span data-ttu-id="4b397-107">![ListView 控件中的平铺视图](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "磁贴视图图标和文本")</span><span class="sxs-lookup"><span data-stu-id="4b397-107">![Tile View in a ListView Control](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Tile view icons and text")</span></span>

 <span data-ttu-id="4b397-108">利用磁贴视图属性和方法，您可以指定要为每个项显示的列字段，以及共同控制平铺视图窗口中所有项的大小和外观。</span><span class="sxs-lookup"><span data-stu-id="4b397-108">Tile view properties and methods enable you to specify which column fields to display for each item, and to collectively control the size and appearance of all items within a tile view window.</span></span> <span data-ttu-id="4b397-109">为清楚起见，磁贴中的第一行文本始终是项的名称;不能更改它。</span><span class="sxs-lookup"><span data-stu-id="4b397-109">For clarity, the first line of text in a tile is always the item's name; it cannot be changed.</span></span>

 <span data-ttu-id="4b397-110">下面的过程需要一个**Windows 应用程序**项目，其中包含一个包含 <xref:System.Windows.Forms.ListView> 控件的窗体。</span><span class="sxs-lookup"><span data-stu-id="4b397-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="4b397-111">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="4b397-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-set-tile-view-in-the-designer"></a><span data-ttu-id="4b397-112">在设计器中设置磁贴视图</span><span class="sxs-lookup"><span data-stu-id="4b397-112">To set tile view in the designer</span></span>

1. <span data-ttu-id="4b397-113">在 Visual Studio 中，选择窗体上的 "<xref:System.Windows.Forms.ListView>" 控件。</span><span class="sxs-lookup"><span data-stu-id="4b397-113">In Visual Studio, select the <xref:System.Windows.Forms.ListView> control on your form.</span></span>

2. <span data-ttu-id="4b397-114">在 "**属性**" 窗口中，选择 "<xref:System.Windows.Forms.ListView.View%2A>" 属性，然后选择 "**磁贴**"。</span><span class="sxs-lookup"><span data-stu-id="4b397-114">In the **Properties** window, select the <xref:System.Windows.Forms.ListView.View%2A> property and choose **Tile**.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b397-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b397-115">See also</span></span>

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [<span data-ttu-id="4b397-116">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="4b397-116">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
