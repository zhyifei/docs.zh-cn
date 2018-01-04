---
title: "如何：在 TableLayoutPanel 控件中对齐和拉伸控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c8a852926f8b7a33fdaa1e2e16fea7eb1a1dac4b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a><span data-ttu-id="c3af1-102">如何：在 TableLayoutPanel 控件中对齐和拉伸控件</span><span class="sxs-lookup"><span data-stu-id="c3af1-102">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>
<span data-ttu-id="c3af1-103">您可以对齐和拉伸控件中的<xref:System.Windows.Forms.TableLayoutPanel>与<xref:System.Windows.Forms.Control.Anchor%2A>和<xref:System.Windows.Forms.Control.Dock%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="c3af1-103">You can align and stretch controls in a <xref:System.Windows.Forms.TableLayoutPanel> with the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3af1-104">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="c3af1-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c3af1-105">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="c3af1-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c3af1-106">有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="c3af1-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-align-and-stretch-a-control"></a><span data-ttu-id="c3af1-107">若要对齐和拉伸控件</span><span class="sxs-lookup"><span data-stu-id="c3af1-107">To align and stretch a control</span></span>  
  
1.  <span data-ttu-id="c3af1-108">拖动<xref:System.Windows.Forms.TableLayoutPanel>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="c3af1-108">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="c3af1-109">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到的左上角单元格中<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="c3af1-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="c3af1-110"><xref:System.Windows.Forms.Button>控件居中的单元格中。</span><span class="sxs-lookup"><span data-stu-id="c3af1-110">The <xref:System.Windows.Forms.Button> control is centered in the cell.</span></span>  
  
3.  <span data-ttu-id="c3af1-111">设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性`Left,Right`。</span><span class="sxs-lookup"><span data-stu-id="c3af1-111">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left,Right`.</span></span> <span data-ttu-id="c3af1-112"><xref:System.Windows.Forms.Button>控件将拉伸到匹配的单元格的宽度。</span><span class="sxs-lookup"><span data-stu-id="c3af1-112">The <xref:System.Windows.Forms.Button> control stretches to match the width of the cell.</span></span>  
  
4.  <span data-ttu-id="c3af1-113">设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性`Top,Bottom`。</span><span class="sxs-lookup"><span data-stu-id="c3af1-113">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top,Bottom`.</span></span> <span data-ttu-id="c3af1-114"><xref:System.Windows.Forms.Button>控件将拉伸到匹配的单元格的高度。</span><span class="sxs-lookup"><span data-stu-id="c3af1-114">The <xref:System.Windows.Forms.Button> control stretches to match the height of the cell.</span></span>  
  
5.  <span data-ttu-id="c3af1-115">设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Dock%2A>属性<xref:System.Windows.Forms.DockStyle.Fill>。</span><span class="sxs-lookup"><span data-stu-id="c3af1-115">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="c3af1-116"><xref:System.Windows.Forms.Button>控件扩展以填充单元格。</span><span class="sxs-lookup"><span data-stu-id="c3af1-116">The <xref:System.Windows.Forms.Button> control expands to fill the cell.</span></span>  
  
6.  <span data-ttu-id="c3af1-117">设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Dock%2A>属性<xref:System.Windows.Forms.DockStyle.None>。</span><span class="sxs-lookup"><span data-stu-id="c3af1-117">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.None>.</span></span> <span data-ttu-id="c3af1-118"><xref:System.Windows.Forms.Button>控件返回到其原始大小，并将移动到单元格的左上角。</span><span class="sxs-lookup"><span data-stu-id="c3af1-118">The <xref:System.Windows.Forms.Button> control returns to its original size and moves to the upper-left corner of the cell.</span></span> <span data-ttu-id="c3af1-119">**Windows 窗体设计器**已设置<xref:System.Windows.Forms.Control.Anchor%2A>属性`Top, Left`。</span><span class="sxs-lookup"><span data-stu-id="c3af1-119">The **Windows Forms Designer** has set the <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span>  
  
7.  <span data-ttu-id="c3af1-120">设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性`Bottom,Right`。</span><span class="sxs-lookup"><span data-stu-id="c3af1-120">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Bottom,Right`.</span></span> <span data-ttu-id="c3af1-121"><xref:System.Windows.Forms.Button>控件移动到单元格右下角。</span><span class="sxs-lookup"><span data-stu-id="c3af1-121">The <xref:System.Windows.Forms.Button> control moves to the lower-right corner of the cell.</span></span>  
  
8.  <span data-ttu-id="c3af1-122">设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性<xref:System.Windows.Forms.AnchorStyles.None>。</span><span class="sxs-lookup"><span data-stu-id="c3af1-122">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.None>.</span></span> <span data-ttu-id="c3af1-123"><xref:System.Windows.Forms.Button>控件将移动到单元格的中心。</span><span class="sxs-lookup"><span data-stu-id="c3af1-123">The <xref:System.Windows.Forms.Button> control moves to the center of the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3af1-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3af1-124">See Also</span></span>  
 [<span data-ttu-id="c3af1-125">TableLayoutPanel 控件</span><span class="sxs-lookup"><span data-stu-id="c3af1-125">TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
