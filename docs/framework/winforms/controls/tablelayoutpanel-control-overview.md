---
title: "TableLayoutPanel 控件概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: TableLayoutPanel
helpviewer_keywords:
- controls [Windows Forms], resizing
- resizable controls [Windows Forms]
- Windows Forms controls, proportional resizing
- Windows Forms, proportional resizing of controls
- layout [Windows Forms], TableLayoutPanel control
- TableLayoutPanel control [Windows Forms], about TableLayoutPanel control
ms.assetid: 337661c8-61cb-44ee-93e0-3662bddec327
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fd8d68aa57ffe8b6fb84ceddf9d01aed56d40bdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="tablelayoutpanel-control-overview"></a><span data-ttu-id="08428-102">TableLayoutPanel 控件概述</span><span class="sxs-lookup"><span data-stu-id="08428-102">TableLayoutPanel Control Overview</span></span>
<span data-ttu-id="08428-103"><xref:System.Windows.Forms.TableLayoutPanel> 控件将其内容排列在网格中。</span><span class="sxs-lookup"><span data-stu-id="08428-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="08428-104">由于布局是同时在设计时和运行时执行的，因此它可随应用程序环境的变化而动态地变化。</span><span class="sxs-lookup"><span data-stu-id="08428-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="08428-105">这使得面板中的控件能够按比例调整大小，以便能够响应更改（例如父控件的大小调整或本地化产生的文本长度更改）。</span><span class="sxs-lookup"><span data-stu-id="08428-105">This gives the controls in the panel the ability to proportionally resize, so they can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
 <span data-ttu-id="08428-106">任何 Windows 窗体控件均可以是 <xref:System.Windows.Forms.TableLayoutPanel> 控制的子控件，包括 <xref:System.Windows.Forms.TableLayoutPanel> 的其他实例。</span><span class="sxs-lookup"><span data-stu-id="08428-106">Any Windows Forms control can be a child of the <xref:System.Windows.Forms.TableLayoutPanel> control, including other instances of <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="08428-107">这使你可以构造适应在运行时发生更改的复杂布局。</span><span class="sxs-lookup"><span data-stu-id="08428-107">This allows you to construct sophisticated layouts that adapt to changes at run time.</span></span>  
  
 <span data-ttu-id="08428-108">添加新控件时，<xref:System.Windows.Forms.TableLayoutPanel> 控件可扩展以容纳新控件，具体取决于 <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>、<xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> 和 <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> 属性的值。</span><span class="sxs-lookup"><span data-stu-id="08428-108">The <xref:System.Windows.Forms.TableLayoutPanel> control can expand to accommodate new controls when they are added, depending on the value of the <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A>, and <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> properties.</span></span> <span data-ttu-id="08428-109">将 <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> 或 <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> 属性的值设置为 0 指定将取消 <xref:System.Windows.Forms.TableLayoutPanel> 在相应方向的绑定。</span><span class="sxs-lookup"><span data-stu-id="08428-109">Setting either the <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> or <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> property to a value of 0 specifies that the <xref:System.Windows.Forms.TableLayoutPanel> will be unbound in the corresponding direction.</span></span>  
  
 <span data-ttu-id="08428-110">在 <xref:System.Windows.Forms.TableLayoutPanel> 控件充满子控件后，还可控制扩展的方向（水平或垂直）。</span><span class="sxs-lookup"><span data-stu-id="08428-110">You can also control the direction of expansion (horizontal or vertical) after the <xref:System.Windows.Forms.TableLayoutPanel> control is full of child controls.</span></span> <span data-ttu-id="08428-111">默认情况下，<xref:System.Windows.Forms.TableLayoutPanel> 控件通过添加行向下扩展。</span><span class="sxs-lookup"><span data-stu-id="08428-111">By default, the <xref:System.Windows.Forms.TableLayoutPanel> control expands downward by adding rows.</span></span>  
  
 <span data-ttu-id="08428-112">如果需要使行和列的行为不同于默认行为，可以通过使用 <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> 和 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 属性来控制行和列的属性。</span><span class="sxs-lookup"><span data-stu-id="08428-112">If you want rows and columns that behave differently from the default behavior, you can control the properties of rows and columns by using the <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> and <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> properties.</span></span> <span data-ttu-id="08428-113">可分别设置行或列的属性。</span><span class="sxs-lookup"><span data-stu-id="08428-113">You can set the properties of rows or columns individually.</span></span>  
  
 <span data-ttu-id="08428-114"><xref:System.Windows.Forms.TableLayoutPanel> 控件将以下属性添加到其子控件中：`Cell`、`Column`、`Row`、`ColumnSpan` 和 `RowSpan`。</span><span class="sxs-lookup"><span data-stu-id="08428-114">The <xref:System.Windows.Forms.TableLayoutPanel> control adds the following properties to its child controls: `Cell`, `Column`, `Row`, `ColumnSpan`, and `RowSpan`.</span></span>  
  
 <span data-ttu-id="08428-115">可以通过设置子控件上的 `ColumnSpan` 或 `RowSpan` 属性来合并 <xref:System.Windows.Forms.TableLayoutPanel> 控件中的单元格。</span><span class="sxs-lookup"><span data-stu-id="08428-115">You can merge cells in the <xref:System.Windows.Forms.TableLayoutPanel> control by setting the `ColumnSpan` or `RowSpan` properties on a child control.</span></span>  
  
1.  <span data-ttu-id="08428-116">[如何：在 TableLayoutPanel 控件中对齐和拉伸控件](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="08428-116">[How to: Align and Stretch a Control in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span></span>  
  
2.  <span data-ttu-id="08428-117">[如何：在 TableLayoutPanel 控件中跨行和跨列](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="08428-117">[How to: Span Rows and Columns in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span></span>  
  
3.  <span data-ttu-id="08428-118">[如何：在 TableLayoutPanel 控件中编辑行和列](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="08428-118">[How to: Edit Columns and Rows in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span></span>  
  
4.  <span data-ttu-id="08428-119">[演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="08428-119">[Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08428-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08428-120">See Also</span></span>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutSettings>  
 [<span data-ttu-id="08428-121">如何：设计非常适合本地化的 Windows 窗体布局</span><span class="sxs-lookup"><span data-stu-id="08428-121">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 [<span data-ttu-id="08428-122">如何：创建可重设大小的 Windows 窗体以供输入数据</span><span class="sxs-lookup"><span data-stu-id="08428-122">How to: Create a Resizable Windows Form for Data Entry</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-resizable-windows-form-for-data-entry.md)  
 [<span data-ttu-id="08428-123">有关 TableLayoutPanel 控件的最佳做法</span><span class="sxs-lookup"><span data-stu-id="08428-123">Best Practices for the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)
