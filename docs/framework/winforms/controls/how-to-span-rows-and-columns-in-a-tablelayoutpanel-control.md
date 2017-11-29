---
title: "如何：在 TableLayoutPanel 控件中跨行和跨列"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0380e63925dcbd27a7ee6262ddbfb2706455c2a9
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a><span data-ttu-id="14d73-102">如何：在 TableLayoutPanel 控件中跨行和跨列</span><span class="sxs-lookup"><span data-stu-id="14d73-102">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>
<span data-ttu-id="14d73-103">中的控件<xref:System.Windows.Forms.TableLayoutPanel>控件可以跨越相邻的行和列。</span><span class="sxs-lookup"><span data-stu-id="14d73-103">Controls in a <xref:System.Windows.Forms.TableLayoutPanel> control can span adjacent rows and columns.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14d73-104">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="14d73-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="14d73-105">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="14d73-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="14d73-106">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="14d73-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-span-columns-and-rows"></a><span data-ttu-id="14d73-107">跨列和行</span><span class="sxs-lookup"><span data-stu-id="14d73-107">To span columns and rows</span></span>  
  
1.  <span data-ttu-id="14d73-108">拖动<xref:System.Windows.Forms.TableLayoutPanel>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="14d73-108">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="14d73-109">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到的左上角单元格中<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="14d73-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
3.  <span data-ttu-id="14d73-110">设置<xref:System.Windows.Forms.Button>控件的**ColumnSpan**属性**2**。</span><span class="sxs-lookup"><span data-stu-id="14d73-110">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **2**.</span></span> <span data-ttu-id="14d73-111">请注意，<xref:System.Windows.Forms.Button>控件跨的第一个和第二个列。</span><span class="sxs-lookup"><span data-stu-id="14d73-111">Note that the <xref:System.Windows.Forms.Button> control spans the first and second columns.</span></span>  
  
4.  <span data-ttu-id="14d73-112">设置<xref:System.Windows.Forms.Button>控件的**RowSpan**属性**2**。</span><span class="sxs-lookup"><span data-stu-id="14d73-112">Set the <xref:System.Windows.Forms.Button> control's **RowSpan** property to **2**.</span></span> <span data-ttu-id="14d73-113">请注意，<xref:System.Windows.Forms.Button>控件跨的第一个和第二个行。</span><span class="sxs-lookup"><span data-stu-id="14d73-113">Note that the <xref:System.Windows.Forms.Button> control spans the first and second rows.</span></span>  
  
5.  <span data-ttu-id="14d73-114">设置<xref:System.Windows.Forms.Button>控件的**ColumnSpan**属性**1**。</span><span class="sxs-lookup"><span data-stu-id="14d73-114">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **1**.</span></span> <span data-ttu-id="14d73-115">请注意，<xref:System.Windows.Forms.Button>控制会移动到第一列和跨越的第一个和第二个行。</span><span class="sxs-lookup"><span data-stu-id="14d73-115">Note that the <xref:System.Windows.Forms.Button> control moves into the first column and spans the first and second rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14d73-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14d73-116">See Also</span></span>  
 [<span data-ttu-id="14d73-117">TableLayoutPanel 控件</span><span class="sxs-lookup"><span data-stu-id="14d73-117">TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
