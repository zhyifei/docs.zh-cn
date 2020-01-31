---
title: 更改 DataGridView 控件中的边框和网格线样式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gridlines [Windows Forms], changing styles
- data grids [Windows Forms], changing gridline styles
- DataGridView control [Windows Forms], border styles
- data grids [Windows Forms], changing border styles
- DataGridView control [Windows Forms], gridline styles
ms.assetid: 2f413c7a-4025-4171-8e3a-66ef908ea583
ms.openlocfilehash: 918102a87ee29a3d3b78d6e6eedce57237135a51
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744702"
---
# <a name="how-to-change-the-border-and-gridline-styles-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d9263-102">방법: Windows Forms DataGridView 컨트롤의 테두리 및 모눈선 스타일 변경</span><span class="sxs-lookup"><span data-stu-id="d9263-102">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d9263-103">利用 <xref:System.Windows.Forms.DataGridView> 控件，你可以自定义控件的边框和网格线的外观，以改善用户体验。</span><span class="sxs-lookup"><span data-stu-id="d9263-103">With the <xref:System.Windows.Forms.DataGridView> control, you can customize the appearance of the control's border and gridlines to improve the user experience.</span></span> <span data-ttu-id="d9263-104">除了控件中单元格的边框样式外，还可以修改网格线颜色和控件边框样式。</span><span class="sxs-lookup"><span data-stu-id="d9263-104">You can modify the gridline color and the control border style in addition to the border styles for the cells within the control.</span></span> <span data-ttu-id="d9263-105">对于普通单元格、行标题单元格和列标题单元，还可以应用不同的单元格边框样式。</span><span class="sxs-lookup"><span data-stu-id="d9263-105">You can also apply different cell border styles for ordinary cells, row header cells, and column header cells.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d9263-106">网格线颜色仅与 <xref:System.Windows.Forms.DataGridViewCellBorderStyle> 枚举的 <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>、<xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>和 <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> 值以及 <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> 枚举的 <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> 值一起使用。</span><span class="sxs-lookup"><span data-stu-id="d9263-106">The gridline color is used only with the <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, and <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> values of the <xref:System.Windows.Forms.DataGridViewCellBorderStyle> enumeration and the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> value of the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> enumeration.</span></span> <span data-ttu-id="d9263-107">这些枚举的其他值使用操作系统指定的颜色。</span><span class="sxs-lookup"><span data-stu-id="d9263-107">The other values of these enumerations use colors specified by the operating system.</span></span> <span data-ttu-id="d9263-108">此外，当在 Windows XP 和 Windows Server 2003 家族上通过 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 方法启用视觉样式时，不使用 <xref:System.Windows.Forms.DataGridView.GridColor%2A> 属性值。</span><span class="sxs-lookup"><span data-stu-id="d9263-108">Additionally, when visual styles are enabled on Windows XP and the Windows Server 2003 family through the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method, the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property value is not used.</span></span>  
  
### <a name="to-change-the-gridline-color-programmatically"></a><span data-ttu-id="d9263-109">以编程方式更改网格线颜色</span><span class="sxs-lookup"><span data-stu-id="d9263-109">To change the gridline color programmatically</span></span>  
  
- <span data-ttu-id="d9263-110"><xref:System.Windows.Forms.DataGridView.GridColor%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9263-110">Set the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### <a name="to-change-the-border-style-of-the-entire-datagridview-control-programmatically"></a><span data-ttu-id="d9263-111">以编程方式更改整个 DataGridView 控件的边框样式</span><span class="sxs-lookup"><span data-stu-id="d9263-111">To change the border style of the entire DataGridView control programmatically</span></span>  
  
- <span data-ttu-id="d9263-112"><xref:System.Windows.Forms.DataGridView.BorderStyle%2A> 속성을 <xref:System.Windows.Forms.BorderStyle> 열거형 값 중 하나로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9263-112">Set the <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> property to one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### <a name="to-change-the-border-styles-for-datagridview-cells-programmatically"></a><span data-ttu-id="d9263-113">以编程方式更改 DataGridView 单元格的边框样式</span><span class="sxs-lookup"><span data-stu-id="d9263-113">To change the border styles for DataGridView cells programmatically</span></span>  
  
- <span data-ttu-id="d9263-114">设置 <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>、<xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>和 <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="d9263-114">Set the <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, and <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## <a name="example"></a><span data-ttu-id="d9263-115">示例</span><span class="sxs-lookup"><span data-stu-id="d9263-115">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d9263-116">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="d9263-116">Compiling the Code</span></span>  
 <span data-ttu-id="d9263-117">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d9263-117">This example requires:</span></span>  
  
- <span data-ttu-id="d9263-118">`dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="d9263-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="d9263-119"><xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> 및 <xref:System.Drawing?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="d9263-119">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9263-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9263-120">See also</span></span>

- <xref:System.Windows.Forms.BorderStyle>
- <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellBorderStyle>
- <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>
- [<span data-ttu-id="d9263-121">Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="d9263-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
