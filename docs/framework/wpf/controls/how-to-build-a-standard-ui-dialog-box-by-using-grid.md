---
title: 如何：使用 Grid 来构建标准的 UI 对话框
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: d0b24e320c2a341b069e1c9c3e8b6d5e93076733
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551877"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a><span data-ttu-id="f7ffa-102">如何：使用 Grid 来构建标准的 UI 对话框</span><span class="sxs-lookup"><span data-stu-id="f7ffa-102">How to: Build a Standard UI Dialog Box by Using Grid</span></span>
<span data-ttu-id="f7ffa-103">此示例演示如何创建标准[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]对话框中，通过使用<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="f7ffa-103">This example shows how to create a standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialog box by using the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7ffa-104">示例</span><span class="sxs-lookup"><span data-stu-id="f7ffa-104">Example</span></span>  
 <span data-ttu-id="f7ffa-105">下面的示例创建如下所示的对话框**运行**中的对话框[!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]操作系统。</span><span class="sxs-lookup"><span data-stu-id="f7ffa-105">The following example creates a dialog box like the **Run** dialog box in the [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="f7ffa-106">该示例创建<xref:System.Windows.Controls.Grid>并使用<xref:System.Windows.Controls.ColumnDefinition>和<xref:System.Windows.Controls.RowDefinition>类定义五列和四个行。</span><span class="sxs-lookup"><span data-stu-id="f7ffa-106">The example creates a <xref:System.Windows.Controls.Grid> and uses the <xref:System.Windows.Controls.ColumnDefinition> and <xref:System.Windows.Controls.RowDefinition> classes to define five columns and four rows.</span></span>  
  
 <span data-ttu-id="f7ffa-107">然后该示例将添加定位<xref:System.Windows.Controls.Image>， `RunIcon.png`，用于表示在对话框中找到的映像。</span><span class="sxs-lookup"><span data-stu-id="f7ffa-107">The example then adds and positions an <xref:System.Windows.Controls.Image>, `RunIcon.png`, to represent the image that is found in the dialog box.</span></span> <span data-ttu-id="f7ffa-108">映像放置在第一列和行的<xref:System.Windows.Controls.Grid>（左上角）。</span><span class="sxs-lookup"><span data-stu-id="f7ffa-108">The image is placed in the first column and row of the <xref:System.Windows.Controls.Grid> (the upper-left corner).</span></span>  
  
 <span data-ttu-id="f7ffa-109">接下来，该示例将添加<xref:System.Windows.Controls.TextBlock>到第一个列跨越第一行的剩余列的元素。</span><span class="sxs-lookup"><span data-stu-id="f7ffa-109">Next, the example adds a <xref:System.Windows.Controls.TextBlock> element to the first column, which spans the remaining columns of the first row.</span></span> <span data-ttu-id="f7ffa-110">它将添加另一个<xref:System.Windows.Controls.TextBlock>元素来表示第一列中的第二个行**打开**文本框。</span><span class="sxs-lookup"><span data-stu-id="f7ffa-110">It adds another <xref:System.Windows.Controls.TextBlock> element to the second row in the first column, to represent the **Open** text box.</span></span> <span data-ttu-id="f7ffa-111">A<xref:System.Windows.Controls.TextBlock>如下所示，它表示在数据输入区域。</span><span class="sxs-lookup"><span data-stu-id="f7ffa-111">A <xref:System.Windows.Controls.TextBlock> follows, which represents the data entry area.</span></span>  
  
 <span data-ttu-id="f7ffa-112">最后，该示例将添加三个<xref:System.Windows.Controls.Button>元素到最后一行，后者表示**确定**，**取消**，和**浏览**事件。</span><span class="sxs-lookup"><span data-stu-id="f7ffa-112">Finally, the example adds three <xref:System.Windows.Controls.Button> elements to the final row, which represent the **OK**, **Cancel**, and **Browse** events.</span></span>  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f7ffa-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7ffa-113">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.GridUnitType>  
 [<span data-ttu-id="f7ffa-114">面板概述</span><span class="sxs-lookup"><span data-stu-id="f7ffa-114">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="f7ffa-115">帮助主题</span><span class="sxs-lookup"><span data-stu-id="f7ffa-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/grid-how-to-topics.md)
