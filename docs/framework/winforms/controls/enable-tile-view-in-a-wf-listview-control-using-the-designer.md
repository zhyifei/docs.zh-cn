---
title: "如何：使用设计器在 Windows 窗体 ListView 控件中启用平铺视图"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 36b20f4ee5bed6f81c42225f35083d51fb2a6308
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="3f0fd-102">如何：使用设计器在 Windows 窗体 ListView 控件中启用平铺视图</span><span class="sxs-lookup"><span data-stu-id="3f0fd-102">How to: Enable Tile View in a Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="3f0fd-103">磁贴视图功能<xref:System.Windows.Forms.ListView>控制，你可以提供一种视觉平衡图形和文本信息之间。</span><span class="sxs-lookup"><span data-stu-id="3f0fd-103">The tile view feature of the <xref:System.Windows.Forms.ListView> control enables you to provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="3f0fd-104">磁贴视图中，为项目显示的文本信息与为详细信息视图定义的列信息相同。</span><span class="sxs-lookup"><span data-stu-id="3f0fd-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="3f0fd-105">磁贴视图功能结合的分组或插入标记中的功能<xref:System.Windows.Forms.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="3f0fd-105">Tile view functions in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 <span data-ttu-id="3f0fd-106">磁贴视图使用 32 x 32 图标和若干行文本，如在下图中所示。</span><span class="sxs-lookup"><span data-stu-id="3f0fd-106">The tile view uses a 32 x 32 icon and several lines of text, as shown in the following image.</span></span>  
  
 <span data-ttu-id="3f0fd-107">![平铺 ListView 控件中的视图](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")</span><span class="sxs-lookup"><span data-stu-id="3f0fd-107">![Tile View in a ListView Control](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")</span></span>  
  
 <span data-ttu-id="3f0fd-108">平铺视图属性和方法，可以指定哪些列字段以显示每个项，以及共同控制的大小和磁贴视图窗口中的所有项的外观。</span><span class="sxs-lookup"><span data-stu-id="3f0fd-108">Tile view properties and methods enable you to specify which column fields to display for each item, and to collectively control the size and appearance of all items within a tile view window.</span></span> <span data-ttu-id="3f0fd-109">为清楚起见，将磁贴中的第一行始终是文本的项的名称;它不能更改。</span><span class="sxs-lookup"><span data-stu-id="3f0fd-109">For clarity, the first line of text in a tile is always the item's name; it cannot be changed.</span></span>  
  
 <span data-ttu-id="3f0fd-110">下面的过程需要**Windows 应用程序**具有一个窗体包含项目<xref:System.Windows.Forms.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="3f0fd-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="3f0fd-111">有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="3f0fd-111">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f0fd-112">当应用程序调用 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 方法时，磁贴视图仅适用于 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3f0fd-112">The tile view is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="3f0fd-113">在早期的操作系统上，任何与磁贴视图相关的代码都不起作用，且 <xref:System.Windows.Forms.ListView> 控件将显示在大图标视图中。</span><span class="sxs-lookup"><span data-stu-id="3f0fd-113">On earlier operating systems, any code related to the tile view has no effect, and the <xref:System.Windows.Forms.ListView> control displays in the large icon view.</span></span> <span data-ttu-id="3f0fd-114">有关详细信息，请参阅<xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="3f0fd-114">For more information, see <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span></span>  
>   
>  <span data-ttu-id="3f0fd-115">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="3f0fd-115">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3f0fd-116">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="3f0fd-116">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3f0fd-117">有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="3f0fd-117">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-set-tile-view-in-the-designer"></a><span data-ttu-id="3f0fd-118">若要设置设计器中的磁贴视图</span><span class="sxs-lookup"><span data-stu-id="3f0fd-118">To set tile view in the designer</span></span>  
  
1.  <span data-ttu-id="3f0fd-119">选择<xref:System.Windows.Forms.ListView>窗体上的控件。</span><span class="sxs-lookup"><span data-stu-id="3f0fd-119">Select the <xref:System.Windows.Forms.ListView> control on your form.</span></span>  
  
2.  <span data-ttu-id="3f0fd-120">在**属性**窗口中，选择<xref:System.Windows.Forms.ListView.View%2A>属性，然后选择**磁贴**。</span><span class="sxs-lookup"><span data-stu-id="3f0fd-120">In the **Properties** window, select the <xref:System.Windows.Forms.ListView.View%2A> property and choose **Tile**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f0fd-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f0fd-121">See Also</span></span>  
 <xref:System.Windows.Forms.ListView.TileSize%2A>  
 [<span data-ttu-id="3f0fd-122">Windows XP 功能和 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="3f0fd-122">Windows XP Features and Windows Forms Controls</span></span>](http://msdn.microsoft.com/en-us/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [<span data-ttu-id="3f0fd-123">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="3f0fd-123">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
