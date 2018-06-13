---
title: 如何：在数据绑定 Windows 窗体 DataGridView 控件中自动生成列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], autogenerating columns
- columns [Windows Forms], autogenerating
- DataGridView control [Windows Forms], data-bound columns
ms.assetid: 699f6f9e-6aa5-4811-902b-6a2c57dec7d6
ms.openlocfilehash: 97fbc2c21f618b9fa0451c17ebf87579f51a3f0d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524382"
---
# <a name="how-to-autogenerate-columns-in-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="37a32-102">如何：在数据绑定 Windows 窗体 DataGridView 控件中自动生成列</span><span class="sxs-lookup"><span data-stu-id="37a32-102">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="37a32-103">下面的代码示例演示如何显示列中的绑定的数据源从<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="37a32-103">The following code example demonstrates how to display columns from a bound data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="37a32-104">当<xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A>属性值是`true`（默认值）、<xref:System.Windows.Forms.DataGridViewColumn>为每个列中的数据源表创建。</span><span class="sxs-lookup"><span data-stu-id="37a32-104">When the <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> property value is `true` (the default), a <xref:System.Windows.Forms.DataGridViewColumn> is created for each column in the data source table.</span></span>  
  
 <span data-ttu-id="37a32-105">如果<xref:System.Windows.Forms.DataGridView>控件已包含列，设置时<xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>属性、 现有绑定列是与数据源中的列时，会保留没有匹配项。</span><span class="sxs-lookup"><span data-stu-id="37a32-105">If the <xref:System.Windows.Forms.DataGridView> control already has columns when you set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property, the existing bound columns are compared to the columns in the data source and preserved whenever there is a match.</span></span> <span data-ttu-id="37a32-106">始终保留未绑定的列。</span><span class="sxs-lookup"><span data-stu-id="37a32-106">Unbound columns are always preserved.</span></span> <span data-ttu-id="37a32-107">没有数据源中的匹配的绑定的列被删除。</span><span class="sxs-lookup"><span data-stu-id="37a32-107">Bound columns for which there is no match in the data source are removed.</span></span> <span data-ttu-id="37a32-108">在控件中的没有匹配数据源中的列生成新<xref:System.Windows.Forms.DataGridViewColumn>对象，添加到末尾<xref:System.Windows.Forms.DataGridView.Columns%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="37a32-108">Columns in the data source for which there is no match in the control generate new <xref:System.Windows.Forms.DataGridViewColumn> objects, which are added to the end of the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37a32-109">示例</span><span class="sxs-lookup"><span data-stu-id="37a32-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#020](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#020)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#020](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#020)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="37a32-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="37a32-110">Compiling the Code</span></span>  
 <span data-ttu-id="37a32-111">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="37a32-111">This example requires:</span></span>  
  
-   <span data-ttu-id="37a32-112">名为 `customersDataGridView` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="37a32-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView`.</span></span>  
  
-   <span data-ttu-id="37a32-113">A<xref:System.Data.DataSet>对象名为`customersDataSet`具有名为的表`Customers`。</span><span class="sxs-lookup"><span data-stu-id="37a32-113">A <xref:System.Data.DataSet> object named `customersDataSet` that has a table named `Customers`.</span></span>  
  
-   <span data-ttu-id="37a32-114">对 <xref:System?displayProperty=nameWithType>、<xref:System.Windows.Forms?displayProperty=nameWithType>、<xref:System.Data?displayProperty=nameWithType> 和 <xref:System.Xml?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="37a32-114">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37a32-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="37a32-115">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="37a32-116">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="37a32-116">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="37a32-117">如何：从 Windows 窗体 DataGridView 控件中删除自动生成的列</span><span class="sxs-lookup"><span data-stu-id="37a32-117">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/remove-autogenerated-columns-from-a-wf-datagridview-control.md)
