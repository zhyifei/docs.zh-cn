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
ms.openlocfilehash: 0dba318e6aa35761f4e9471fdb13b65644747b57
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966496"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d7c87-102">如何：使用行模板自定义 Windows 窗体 DataGridView 控件中的行</span><span class="sxs-lookup"><span data-stu-id="d7c87-102">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d7c87-103">控件将行模板用作通过数据绑定或在<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType>调用方法时未指定要使用的现有行的所有行的基础。 <xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="d7c87-103">The <xref:System.Windows.Forms.DataGridView> control uses the row template as a basis for all rows that it adds to the control either through data binding or when you call the <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> method without specifying an existing row to use.</span></span>  
  
 <span data-ttu-id="d7c87-104">行模板使你可以更好地控制行的外观和行为, 而<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>不是属性提供的。</span><span class="sxs-lookup"><span data-stu-id="d7c87-104">The row template gives you greater control over the appearance and behavior of rows than the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property provides.</span></span> <span data-ttu-id="d7c87-105">利用行模板, 可以设置任何<xref:System.Windows.Forms.DataGridViewRow>属性, 包括。 <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A></span><span class="sxs-lookup"><span data-stu-id="d7c87-105">With the row template, you can set any <xref:System.Windows.Forms.DataGridViewRow> properties, including <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span></span>  
  
 <span data-ttu-id="d7c87-106">在某些情况下, 您必须使用行模板来实现特定的效果。</span><span class="sxs-lookup"><span data-stu-id="d7c87-106">There are some situations where you must use the row template to achieve a particular effect.</span></span> <span data-ttu-id="d7c87-107">例如, 行高信息无法存储在中<xref:System.Windows.Forms.DataGridViewCellStyle>, 因此您必须使用行模板来更改所有行使用的默认高度。</span><span class="sxs-lookup"><span data-stu-id="d7c87-107">For example, row height information cannot be stored in a <xref:System.Windows.Forms.DataGridViewCellStyle>, so you must use a row template to change the default height used by all rows.</span></span> <span data-ttu-id="d7c87-108">当您创建自己的<xref:System.Windows.Forms.DataGridViewRow>派生自的类, 并且您希望在将新行添加到控件时使用您的自定义类型时, 行模板也很有用。</span><span class="sxs-lookup"><span data-stu-id="d7c87-108">The row template is also useful when you create your own classes derived from <xref:System.Windows.Forms.DataGridViewRow> and you want your custom type used when new rows are added to the control.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7c87-109">行模板仅在添加行时使用。</span><span class="sxs-lookup"><span data-stu-id="d7c87-109">The row template is used only when rows are added.</span></span> <span data-ttu-id="d7c87-110">不能通过更改行模板来更改现有行。</span><span class="sxs-lookup"><span data-stu-id="d7c87-110">You cannot change existing rows by changing the row template.</span></span>  
  
### <a name="to-use-the-row-template"></a><span data-ttu-id="d7c87-111">使用行模板</span><span class="sxs-lookup"><span data-stu-id="d7c87-111">To use the row template</span></span>  
  
- <span data-ttu-id="d7c87-112">设置从<xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>属性中检索的对象的属性。</span><span class="sxs-lookup"><span data-stu-id="d7c87-112">Set properties on the object retrieved from the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d7c87-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="d7c87-113">Compiling the Code</span></span>  
 <span data-ttu-id="d7c87-114">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="d7c87-114">This example requires:</span></span>  
  
- <span data-ttu-id="d7c87-115">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="d7c87-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="d7c87-116">对 <xref:System?displayProperty=nameWithType><xref:System.Drawing?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="d7c87-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7c87-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7c87-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d7c87-118">Windows 窗体 DataGridView 控件中的基本格式和样式设置</span><span class="sxs-lookup"><span data-stu-id="d7c87-118">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d7c87-119">Windows 窗体 DataGridView 控件中的单元格样式</span><span class="sxs-lookup"><span data-stu-id="d7c87-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
