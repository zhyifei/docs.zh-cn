---
title: TableLayoutPanel 控件（Windows 窗体）
ms.date: 03/30/2017
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms]
- controls [Windows Forms], sizing
- sizing [Windows Forms], automatic
- layout [Windows Forms], TableLayoutPanel control
- automatic sizing
ms.assetid: f55175c6-424e-4782-a86e-3f79c1550235
ms.openlocfilehash: 3615ab1f9a9076b8db0e5fde1e5bd4a1a804f3bf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538523"
---
# <a name="tablelayoutpanel-control-windows-forms"></a><span data-ttu-id="a9018-102">TableLayoutPanel 控件（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="a9018-102">TableLayoutPanel Control (Windows Forms)</span></span>
<span data-ttu-id="a9018-103"><xref:System.Windows.Forms.TableLayoutPanel> 控件将其内容排列在网格中。</span><span class="sxs-lookup"><span data-stu-id="a9018-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="a9018-104">由于布局是同时在设计时和运行时执行的，因此它可随应用程序环境的变化而动态地变化。</span><span class="sxs-lookup"><span data-stu-id="a9018-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="a9018-105">这使得面板中的控件能够按比例调整大小，以便能够响应更改（例如父控件的大小调整或本地化产生的文本长度更改）。</span><span class="sxs-lookup"><span data-stu-id="a9018-105">This gives the controls in the panel the ability to proportionally resize, so it can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a9018-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="a9018-106">In This Section</span></span>  
 [<span data-ttu-id="a9018-107">TableLayoutPanel 控件概述</span><span class="sxs-lookup"><span data-stu-id="a9018-107">TableLayoutPanel Control Overview</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-overview.md)  
 <span data-ttu-id="a9018-108">介绍 <xref:System.Windows.Forms.TableLayoutPanel> 控件的一般概念，你可以用该控件创建具有行和列的布局。</span><span class="sxs-lookup"><span data-stu-id="a9018-108">Introduces the general concepts of the <xref:System.Windows.Forms.TableLayoutPanel> control, which allows you to create a layout with rows and columns.</span></span>  
  
 [<span data-ttu-id="a9018-109">有关 TableLayoutPanel 控件的最佳做法</span><span class="sxs-lookup"><span data-stu-id="a9018-109">Best Practices for the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="a9018-110">概述能够帮助你充分利用 <xref:System.Windows.Forms.TableLayoutPanel> 控件的布局功能的建议。</span><span class="sxs-lookup"><span data-stu-id="a9018-110">Outlines recommendations to help you get the most out of the layout features of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="a9018-111">TableLayoutPanel 控件中的自动调整大小行为</span><span class="sxs-lookup"><span data-stu-id="a9018-111">AutoSize Behavior in the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/autosize-behavior-in-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="a9018-112">说明 <xref:System.Windows.Forms.TableLayoutPanel> 控件支持自动调整大小行为的方式。</span><span class="sxs-lookup"><span data-stu-id="a9018-112">Explains the ways in which the <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior.</span></span>  
  
 [<span data-ttu-id="a9018-113">如何：在 TableLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="a9018-113">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 <span data-ttu-id="a9018-114">演示如何在 <xref:System.Windows.Forms.TableLayoutPanel> 控件中锚定和停靠子控件。</span><span class="sxs-lookup"><span data-stu-id="a9018-114">Shows how to anchor and dock child controls in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="a9018-115">如何：设计非常适合本地化的 Windows 窗体布局</span><span class="sxs-lookup"><span data-stu-id="a9018-115">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 <span data-ttu-id="a9018-116">演示使用 <xref:System.Windows.Forms.TableLayoutPanel> 控件来生成适合本地化的窗体。</span><span class="sxs-lookup"><span data-stu-id="a9018-116">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to localization.</span></span>  
  
 [<span data-ttu-id="a9018-117">如何：创建可重设大小的 Windows 窗体以供输入数据</span><span class="sxs-lookup"><span data-stu-id="a9018-117">How to: Create a Resizable Windows Form for Data Entry</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-resizable-windows-form-for-data-entry.md)  
 <span data-ttu-id="a9018-118">演示使用 <xref:System.Windows.Forms.TableLayoutPanel> 控件来生成能很好地响应大小调整的窗体。</span><span class="sxs-lookup"><span data-stu-id="a9018-118">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to resizing.</span></span>  
  
1.  <span data-ttu-id="a9018-119">[如何：在 TableLayoutPanel 控件中对齐和拉伸控件](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="a9018-119">[How to: Align and Stretch a Control in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span></span>  
  
2.  <span data-ttu-id="a9018-120">[如何：在 TableLayoutPanel 控件中跨行和跨列](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="a9018-120">[How to: Span Rows and Columns in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span></span>  
  
3.  <span data-ttu-id="a9018-121">[如何：在 TableLayoutPanel 控件中编辑行和列](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="a9018-121">[How to: Edit Columns and Rows in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span></span>  
  
4.  <span data-ttu-id="a9018-122">[演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="a9018-122">[Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a9018-123">参考</span><span class="sxs-lookup"><span data-stu-id="a9018-123">Reference</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <span data-ttu-id="a9018-124">提供关于 <xref:System.Windows.Forms.TableLayoutPanel> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="a9018-124">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 <xref:System.Windows.Forms.TableLayoutSettings>  
 <span data-ttu-id="a9018-125">提供 <xref:System.Windows.Forms.TableLayoutSettings> 类型的参考文档。</span><span class="sxs-lookup"><span data-stu-id="a9018-125">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutSettings> type.</span></span>  
  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <span data-ttu-id="a9018-126">提供关于 <xref:System.Windows.Forms.FlowLayoutPanel> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="a9018-126">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a9018-127">相关章节</span><span class="sxs-lookup"><span data-stu-id="a9018-127">Related Sections</span></span>  
 [<span data-ttu-id="a9018-128">本地化</span><span class="sxs-lookup"><span data-stu-id="a9018-128">Localization</span></span>](../../../../docs/standard/globalization-localization/localization.md)  
 <span data-ttu-id="a9018-129">提供对本地化相关主题的概述。</span><span class="sxs-lookup"><span data-stu-id="a9018-129">Provides an overview of topics relating to localization.</span></span>  
  
 <span data-ttu-id="a9018-130">另请参阅[本地化应用程序](http://msdn.microsoft.com/library/z68135h5\(v=vs.110\))或[本地化应用程序](http://msdn.microsoft.com/library/z68135h5\(v=vs.120\))</span><span class="sxs-lookup"><span data-stu-id="a9018-130">Also see [Localizing Applications](http://msdn.microsoft.com/library/z68135h5\(v=vs.110\)) or [Localizing Applications](http://msdn.microsoft.com/library/z68135h5\(v=vs.120\))</span></span>
