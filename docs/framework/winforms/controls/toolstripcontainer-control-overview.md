---
title: ToolStripContainer 控件概述
ms.date: 03/30/2017
f1_keywords:
- ToolStripContainer
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], about ToolStripContainer control
ms.assetid: c7d63bff-64e2-4a63-bd89-d31bc96dacb8
ms.openlocfilehash: c279316c2a372a1498707b27ec8658813306304b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768327"
---
# <a name="toolstripcontainer-control-overview"></a><span data-ttu-id="e6c10-102">ToolStripContainer 控件概述</span><span class="sxs-lookup"><span data-stu-id="e6c10-102">ToolStripContainer Control Overview</span></span>
<span data-ttu-id="e6c10-103">一个<xref:System.Windows.Forms.ToolStripContainer>面板上其左侧、 右侧、 顶部和底部均带有用于定位和漂浮<xref:System.Windows.Forms.ToolStrip>， <xref:System.Windows.Forms.MenuStrip>，和<xref:System.Windows.Forms.StatusStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="e6c10-103">A <xref:System.Windows.Forms.ToolStripContainer> has panels on its left, right, top, and bottom sides for positioning and rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="e6c10-104">如果将多个 <xref:System.Windows.Forms.ToolStrip> 控件放置在 <xref:System.Windows.Forms.ToolStripContainer> 左侧或右侧，它们会垂直堆叠。</span><span class="sxs-lookup"><span data-stu-id="e6c10-104">Multiple <xref:System.Windows.Forms.ToolStrip> controls stack vertically if you put them in the left or right <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="e6c10-105">如果将其放置在 <xref:System.Windows.Forms.ToolStripContainer> 顶部或底部，则水平堆叠。</span><span class="sxs-lookup"><span data-stu-id="e6c10-105">They stack horizontally if you put them in the top or bottom <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="e6c10-106">可使用 <xref:System.Windows.Forms.ToolStripContainer> 的中央 <xref:System.Windows.Forms.ToolStripContentPanel> 将传统控件放置在窗体上。</span><span class="sxs-lookup"><span data-stu-id="e6c10-106">You can use the central <xref:System.Windows.Forms.ToolStripContentPanel> of the <xref:System.Windows.Forms.ToolStripContainer> to position traditional controls on the form.</span></span>  
  
 <span data-ttu-id="e6c10-107">任何或所有 <xref:System.Windows.Forms.ToolStripContainer> 控件都可在设计时选择且可删除。</span><span class="sxs-lookup"><span data-stu-id="e6c10-107">Any or all <xref:System.Windows.Forms.ToolStripContainer> controls are directly selectable at design time and can be deleted.</span></span> <span data-ttu-id="e6c10-108">每个面板<xref:System.Windows.Forms.ToolStripContainer>是可展开和折叠，并调整其大小与它所包含的控件。</span><span class="sxs-lookup"><span data-stu-id="e6c10-108">Each panel of a <xref:System.Windows.Forms.ToolStripContainer> is expandable and collapsible, and resizes with the controls that it contains.</span></span>  
  
### <a name="important-toolstripcontainer-members"></a><span data-ttu-id="e6c10-109">重要 ToolStripContainer 成员</span><span class="sxs-lookup"><span data-stu-id="e6c10-109">Important ToolStripContainer Members</span></span>  
  
|<span data-ttu-id="e6c10-110">名称</span><span class="sxs-lookup"><span data-stu-id="e6c10-110">Name</span></span>|<span data-ttu-id="e6c10-111">描述</span><span class="sxs-lookup"><span data-stu-id="e6c10-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|<span data-ttu-id="e6c10-112">获取的底部面板<xref:System.Windows.Forms.ToolStripContainer>。</span><span class="sxs-lookup"><span data-stu-id="e6c10-112">Gets the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|<span data-ttu-id="e6c10-113">获取或设置一个值，该值指示是否的底部面板<xref:System.Windows.Forms.ToolStripContainer>可见。</span><span class="sxs-lookup"><span data-stu-id="e6c10-113">Gets or sets a value indicating whether the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|<span data-ttu-id="e6c10-114">获取左的面板中的<xref:System.Windows.Forms.ToolStripContainer>。</span><span class="sxs-lookup"><span data-stu-id="e6c10-114">Gets the left panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|<span data-ttu-id="e6c10-115">获取或设置一个值，该值指示是否的左侧的面板<xref:System.Windows.Forms.ToolStripContainer>可见。</span><span class="sxs-lookup"><span data-stu-id="e6c10-115">Gets or sets a value indicating whether the left panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|<span data-ttu-id="e6c10-116">获取的右侧面板<xref:System.Windows.Forms.ToolStripContainer>。</span><span class="sxs-lookup"><span data-stu-id="e6c10-116">Gets the right panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|<span data-ttu-id="e6c10-117">获取或设置一个值，该值指示是否的右侧面板<xref:System.Windows.Forms.ToolStripContainer>可见。</span><span class="sxs-lookup"><span data-stu-id="e6c10-117">Gets or sets a value indicating whether the right panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|<span data-ttu-id="e6c10-118">获取的顶部面板<xref:System.Windows.Forms.ToolStripContainer>。</span><span class="sxs-lookup"><span data-stu-id="e6c10-118">Gets the top panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|<span data-ttu-id="e6c10-119">获取或设置一个值，该值指示是否的顶部面板<xref:System.Windows.Forms.ToolStripContainer>可见。</span><span class="sxs-lookup"><span data-stu-id="e6c10-119">Gets or sets a value indicating whether the top panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e6c10-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6c10-120">See also</span></span>

- <xref:System.Windows.Forms.ToolStripContainer>
- <xref:System.Windows.Forms.ToolStripContentPanel>
