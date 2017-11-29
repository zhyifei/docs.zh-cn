---
title: "ToolStripPanel 控件概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ToolStripPanel
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms], about ToolStripPanel control
ms.assetid: ce54a60c-5eba-4b4c-bd77-cf0748a666cc
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bed2f4cbdc2f7d2e2647e39163959aaf42ae8bab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="toolstrippanel-control-overview"></a><span data-ttu-id="5fdbc-102">ToolStripPanel 控件概述</span><span class="sxs-lookup"><span data-stu-id="5fdbc-102">ToolStripPanel Control Overview</span></span>
<span data-ttu-id="5fdbc-103">A<xref:System.Windows.Forms.ToolStripPanel>单个区域提供用于定位和漂浮<xref:System.Windows.Forms.ToolStrip>， <xref:System.Windows.Forms.MenuStrip>，和<xref:System.Windows.Forms.StatusStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="5fdbc-103">A <xref:System.Windows.Forms.ToolStripPanel> provides a single area for positioning and rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="5fdbc-104">多个<xref:System.Windows.Forms.ToolStrip>控件堆栈垂直或水平，具体取决于<xref:System.Windows.Forms.ToolStripPanelRow.Orientation%2A>的<xref:System.Windows.Forms.ToolStripPanel>。</span><span class="sxs-lookup"><span data-stu-id="5fdbc-104">Multiple <xref:System.Windows.Forms.ToolStrip> controls stack vertically or horizontally depending on the <xref:System.Windows.Forms.ToolStripPanelRow.Orientation%2A> of the <xref:System.Windows.Forms.ToolStripPanel>.</span></span>  
  
### <a name="important-toolstrippanel-members"></a><span data-ttu-id="5fdbc-105">重要 ToolStripPanel 成员</span><span class="sxs-lookup"><span data-stu-id="5fdbc-105">Important ToolStripPanel Members</span></span>  
  
|<span data-ttu-id="5fdbc-106">名称</span><span class="sxs-lookup"><span data-stu-id="5fdbc-106">Name</span></span>|<span data-ttu-id="5fdbc-107">描述</span><span class="sxs-lookup"><span data-stu-id="5fdbc-107">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripPanel.Orientation%2A>|<span data-ttu-id="5fdbc-108">获取或设置一个值，该值的水平或垂直方向<xref:System.Windows.Forms.ToolStripPanel>。</span><span class="sxs-lookup"><span data-stu-id="5fdbc-108">Gets or sets a value indicating the horizontal or vertical orientation of the <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.Renderer%2A>|<span data-ttu-id="5fdbc-109">获取或设置<xref:System.Windows.Forms.ToolStripRenderer>用于自定义的外观<xref:System.Windows.Forms.ToolStripPanel>。</span><span class="sxs-lookup"><span data-stu-id="5fdbc-109">Gets or sets a <xref:System.Windows.Forms.ToolStripRenderer> used to customize the appearance of a <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.RenderMode%2A>|<span data-ttu-id="5fdbc-110">获取或设置要应用于的绘制样式<xref:System.Windows.Forms.ToolStripPanel>。</span><span class="sxs-lookup"><span data-stu-id="5fdbc-110">Gets or sets the painting styles to be applied to the <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.RowMargin%2A>|<span data-ttu-id="5fdbc-111">获取或设置，以像素为单位，之间<xref:System.Windows.Forms.ToolStripPanelRow>和<xref:System.Windows.Forms.ToolStripPanel>。</span><span class="sxs-lookup"><span data-stu-id="5fdbc-111">Gets or sets the spacing, in pixels, between the <xref:System.Windows.Forms.ToolStripPanelRow> and the <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.Rows%2A>|<span data-ttu-id="5fdbc-112">获取<xref:System.Windows.Forms.ToolStripPanelRow>在此<xref:System.Windows.Forms.ToolStripPanel>。</span><span class="sxs-lookup"><span data-stu-id="5fdbc-112">Gets the <xref:System.Windows.Forms.ToolStripPanelRow> in this <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.Join%2A>|<span data-ttu-id="5fdbc-113">将添加<xref:System.Windows.Forms.ToolStrip>到<xref:System.Windows.Forms.ToolStripPanel>。</span><span class="sxs-lookup"><span data-stu-id="5fdbc-113">Adds a <xref:System.Windows.Forms.ToolStrip> to a <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5fdbc-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5fdbc-114">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 <xref:System.Windows.Forms.ToolStripContentPanel>  
 [<span data-ttu-id="5fdbc-115">ToolStrip 示例</span><span class="sxs-lookup"><span data-stu-id="5fdbc-115">ToolStrip Sample</span></span>](http://msdn.microsoft.com/en-us/b7352439-184a-4a3a-b2ad-07465d3af9ed)
