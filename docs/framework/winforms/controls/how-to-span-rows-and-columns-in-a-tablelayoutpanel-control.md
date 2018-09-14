---
title: 如何：在 TableLayoutPanel 控件中跨行和跨列
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: 5363e7a7def8d2593d3ac474deb9d3d7b77d3912
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2018
ms.locfileid: "45618998"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a><span data-ttu-id="b69b1-102">如何：在 TableLayoutPanel 控件中跨行和跨列</span><span class="sxs-lookup"><span data-stu-id="b69b1-102">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>
<span data-ttu-id="b69b1-103">中的控件<xref:System.Windows.Forms.TableLayoutPanel>控件可以跨越相邻的行和列。</span><span class="sxs-lookup"><span data-stu-id="b69b1-103">Controls in a <xref:System.Windows.Forms.TableLayoutPanel> control can span adjacent rows and columns.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b69b1-104">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="b69b1-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b69b1-105">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="b69b1-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b69b1-106">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="b69b1-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-span-columns-and-rows"></a><span data-ttu-id="b69b1-107">若要跨的列和行</span><span class="sxs-lookup"><span data-stu-id="b69b1-107">To span columns and rows</span></span>  
  
1.  <span data-ttu-id="b69b1-108">拖动<xref:System.Windows.Forms.TableLayoutPanel>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="b69b1-108">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="b69b1-109">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到的左上角单元格<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="b69b1-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
3.  <span data-ttu-id="b69b1-110">设置<xref:System.Windows.Forms.Button>控件的**ColumnSpan**属性设置为**2**。</span><span class="sxs-lookup"><span data-stu-id="b69b1-110">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **2**.</span></span> <span data-ttu-id="b69b1-111">请注意，<xref:System.Windows.Forms.Button>控件跨的第一个和第二个列。</span><span class="sxs-lookup"><span data-stu-id="b69b1-111">Note that the <xref:System.Windows.Forms.Button> control spans the first and second columns.</span></span>  
  
4.  <span data-ttu-id="b69b1-112">设置<xref:System.Windows.Forms.Button>控件的**RowSpan**属性设置为**2**。</span><span class="sxs-lookup"><span data-stu-id="b69b1-112">Set the <xref:System.Windows.Forms.Button> control's **RowSpan** property to **2**.</span></span> <span data-ttu-id="b69b1-113">请注意，<xref:System.Windows.Forms.Button>控件跨的第一个和第二个行。</span><span class="sxs-lookup"><span data-stu-id="b69b1-113">Note that the <xref:System.Windows.Forms.Button> control spans the first and second rows.</span></span>  
  
5.  <span data-ttu-id="b69b1-114">设置<xref:System.Windows.Forms.Button>控件的**ColumnSpan**属性设置为**1**。</span><span class="sxs-lookup"><span data-stu-id="b69b1-114">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **1**.</span></span> <span data-ttu-id="b69b1-115">请注意，<xref:System.Windows.Forms.Button>控件将移动到第一列并跨越的第一个和第二个行。</span><span class="sxs-lookup"><span data-stu-id="b69b1-115">Note that the <xref:System.Windows.Forms.Button> control moves into the first column and spans the first and second rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b69b1-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="b69b1-116">See Also</span></span>  
 [<span data-ttu-id="b69b1-117">TableLayoutPanel 控件</span><span class="sxs-lookup"><span data-stu-id="b69b1-117">TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
