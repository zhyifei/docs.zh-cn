---
title: TableLayoutPanel 控件的最佳做法
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- TableLayoutPanel control [Windows Forms], best practices
- forms [Windows Forms], best practices
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- layout [Windows Forms], AutoSize
- layout [Windows Forms], best practices
- best practices [Windows Forms], tableLayoutPanel control
- sizing [Windows Forms], automatic
- automatic sizing
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
ms.openlocfilehash: 6be6d0904d5b52e5188f0a5a16aaefa08265379c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674188"
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a><span data-ttu-id="60cb7-102">TableLayoutPanel 控件的最佳做法</span><span class="sxs-lookup"><span data-stu-id="60cb7-102">Best Practices for the TableLayoutPanel Control</span></span>
<span data-ttu-id="60cb7-103"><xref:System.Windows.Forms.TableLayoutPanel>控件提供了强大的布局功能，应在 Windows 窗体上使用之前仔细考虑。</span><span class="sxs-lookup"><span data-stu-id="60cb7-103">The <xref:System.Windows.Forms.TableLayoutPanel> control provides powerful layout features that you should consider carefully before using on your Windows Forms.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="60cb7-104">建议</span><span class="sxs-lookup"><span data-stu-id="60cb7-104">Recommendations</span></span>  
 <span data-ttu-id="60cb7-105">以下建议将帮助你使用<xref:System.Windows.Forms.TableLayoutPanel>最有效地控制。</span><span class="sxs-lookup"><span data-stu-id="60cb7-105">The following recommendations will help you use the <xref:System.Windows.Forms.TableLayoutPanel> control to its best advantage.</span></span>  
  
### <a name="targeted-use"></a><span data-ttu-id="60cb7-106">目标的使用</span><span class="sxs-lookup"><span data-stu-id="60cb7-106">Targeted Use</span></span>  
 <span data-ttu-id="60cb7-107">使用<xref:System.Windows.Forms.TableLayoutPanel>谨慎控制。</span><span class="sxs-lookup"><span data-stu-id="60cb7-107">Use the <xref:System.Windows.Forms.TableLayoutPanel> control sparingly.</span></span> <span data-ttu-id="60cb7-108">不应使用它在所有情况下，需要可调整大小的布局。</span><span class="sxs-lookup"><span data-stu-id="60cb7-108">You should not use it in all situations that require a resizable layout.</span></span> <span data-ttu-id="60cb7-109">以下列表介绍从使用获益最多的布局<xref:System.Windows.Forms.TableLayoutPanel>控件：</span><span class="sxs-lookup"><span data-stu-id="60cb7-109">The following list describes layouts that benefit most from the use of the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>  
  
-   <span data-ttu-id="60cb7-110">其中有个彼此的按比例调整大小的多个部分的窗体的布局。</span><span class="sxs-lookup"><span data-stu-id="60cb7-110">Layouts in which there are multiple parts of the form that resize proportionally to each other.</span></span>  
  
-   <span data-ttu-id="60cb7-111">将修改或在运行时，如数据输入窗体具有加上或减去的用户可自定义字段的动态生成的布局根据首选项。</span><span class="sxs-lookup"><span data-stu-id="60cb7-111">Layouts that will be modified or generated dynamically at run time, such as data entry forms that have user-customizable fields added or subtracted based on preferences.</span></span>  
  
-   <span data-ttu-id="60cb7-112">应保持为整体的固定大小的布局。</span><span class="sxs-lookup"><span data-stu-id="60cb7-112">Layouts that should remain at an overall fixed size.</span></span> <span data-ttu-id="60cb7-113">例如，可能有一个对话框，应保持小于 800 x 600，但你需要支持本地化的字符串。</span><span class="sxs-lookup"><span data-stu-id="60cb7-113">For example, you may have a dialog box that should remain smaller than 800 x 600, but you need to support localized strings.</span></span>  
  
 <span data-ttu-id="60cb7-114">以下列表介绍执行不会大大受益于使用的布局<xref:System.Windows.Forms.TableLayoutPanel>控件：</span><span class="sxs-lookup"><span data-stu-id="60cb7-114">The following list describes layouts that do not benefit greatly from using the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>  
  
-   <span data-ttu-id="60cb7-115">简单数据输入窗体包含单个列的标签和文本输入区域的单个列。</span><span class="sxs-lookup"><span data-stu-id="60cb7-115">Simple data entry forms with a single column of labels and a single column of text-entry areas.</span></span>  
  
-   <span data-ttu-id="60cb7-116">含有单个较大的窗体显示在调整大小时应填充所有可用空间的区域。</span><span class="sxs-lookup"><span data-stu-id="60cb7-116">Forms with a single large display area that should fill all the available space when a resize occurs.</span></span> <span data-ttu-id="60cb7-117">此示例是窗体中显示单个<xref:System.Windows.Forms.PropertyGrid>控件。</span><span class="sxs-lookup"><span data-stu-id="60cb7-117">An example of this is a form that displays a single <xref:System.Windows.Forms.PropertyGrid> control.</span></span> <span data-ttu-id="60cb7-118">在这种情况下，使用定位功能，因为没有其他应展开时调整窗体。</span><span class="sxs-lookup"><span data-stu-id="60cb7-118">In this case, use anchoring, because nothing else should expand when the form is resized.</span></span>  
  
 <span data-ttu-id="60cb7-119">请仔细选择哪些控件必须位于<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="60cb7-119">Choose carefully which controls need to be in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="60cb7-120">如果为文本使用锚定的 30%的增长留出空间，请考虑使用<xref:System.Windows.Forms.Control.Anchor%2A>只属性。</span><span class="sxs-lookup"><span data-stu-id="60cb7-120">If you have room for your text to grow by 30% using anchoring, consider using the <xref:System.Windows.Forms.Control.Anchor%2A> property only.</span></span> <span data-ttu-id="60cb7-121">如果在可以估计您的布局所需的空间，请使用<xref:System.Windows.Forms.Control.Dock%2A>并<xref:System.Windows.Forms.Control.Anchor%2A>是更容易估计的剩余空间的详细信息和<xref:System.Windows.Forms.Control.AutoSize%2A>行为。</span><span class="sxs-lookup"><span data-stu-id="60cb7-121">If you can estimate the space required by your layout, use of <xref:System.Windows.Forms.Control.Dock%2A> and <xref:System.Windows.Forms.Control.Anchor%2A> is easier than estimating the details of remaining space and <xref:System.Windows.Forms.Control.AutoSize%2A> behavior.</span></span>  
  
 <span data-ttu-id="60cb7-122">通常，当设计与布局中<xref:System.Windows.Forms.TableLayoutPanel>控件，使设计尽可能简单。</span><span class="sxs-lookup"><span data-stu-id="60cb7-122">In general, when designing your layout with the <xref:System.Windows.Forms.TableLayoutPanel> control, keep the design as simple as possible.</span></span>  
  
### <a name="use-the-document-outline-window"></a><span data-ttu-id="60cb7-123">使用文档大纲窗口</span><span class="sxs-lookup"><span data-stu-id="60cb7-123">Use the Document Outline Window</span></span>  
 <span data-ttu-id="60cb7-124">文档大纲窗口提供了您的布局，可用于处理您的控件的 z 顺序和父-子关系的树视图。</span><span class="sxs-lookup"><span data-stu-id="60cb7-124">The Document Outline window gives you a tree view of your layout, which you can use to manipulate the z-order and parent-child relationships of your controls.</span></span> <span data-ttu-id="60cb7-125">从**视图菜单**，选择**其他 Windows**，然后选择**文档大纲**。</span><span class="sxs-lookup"><span data-stu-id="60cb7-125">From the **View menu**, select **Other Windows**, then select **Document Outline**.</span></span>  
  
### <a name="avoid-nesting"></a><span data-ttu-id="60cb7-126">避免嵌套</span><span class="sxs-lookup"><span data-stu-id="60cb7-126">Avoid Nesting</span></span>  
 <span data-ttu-id="60cb7-127">避免其他嵌套<xref:System.Windows.Forms.TableLayoutPanel>控件的<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="60cb7-127">Avoid nesting other <xref:System.Windows.Forms.TableLayoutPanel> controls within a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="60cb7-128">调试嵌套的布局可能很困难。</span><span class="sxs-lookup"><span data-stu-id="60cb7-128">Debugging nested layouts can be difficult.</span></span>  
  
### <a name="avoid-visual-inheritance"></a><span data-ttu-id="60cb7-129">避免 Visual 继承</span><span class="sxs-lookup"><span data-stu-id="60cb7-129">Avoid Visual Inheritance</span></span>  
 <span data-ttu-id="60cb7-130"><xref:System.Windows.Forms.TableLayoutPanel>控件在 Windows 窗体设计器中不支持 visual 继承。</span><span class="sxs-lookup"><span data-stu-id="60cb7-130">The <xref:System.Windows.Forms.TableLayoutPanel> control does not support visual inheritance in the Windows Forms Designer.</span></span> <span data-ttu-id="60cb7-131">一个<xref:System.Windows.Forms.TableLayoutPanel>派生类中的控件将显示为"已锁定"在设计时。</span><span class="sxs-lookup"><span data-stu-id="60cb7-131">A <xref:System.Windows.Forms.TableLayoutPanel> control in a derived class appears as "locked" at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60cb7-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="60cb7-132">See also</span></span>
- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
