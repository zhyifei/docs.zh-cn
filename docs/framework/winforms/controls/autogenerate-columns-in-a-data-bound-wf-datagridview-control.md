---
title: 如何：数据绑定 Windows 窗体 DataGridView 控件中自动生成列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], autogenerating columns
- columns [Windows Forms], autogenerating
- DataGridView control [Windows Forms], data-bound columns
ms.assetid: 699f6f9e-6aa5-4811-902b-6a2c57dec7d6
ms.openlocfilehash: 1968968461edb475be4cd30261a66b53cd7f0e94
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554005"
---
# <a name="how-to-autogenerate-columns-in-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="cd71f-102">如何：数据绑定 Windows 窗体 DataGridView 控件中自动生成列</span><span class="sxs-lookup"><span data-stu-id="cd71f-102">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="cd71f-103">下面的代码示例演示如何显示来自绑定的数据源中的列<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="cd71f-103">The following code example demonstrates how to display columns from a bound data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="cd71f-104">当<xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A>属性值是`true`（默认值），<xref:System.Windows.Forms.DataGridViewColumn>为数据源表中的每个列创建。</span><span class="sxs-lookup"><span data-stu-id="cd71f-104">When the <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> property value is `true` (the default), a <xref:System.Windows.Forms.DataGridViewColumn> is created for each column in the data source table.</span></span>  
  
 <span data-ttu-id="cd71f-105">如果<xref:System.Windows.Forms.DataGridView>控件已有的列设置时<xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>属性中，现有绑定到数据源中的列比较和匹配项时保留列。</span><span class="sxs-lookup"><span data-stu-id="cd71f-105">If the <xref:System.Windows.Forms.DataGridView> control already has columns when you set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property, the existing bound columns are compared to the columns in the data source and preserved whenever there is a match.</span></span> <span data-ttu-id="cd71f-106">始终保留未绑定的列。</span><span class="sxs-lookup"><span data-stu-id="cd71f-106">Unbound columns are always preserved.</span></span> <span data-ttu-id="cd71f-107">删除绑定的列没有数据源中的没有匹配项。</span><span class="sxs-lookup"><span data-stu-id="cd71f-107">Bound columns for which there is no match in the data source are removed.</span></span> <span data-ttu-id="cd71f-108">在控件中的没有匹配项的数据源中的列生成新<xref:System.Windows.Forms.DataGridViewColumn>对象添加到末尾<xref:System.Windows.Forms.DataGridView.Columns%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="cd71f-108">Columns in the data source for which there is no match in the control generate new <xref:System.Windows.Forms.DataGridViewColumn> objects, which are added to the end of the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd71f-109">示例</span><span class="sxs-lookup"><span data-stu-id="cd71f-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#020](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#020)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#020](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#020)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cd71f-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="cd71f-110">Compiling the Code</span></span>  
 <span data-ttu-id="cd71f-111">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="cd71f-111">This example requires:</span></span>  
  
-   <span data-ttu-id="cd71f-112">名为 `customersDataGridView` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="cd71f-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView`.</span></span>  
  
-   <span data-ttu-id="cd71f-113">一个<xref:System.Data.DataSet>名为对象`customersDataSet`具有一个名为表`Customers`。</span><span class="sxs-lookup"><span data-stu-id="cd71f-113">A <xref:System.Data.DataSet> object named `customersDataSet` that has a table named `Customers`.</span></span>  
  
-   <span data-ttu-id="cd71f-114">对 <xref:System?displayProperty=nameWithType>、<xref:System.Windows.Forms?displayProperty=nameWithType>、<xref:System.Data?displayProperty=nameWithType> 和 <xref:System.Xml?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="cd71f-114">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd71f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd71f-115">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="cd71f-116">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="cd71f-116">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="cd71f-117">如何：从 Windows 窗体 DataGridView 控件中删除自动生成的列</span><span class="sxs-lookup"><span data-stu-id="cd71f-117">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/remove-autogenerated-columns-from-a-wf-datagridview-control.md)
