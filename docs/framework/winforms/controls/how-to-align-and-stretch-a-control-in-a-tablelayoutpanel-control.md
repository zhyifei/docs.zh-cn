---
title: 如何：在 TableLayoutPanel 控件中对齐和拉伸控件
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
ms.openlocfilehash: fd32593bcad9e3f3ef93edee8aa2659d423f9feb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210367"
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a><span data-ttu-id="b89ec-102">如何：在 TableLayoutPanel 控件中对齐和拉伸控件</span><span class="sxs-lookup"><span data-stu-id="b89ec-102">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>

<span data-ttu-id="b89ec-103">您可以对齐和拉伸控件中的<xref:System.Windows.Forms.TableLayoutPanel>与<xref:System.Windows.Forms.Control.Anchor%2A>和<xref:System.Windows.Forms.Control.Dock%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="b89ec-103">You can align and stretch controls in a <xref:System.Windows.Forms.TableLayoutPanel> with the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties.</span></span>

## <a name="align-and-stretch-a-control"></a><span data-ttu-id="b89ec-104">对齐和拉伸控件</span><span class="sxs-lookup"><span data-stu-id="b89ec-104">Align and stretch a control</span></span>

1. <span data-ttu-id="b89ec-105">在 Visual Studio 中，拖动<xref:System.Windows.Forms.TableLayoutPanel>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="b89ec-105">In Visual Studio, drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="b89ec-106">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到的左上角单元格<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="b89ec-106">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="b89ec-107"><xref:System.Windows.Forms.Button>控件居中单元格中。</span><span class="sxs-lookup"><span data-stu-id="b89ec-107">The <xref:System.Windows.Forms.Button> control is centered in the cell.</span></span>

3. <span data-ttu-id="b89ec-108">设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性设置为`Left,Right`。</span><span class="sxs-lookup"><span data-stu-id="b89ec-108">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left,Right`.</span></span> <span data-ttu-id="b89ec-109"><xref:System.Windows.Forms.Button>控件将拉伸到匹配的单元格的宽度。</span><span class="sxs-lookup"><span data-stu-id="b89ec-109">The <xref:System.Windows.Forms.Button> control stretches to match the width of the cell.</span></span>

4. <span data-ttu-id="b89ec-110">设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性设置为`Top,Bottom`。</span><span class="sxs-lookup"><span data-stu-id="b89ec-110">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top,Bottom`.</span></span> <span data-ttu-id="b89ec-111"><xref:System.Windows.Forms.Button>控件将拉伸到匹配的单元格的高度。</span><span class="sxs-lookup"><span data-stu-id="b89ec-111">The <xref:System.Windows.Forms.Button> control stretches to match the height of the cell.</span></span>

5. <span data-ttu-id="b89ec-112">设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Dock%2A>属性设置为<xref:System.Windows.Forms.DockStyle.Fill>。</span><span class="sxs-lookup"><span data-stu-id="b89ec-112">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="b89ec-113"><xref:System.Windows.Forms.Button>控件扩展以填充单元格。</span><span class="sxs-lookup"><span data-stu-id="b89ec-113">The <xref:System.Windows.Forms.Button> control expands to fill the cell.</span></span>

6. <span data-ttu-id="b89ec-114">设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Dock%2A>属性设置为<xref:System.Windows.Forms.DockStyle.None>。</span><span class="sxs-lookup"><span data-stu-id="b89ec-114">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.None>.</span></span> <span data-ttu-id="b89ec-115"><xref:System.Windows.Forms.Button>控件返回到其原始大小，并将移动到单元格的左上角。</span><span class="sxs-lookup"><span data-stu-id="b89ec-115">The <xref:System.Windows.Forms.Button> control returns to its original size and moves to the upper-left corner of the cell.</span></span> <span data-ttu-id="b89ec-116">**Windows 窗体设计器**已设置<xref:System.Windows.Forms.Control.Anchor%2A>属性设置为`Top, Left`。</span><span class="sxs-lookup"><span data-stu-id="b89ec-116">The **Windows Forms Designer** has set the <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span>

7. <span data-ttu-id="b89ec-117">设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性设置为`Bottom,Right`。</span><span class="sxs-lookup"><span data-stu-id="b89ec-117">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Bottom,Right`.</span></span> <span data-ttu-id="b89ec-118"><xref:System.Windows.Forms.Button>控件移动到右下角的单元格。</span><span class="sxs-lookup"><span data-stu-id="b89ec-118">The <xref:System.Windows.Forms.Button> control moves to the lower-right corner of the cell.</span></span>

8. <span data-ttu-id="b89ec-119">设置的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性设置为<xref:System.Windows.Forms.AnchorStyles.None>。</span><span class="sxs-lookup"><span data-stu-id="b89ec-119">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.None>.</span></span> <span data-ttu-id="b89ec-120"><xref:System.Windows.Forms.Button>控件移动到单元格的中心。</span><span class="sxs-lookup"><span data-stu-id="b89ec-120">The <xref:System.Windows.Forms.Button> control moves to the center of the cell.</span></span>

## <a name="see-also"></a><span data-ttu-id="b89ec-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="b89ec-121">See also</span></span>

- [<span data-ttu-id="b89ec-122">TableLayoutPanel 控件</span><span class="sxs-lookup"><span data-stu-id="b89ec-122">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
