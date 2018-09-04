---
title: TableLayoutPanel 控件概述
ms.date: 03/30/2017
f1_keywords:
- TableLayoutPanel
helpviewer_keywords:
- controls [Windows Forms], resizing
- resizable controls [Windows Forms]
- Windows Forms controls, proportional resizing
- Windows Forms, proportional resizing of controls
- layout [Windows Forms], TableLayoutPanel control
- TableLayoutPanel control [Windows Forms], about TableLayoutPanel control
ms.assetid: 337661c8-61cb-44ee-93e0-3662bddec327
ms.openlocfilehash: be7ef4055d809349fe97a3d48e29158c5449576b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43562137"
---
# <a name="tablelayoutpanel-control-overview"></a><span data-ttu-id="b4a71-102">TableLayoutPanel 控件概述</span><span class="sxs-lookup"><span data-stu-id="b4a71-102">TableLayoutPanel Control Overview</span></span>
<span data-ttu-id="b4a71-103"><xref:System.Windows.Forms.TableLayoutPanel> 控件将其内容排列在网格中。</span><span class="sxs-lookup"><span data-stu-id="b4a71-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="b4a71-104">由于布局是同时在设计时和运行时执行的，因此它可随应用程序环境的变化而动态地变化。</span><span class="sxs-lookup"><span data-stu-id="b4a71-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="b4a71-105">这使得面板中的控件能够按比例调整大小，以便能够响应更改（例如父控件的大小调整或本地化产生的文本长度更改）。</span><span class="sxs-lookup"><span data-stu-id="b4a71-105">This gives the controls in the panel the ability to proportionally resize, so they can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
 <span data-ttu-id="b4a71-106">任何 Windows 窗体控件均可以是 <xref:System.Windows.Forms.TableLayoutPanel> 控制的子控件，包括 <xref:System.Windows.Forms.TableLayoutPanel> 的其他实例。</span><span class="sxs-lookup"><span data-stu-id="b4a71-106">Any Windows Forms control can be a child of the <xref:System.Windows.Forms.TableLayoutPanel> control, including other instances of <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="b4a71-107">这使你可以构造适应在运行时发生更改的复杂布局。</span><span class="sxs-lookup"><span data-stu-id="b4a71-107">This allows you to construct sophisticated layouts that adapt to changes at run time.</span></span>  
  
 <span data-ttu-id="b4a71-108">添加新控件时，<xref:System.Windows.Forms.TableLayoutPanel> 控件可扩展以容纳新控件，具体取决于 <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>、<xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> 和 <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> 属性的值。</span><span class="sxs-lookup"><span data-stu-id="b4a71-108">The <xref:System.Windows.Forms.TableLayoutPanel> control can expand to accommodate new controls when they are added, depending on the value of the <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A>, and <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> properties.</span></span> <span data-ttu-id="b4a71-109">将 <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> 或 <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> 属性的值设置为 0 指定将取消 <xref:System.Windows.Forms.TableLayoutPanel> 在相应方向的绑定。</span><span class="sxs-lookup"><span data-stu-id="b4a71-109">Setting either the <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> or <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> property to a value of 0 specifies that the <xref:System.Windows.Forms.TableLayoutPanel> will be unbound in the corresponding direction.</span></span>  
  
 <span data-ttu-id="b4a71-110">在 <xref:System.Windows.Forms.TableLayoutPanel> 控件充满子控件后，还可控制扩展的方向（水平或垂直）。</span><span class="sxs-lookup"><span data-stu-id="b4a71-110">You can also control the direction of expansion (horizontal or vertical) after the <xref:System.Windows.Forms.TableLayoutPanel> control is full of child controls.</span></span> <span data-ttu-id="b4a71-111">默认情况下，<xref:System.Windows.Forms.TableLayoutPanel> 控件通过添加行向下扩展。</span><span class="sxs-lookup"><span data-stu-id="b4a71-111">By default, the <xref:System.Windows.Forms.TableLayoutPanel> control expands downward by adding rows.</span></span>  
  
 <span data-ttu-id="b4a71-112">如果需要使行和列的行为不同于默认行为，可以通过使用 <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> 和 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 属性来控制行和列的属性。</span><span class="sxs-lookup"><span data-stu-id="b4a71-112">If you want rows and columns that behave differently from the default behavior, you can control the properties of rows and columns by using the <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> and <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> properties.</span></span> <span data-ttu-id="b4a71-113">可分别设置行或列的属性。</span><span class="sxs-lookup"><span data-stu-id="b4a71-113">You can set the properties of rows or columns individually.</span></span>  
  
 <span data-ttu-id="b4a71-114"><xref:System.Windows.Forms.TableLayoutPanel> 控件将以下属性添加到其子控件中：`Cell`、`Column`、`Row`、`ColumnSpan` 和 `RowSpan`。</span><span class="sxs-lookup"><span data-stu-id="b4a71-114">The <xref:System.Windows.Forms.TableLayoutPanel> control adds the following properties to its child controls: `Cell`, `Column`, `Row`, `ColumnSpan`, and `RowSpan`.</span></span>  
  
 <span data-ttu-id="b4a71-115">可以通过设置子控件上的 `ColumnSpan` 或 `RowSpan` 属性来合并 <xref:System.Windows.Forms.TableLayoutPanel> 控件中的单元格。</span><span class="sxs-lookup"><span data-stu-id="b4a71-115">You can merge cells in the <xref:System.Windows.Forms.TableLayoutPanel> control by setting the `ColumnSpan` or `RowSpan` properties on a child control.</span></span>  
  
1.  [<span data-ttu-id="b4a71-116">如何：在 TableLayoutPanel 控件中对齐和拉伸控件</span><span class="sxs-lookup"><span data-stu-id="b4a71-116">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2.  [<span data-ttu-id="b4a71-117">如何：在 TableLayoutPanel 控件中跨行和跨列</span><span class="sxs-lookup"><span data-stu-id="b4a71-117">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
3.  [<span data-ttu-id="b4a71-118">如何：在 TableLayoutPanel 控件中编辑行和列</span><span class="sxs-lookup"><span data-stu-id="b4a71-118">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
4.  <span data-ttu-id="b4a71-119">[演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件](https://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="b4a71-119">[Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](https://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4a71-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4a71-120">See Also</span></span>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutSettings>  
 [<span data-ttu-id="b4a71-121">如何：设计非常适合本地化的 Windows 窗体布局</span><span class="sxs-lookup"><span data-stu-id="b4a71-121">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 [<span data-ttu-id="b4a71-122">如何：创建可重设大小的 Windows 窗体以供输入数据</span><span class="sxs-lookup"><span data-stu-id="b4a71-122">How to: Create a Resizable Windows Form for Data Entry</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-resizable-windows-form-for-data-entry.md)  
 [<span data-ttu-id="b4a71-123">有关 TableLayoutPanel 控件的最佳做法</span><span class="sxs-lookup"><span data-stu-id="b4a71-123">Best Practices for the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)
