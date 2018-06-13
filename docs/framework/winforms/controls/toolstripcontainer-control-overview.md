---
title: ToolStripContainer 控件概述
ms.date: 03/30/2017
f1_keywords:
- ToolStripContainer
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], about ToolStripContainer control
ms.assetid: c7d63bff-64e2-4a63-bd89-d31bc96dacb8
ms.openlocfilehash: 59afb9de3a97545407fe96f5ded60faee9d9f725
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536336"
---
# <a name="toolstripcontainer-control-overview"></a><span data-ttu-id="db59d-102">ToolStripContainer 控件概述</span><span class="sxs-lookup"><span data-stu-id="db59d-102">ToolStripContainer Control Overview</span></span>
<span data-ttu-id="db59d-103">A<xref:System.Windows.Forms.ToolStripContainer>面板在其左侧、 右侧、 顶部和底部均带有用于定位和漂浮<xref:System.Windows.Forms.ToolStrip>， <xref:System.Windows.Forms.MenuStrip>，和<xref:System.Windows.Forms.StatusStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="db59d-103">A <xref:System.Windows.Forms.ToolStripContainer> has panels on its left, right, top, and bottom sides for positioning and rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="db59d-104">如果将多个 <xref:System.Windows.Forms.ToolStrip> 控件放置在 <xref:System.Windows.Forms.ToolStripContainer> 左侧或右侧，它们会垂直堆叠。</span><span class="sxs-lookup"><span data-stu-id="db59d-104">Multiple <xref:System.Windows.Forms.ToolStrip> controls stack vertically if you put them in the left or right <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="db59d-105">如果将其放置在 <xref:System.Windows.Forms.ToolStripContainer> 顶部或底部，则水平堆叠。</span><span class="sxs-lookup"><span data-stu-id="db59d-105">They stack horizontally if you put them in the top or bottom <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="db59d-106">可使用 <xref:System.Windows.Forms.ToolStripContainer> 的中央 <xref:System.Windows.Forms.ToolStripContentPanel> 将传统控件放置在窗体上。</span><span class="sxs-lookup"><span data-stu-id="db59d-106">You can use the central <xref:System.Windows.Forms.ToolStripContentPanel> of the <xref:System.Windows.Forms.ToolStripContainer> to position traditional controls on the form.</span></span>  
  
 <span data-ttu-id="db59d-107">任何或所有 <xref:System.Windows.Forms.ToolStripContainer> 控件都可在设计时选择且可删除。</span><span class="sxs-lookup"><span data-stu-id="db59d-107">Any or all <xref:System.Windows.Forms.ToolStripContainer> controls are directly selectable at design time and can be deleted.</span></span> <span data-ttu-id="db59d-108">每个面板<xref:System.Windows.Forms.ToolStripContainer>是可展开和折叠的并调整其大小与它所包含的控件。</span><span class="sxs-lookup"><span data-stu-id="db59d-108">Each panel of a <xref:System.Windows.Forms.ToolStripContainer> is expandable and collapsible, and resizes with the controls that it contains.</span></span>  
  
### <a name="important-toolstripcontainer-members"></a><span data-ttu-id="db59d-109">重要 ToolStripContainer 成员</span><span class="sxs-lookup"><span data-stu-id="db59d-109">Important ToolStripContainer Members</span></span>  
  
|<span data-ttu-id="db59d-110">名称</span><span class="sxs-lookup"><span data-stu-id="db59d-110">Name</span></span>|<span data-ttu-id="db59d-111">描述</span><span class="sxs-lookup"><span data-stu-id="db59d-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|<span data-ttu-id="db59d-112">获取的底部面板<xref:System.Windows.Forms.ToolStripContainer>。</span><span class="sxs-lookup"><span data-stu-id="db59d-112">Gets the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|<span data-ttu-id="db59d-113">获取或设置一个值，该值指示是否的底部面板<xref:System.Windows.Forms.ToolStripContainer>可见。</span><span class="sxs-lookup"><span data-stu-id="db59d-113">Gets or sets a value indicating whether the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|<span data-ttu-id="db59d-114">获取的左的面板<xref:System.Windows.Forms.ToolStripContainer>。</span><span class="sxs-lookup"><span data-stu-id="db59d-114">Gets the left panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|<span data-ttu-id="db59d-115">获取或设置一个值，该值指示是否的左的面板<xref:System.Windows.Forms.ToolStripContainer>可见。</span><span class="sxs-lookup"><span data-stu-id="db59d-115">Gets or sets a value indicating whether the left panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|<span data-ttu-id="db59d-116">获取的右面板<xref:System.Windows.Forms.ToolStripContainer>。</span><span class="sxs-lookup"><span data-stu-id="db59d-116">Gets the right panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|<span data-ttu-id="db59d-117">获取或设置一个值，该值指示是否的右面板<xref:System.Windows.Forms.ToolStripContainer>可见。</span><span class="sxs-lookup"><span data-stu-id="db59d-117">Gets or sets a value indicating whether the right panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|<span data-ttu-id="db59d-118">获取的顶部面板<xref:System.Windows.Forms.ToolStripContainer>。</span><span class="sxs-lookup"><span data-stu-id="db59d-118">Gets the top panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|<span data-ttu-id="db59d-119">获取或设置一个值，该值指示是否的顶部面板<xref:System.Windows.Forms.ToolStripContainer>可见。</span><span class="sxs-lookup"><span data-stu-id="db59d-119">Gets or sets a value indicating whether the top panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="db59d-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="db59d-120">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 <xref:System.Windows.Forms.ToolStripContentPanel>
