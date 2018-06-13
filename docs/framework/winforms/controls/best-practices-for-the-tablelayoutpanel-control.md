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
ms.openlocfilehash: 40322dc6c5facd4167a4c9ac5c12fdf2a8831b7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526447"
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a><span data-ttu-id="e4fa0-102">TableLayoutPanel 控件的最佳做法</span><span class="sxs-lookup"><span data-stu-id="e4fa0-102">Best Practices for the TableLayoutPanel Control</span></span>
<span data-ttu-id="e4fa0-103"><xref:System.Windows.Forms.TableLayoutPanel>控件提供了强大的布局功能，应在 Windows 窗体上使用之前应该认真考虑。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-103">The <xref:System.Windows.Forms.TableLayoutPanel> control provides powerful layout features that you should consider carefully before using on your Windows Forms.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="e4fa0-104">建议</span><span class="sxs-lookup"><span data-stu-id="e4fa0-104">Recommendations</span></span>  
 <span data-ttu-id="e4fa0-105">以下建议将帮助你使用<xref:System.Windows.Forms.TableLayoutPanel>其充分利用的控件。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-105">The following recommendations will help you use the <xref:System.Windows.Forms.TableLayoutPanel> control to its best advantage.</span></span>  
  
### <a name="targeted-use"></a><span data-ttu-id="e4fa0-106">目标的使用</span><span class="sxs-lookup"><span data-stu-id="e4fa0-106">Targeted Use</span></span>  
 <span data-ttu-id="e4fa0-107">使用<xref:System.Windows.Forms.TableLayoutPanel>尽量少控制。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-107">Use the <xref:System.Windows.Forms.TableLayoutPanel> control sparingly.</span></span> <span data-ttu-id="e4fa0-108">你不应在要求可调整大小的布局的所有情况下使用它。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-108">You should not use it in all situations that require a resizable layout.</span></span> <span data-ttu-id="e4fa0-109">以下列表介绍了利用从受益最大的布局<xref:System.Windows.Forms.TableLayoutPanel>控件：</span><span class="sxs-lookup"><span data-stu-id="e4fa0-109">The following list describes layouts that benefit most from the use of the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>  
  
-   <span data-ttu-id="e4fa0-110">其中有相互成比例调整大小的多个部分的窗体的布局。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-110">Layouts in which there are multiple parts of the form that resize proportionally to each other.</span></span>  
  
-   <span data-ttu-id="e4fa0-111">将修改或动态生成在运行时，如具有加上或减去的用户可自定义字段的数据输入窗体根据首选项的布局。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-111">Layouts that will be modified or generated dynamically at run time, such as data entry forms that have user-customizable fields added or subtracted based on preferences.</span></span>  
  
-   <span data-ttu-id="e4fa0-112">应保留在总体的固定大小的布局。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-112">Layouts that should remain at an overall fixed size.</span></span> <span data-ttu-id="e4fa0-113">例如，你可能有一个对话框，应保持小于 800 x 600，但你需要支持本地化的字符串。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-113">For example, you may have a dialog box that should remain smaller than 800 x 600, but you need to support localized strings.</span></span>  
  
 <span data-ttu-id="e4fa0-114">以下列表介绍执行不会大大受益于使用的布局<xref:System.Windows.Forms.TableLayoutPanel>控件：</span><span class="sxs-lookup"><span data-stu-id="e4fa0-114">The following list describes layouts that do not benefit greatly from using the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>  
  
-   <span data-ttu-id="e4fa0-115">简单数据输入窗体与单个列的标签和文本输入区域的单个列。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-115">Simple data entry forms with a single column of labels and a single column of text-entry areas.</span></span>  
  
-   <span data-ttu-id="e4fa0-116">含有单个较大的窗体显示应填满所有可用的空间，在调整大小时的区域。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-116">Forms with a single large display area that should fill all the available space when a resize occurs.</span></span> <span data-ttu-id="e4fa0-117">此示例是窗体中显示单个<xref:System.Windows.Forms.PropertyGrid>控件。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-117">An example of this is a form that displays a single <xref:System.Windows.Forms.PropertyGrid> control.</span></span> <span data-ttu-id="e4fa0-118">在这种情况下，使用锚定，因为没有任何其他应展开时调整窗体。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-118">In this case, use anchoring, because nothing else should expand when the form is resized.</span></span>  
  
 <span data-ttu-id="e4fa0-119">请仔细选择哪些控件需要在<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-119">Choose carefully which controls need to be in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="e4fa0-120">如果你有为你的文本使用锚定的 30%的增长留出空间，请考虑使用<xref:System.Windows.Forms.Control.Anchor%2A>仅属性。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-120">If you have room for your text to grow by 30% using anchoring, consider using the <xref:System.Windows.Forms.Control.Anchor%2A> property only.</span></span> <span data-ttu-id="e4fa0-121">如果你可以估计需要你的布局的空间，使用的<xref:System.Windows.Forms.Control.Dock%2A>和<xref:System.Windows.Forms.Control.Anchor%2A>比估计剩余空间的详细信息和<xref:System.Windows.Forms.Control.AutoSize%2A>行为。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-121">If you can estimate the space required by your layout, use of <xref:System.Windows.Forms.Control.Dock%2A> and <xref:System.Windows.Forms.Control.Anchor%2A> is easier than estimating the details of remaining space and <xref:System.Windows.Forms.Control.AutoSize%2A> behavior.</span></span>  
  
 <span data-ttu-id="e4fa0-122">通常，在设计你使用的布局时<xref:System.Windows.Forms.TableLayoutPanel>控制，使设计保持尽可能简单。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-122">In general, when designing your layout with the <xref:System.Windows.Forms.TableLayoutPanel> control, keep the design as simple as possible.</span></span>  
  
### <a name="use-the-document-outline-window"></a><span data-ttu-id="e4fa0-123">使用文档大纲窗口</span><span class="sxs-lookup"><span data-stu-id="e4fa0-123">Use the Document Outline Window</span></span>  
 <span data-ttu-id="e4fa0-124">文档大纲窗口提供了你的布局，可用于处理你的控件的 z 顺序和父-子关系的树视图。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-124">The Document Outline window gives you a tree view of your layout, which you can use to manipulate the z-order and parent-child relationships of your controls.</span></span> <span data-ttu-id="e4fa0-125">从**视图菜单**，选择**其他窗口**，然后选择**文档大纲**。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-125">From the **View menu**, select **Other Windows**, then select **Document Outline**.</span></span>  
  
### <a name="avoid-nesting"></a><span data-ttu-id="e4fa0-126">避免嵌套</span><span class="sxs-lookup"><span data-stu-id="e4fa0-126">Avoid Nesting</span></span>  
 <span data-ttu-id="e4fa0-127">避免嵌套其他<xref:System.Windows.Forms.TableLayoutPanel>内控制<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-127">Avoid nesting other <xref:System.Windows.Forms.TableLayoutPanel> controls within a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="e4fa0-128">调试嵌套的布局可能很困难。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-128">Debugging nested layouts can be difficult.</span></span>  
  
### <a name="avoid-visual-inheritance"></a><span data-ttu-id="e4fa0-129">避免 Visual 继承</span><span class="sxs-lookup"><span data-stu-id="e4fa0-129">Avoid Visual Inheritance</span></span>  
 <span data-ttu-id="e4fa0-130"><xref:System.Windows.Forms.TableLayoutPanel>控件不支持在 Windows 窗体设计器 visual 继承。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-130">The <xref:System.Windows.Forms.TableLayoutPanel> control does not support visual inheritance in the Windows Forms Designer.</span></span> <span data-ttu-id="e4fa0-131">A<xref:System.Windows.Forms.TableLayoutPanel>为"已锁定"在设计时，将出现在派生类中的控件。</span><span class="sxs-lookup"><span data-stu-id="e4fa0-131">A <xref:System.Windows.Forms.TableLayoutPanel> control in a derived class appears as "locked" at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4fa0-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4fa0-132">See Also</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>
