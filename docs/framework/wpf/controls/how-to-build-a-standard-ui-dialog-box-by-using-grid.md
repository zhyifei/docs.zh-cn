---
title: 如何：使用 Grid 生成标准 UI 对话框
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: 68c9653e616388374aad2ad33ac7dab68446241d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923421"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a><span data-ttu-id="b0a16-102">如何：使用 Grid 生成标准 UI 对话框</span><span class="sxs-lookup"><span data-stu-id="b0a16-102">How to: Build a Standard UI Dialog Box by Using Grid</span></span>
<span data-ttu-id="b0a16-103">此示例演示如何[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] <xref:System.Windows.Controls.Grid>使用元素创建标准对话框。</span><span class="sxs-lookup"><span data-stu-id="b0a16-103">This example shows how to create a standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialog box by using the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0a16-104">示例</span><span class="sxs-lookup"><span data-stu-id="b0a16-104">Example</span></span>  
 <span data-ttu-id="b0a16-105">下面的示例创建一个对话框, 如 Windows 操作系统中的 "**运行**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="b0a16-105">The following example creates a dialog box like the **Run** dialog box in the Windows operating system.</span></span>  
  
 <span data-ttu-id="b0a16-106">该示例创建一个<xref:System.Windows.Controls.Grid> , 并<xref:System.Windows.Controls.ColumnDefinition>使用和<xref:System.Windows.Controls.RowDefinition>类定义五个列和四行。</span><span class="sxs-lookup"><span data-stu-id="b0a16-106">The example creates a <xref:System.Windows.Controls.Grid> and uses the <xref:System.Windows.Controls.ColumnDefinition> and <xref:System.Windows.Controls.RowDefinition> classes to define five columns and four rows.</span></span>  
  
 <span data-ttu-id="b0a16-107">然后, 该示例添加并定位<xref:System.Windows.Controls.Image>, `RunIcon.png`以表示在对话框中找到的图像。</span><span class="sxs-lookup"><span data-stu-id="b0a16-107">The example then adds and positions an <xref:System.Windows.Controls.Image>, `RunIcon.png`, to represent the image that is found in the dialog box.</span></span> <span data-ttu-id="b0a16-108">图像位于<xref:System.Windows.Controls.Grid> (左上角) 的第一列和第一行。</span><span class="sxs-lookup"><span data-stu-id="b0a16-108">The image is placed in the first column and row of the <xref:System.Windows.Controls.Grid> (the upper-left corner).</span></span>  
  
 <span data-ttu-id="b0a16-109">接下来, 该示例向<xref:System.Windows.Controls.TextBlock>第一列添加一个元素, 该元素跨越第一行的其余列。</span><span class="sxs-lookup"><span data-stu-id="b0a16-109">Next, the example adds a <xref:System.Windows.Controls.TextBlock> element to the first column, which spans the remaining columns of the first row.</span></span> <span data-ttu-id="b0a16-110">它将另<xref:System.Windows.Controls.TextBlock>一个元素添加到第一列中的第二行, 以表示**打开**的文本框。</span><span class="sxs-lookup"><span data-stu-id="b0a16-110">It adds another <xref:System.Windows.Controls.TextBlock> element to the second row in the first column, to represent the **Open** text box.</span></span> <span data-ttu-id="b0a16-111">下面<xref:System.Windows.Controls.TextBlock>是一个, 它表示数据输入区域。</span><span class="sxs-lookup"><span data-stu-id="b0a16-111">A <xref:System.Windows.Controls.TextBlock> follows, which represents the data entry area.</span></span>  
  
 <span data-ttu-id="b0a16-112">最后, 此示例将三<xref:System.Windows.Controls.Button>个元素添加到最后一行, 该行表示 **"确定"、"** **取消**" 和 "**浏览**" 事件。</span><span class="sxs-lookup"><span data-stu-id="b0a16-112">Finally, the example adds three <xref:System.Windows.Controls.Button> elements to the final row, which represent the **OK**, **Cancel**, and **Browse** events.</span></span>  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b0a16-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0a16-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [<span data-ttu-id="b0a16-114">面板概述</span><span class="sxs-lookup"><span data-stu-id="b0a16-114">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="b0a16-115">帮助主题</span><span class="sxs-lookup"><span data-stu-id="b0a16-115">How-to Topics</span></span>](grid-how-to-topics.md)
