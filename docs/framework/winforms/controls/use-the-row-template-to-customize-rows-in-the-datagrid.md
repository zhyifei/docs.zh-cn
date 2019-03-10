---
title: 如何：使用行模板自定义 Windows 窗体 DataGridView 控件中的行
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: 3cd1e9af32cb47f5d81abfc92423ea30e2e599cf
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707568"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="5b567-102">如何：使用行模板自定义 Windows 窗体 DataGridView 控件中的行</span><span class="sxs-lookup"><span data-stu-id="5b567-102">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="5b567-103"><xref:System.Windows.Forms.DataGridView>控件中使用行模板为基础，它将添加到该控件通过数据绑定或在调用时的所有行<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType>而无需指定要使用的现有行的方法。</span><span class="sxs-lookup"><span data-stu-id="5b567-103">The <xref:System.Windows.Forms.DataGridView> control uses the row template as a basis for all rows that it adds to the control either through data binding or when you call the <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> method without specifying an existing row to use.</span></span>  
  
 <span data-ttu-id="5b567-104">行模板向您提供更好地控制的外观和行为的行比<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>属性提供。</span><span class="sxs-lookup"><span data-stu-id="5b567-104">The row template gives you greater control over the appearance and behavior of rows than the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property provides.</span></span> <span data-ttu-id="5b567-105">使用行模板，可以设置任何<xref:System.Windows.Forms.DataGridViewRow>属性，包括<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>。</span><span class="sxs-lookup"><span data-stu-id="5b567-105">With the row template, you can set any <xref:System.Windows.Forms.DataGridViewRow> properties, including <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span></span>  
  
 <span data-ttu-id="5b567-106">有某些情况下，必须使用行模板来实现特定的效果。</span><span class="sxs-lookup"><span data-stu-id="5b567-106">There are some situations where you must use the row template to achieve a particular effect.</span></span> <span data-ttu-id="5b567-107">例如，不能行高度信息存储在<xref:System.Windows.Forms.DataGridViewCellStyle>，因此必须使用行模板来更改使用的所有行的默认高度。</span><span class="sxs-lookup"><span data-stu-id="5b567-107">For example, row height information cannot be stored in a <xref:System.Windows.Forms.DataGridViewCellStyle>, so you must use a row template to change the default height used by all rows.</span></span> <span data-ttu-id="5b567-108">行模板非常有用，当您创建您自己的类派生自<xref:System.Windows.Forms.DataGridViewRow>并且你想在新行添加到控件时所使用的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="5b567-108">The row template is also useful when you create your own classes derived from <xref:System.Windows.Forms.DataGridViewRow> and you want your custom type used when new rows are added to the control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b567-109">添加行时仅使用行模板。</span><span class="sxs-lookup"><span data-stu-id="5b567-109">The row template is used only when rows are added.</span></span> <span data-ttu-id="5b567-110">通过更改行模板，您不能更改现有行。</span><span class="sxs-lookup"><span data-stu-id="5b567-110">You cannot change existing rows by changing the row template.</span></span>  
  
### <a name="to-use-the-row-template"></a><span data-ttu-id="5b567-111">若要使用行模板</span><span class="sxs-lookup"><span data-stu-id="5b567-111">To use the row template</span></span>  
  
-   <span data-ttu-id="5b567-112">在从检索的对象上设置属性<xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="5b567-112">Set properties on the object retrieved from the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5b567-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="5b567-113">Compiling the Code</span></span>  
 <span data-ttu-id="5b567-114">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="5b567-114">This example requires:</span></span>  
  
-   <span data-ttu-id="5b567-115">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="5b567-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="5b567-116">对 <xref:System?displayProperty=nameWithType><xref:System.Drawing?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="5b567-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b567-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b567-117">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [<span data-ttu-id="5b567-118">Windows 窗体 DataGridView 控件中的基本格式和样式设置</span><span class="sxs-lookup"><span data-stu-id="5b567-118">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="5b567-119">Windows 窗体 DataGridView 控件中的单元格样式</span><span class="sxs-lookup"><span data-stu-id="5b567-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
