---
title: 如何：访问 Windows 窗体 DataGridViewComboBoxCell 下拉列表中的对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], accessing objects in combo box cells
- combo boxes [Windows Forms], in DataGridView control
- combo boxes [Windows Forms], accessing objects in DataGridViewComboBoxCell drop-down lists
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
ms.openlocfilehash: 2758841031be9ca9f0a5eb5e57165191d6870e87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529397"
---
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a><span data-ttu-id="cae61-102">如何：访问 Windows 窗体 DataGridViewComboBoxCell 下拉列表中的对象</span><span class="sxs-lookup"><span data-stu-id="cae61-102">How to: Access Objects in a Windows Forms DataGridViewComboBoxCell Drop-Down List</span></span>
<span data-ttu-id="cae61-103">如<xref:System.Windows.Forms.ComboBox>控件，<xref:System.Windows.Forms.DataGridViewComboBoxColumn>和<xref:System.Windows.Forms.DataGridViewComboBoxCell>类型使你能够将任意对象添加到他们的下拉列表。</span><span class="sxs-lookup"><span data-stu-id="cae61-103">Like the <xref:System.Windows.Forms.ComboBox> control, the <xref:System.Windows.Forms.DataGridViewComboBoxColumn> and <xref:System.Windows.Forms.DataGridViewComboBoxCell> types enable you to add arbitrary objects to their drop-down lists.</span></span> <span data-ttu-id="cae61-104">使用此功能，可以表示下拉列表中的复杂状态，而无需在一个单独的集合中存储相应的对象。</span><span class="sxs-lookup"><span data-stu-id="cae61-104">With this feature, you can represent complex states in a drop-down list without having to store corresponding objects in a separate collection.</span></span>  
  
 <span data-ttu-id="cae61-105">与不同<xref:System.Windows.Forms.ComboBox>控件，<xref:System.Windows.Forms.DataGridView>类型不具有<xref:System.Windows.Forms.ComboBox.SelectedItem%2A>用于检索当前所选的对象的属性。</span><span class="sxs-lookup"><span data-stu-id="cae61-105">Unlike the <xref:System.Windows.Forms.ComboBox> control, the <xref:System.Windows.Forms.DataGridView> types do not have a <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> property for retrieving the currently selected object.</span></span> <span data-ttu-id="cae61-106">相反，必须设置<xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType>或<xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType>到业务对象上的属性名称的属性。</span><span class="sxs-lookup"><span data-stu-id="cae61-106">Instead, you must set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> or <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> property to the name of a property on your business object.</span></span> <span data-ttu-id="cae61-107">当用户进行的选择时，业务对象的指定的属性设置的单元格<xref:System.Windows.Forms.DataGridViewCell.Value%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="cae61-107">When the user makes a selection, the indicated property of the business object sets the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property.</span></span>  
  
 <span data-ttu-id="cae61-108">若要检索单元格的值，通过业务对象`ValueMember`属性必须指示该属性返回对业务对象本身的引用。</span><span class="sxs-lookup"><span data-stu-id="cae61-108">To retrieve the business object through the cell value, the `ValueMember` property must indicate a property that returns a reference to the business object itself.</span></span> <span data-ttu-id="cae61-109">因此，如果业务对象的类型不是受你控制，必须添加此属性，通过扩展通过继承的类型。</span><span class="sxs-lookup"><span data-stu-id="cae61-109">Therefore, if the type of the business object is not under your control, you must add such a property by extending the type through inheritance.</span></span>  
  
 <span data-ttu-id="cae61-110">下面的过程演示如何使用填充业务对象下拉列表和检索对象到单元格<xref:System.Windows.Forms.DataGridViewCell.Value%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="cae61-110">The following procedures demonstrate how to populate a drop-down list with business objects and retrieve the objects through the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property.</span></span>  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a><span data-ttu-id="cae61-111">若要将业务对象添加到下拉列表</span><span class="sxs-lookup"><span data-stu-id="cae61-111">To add business objects to the drop-down list</span></span>  
  
1.  <span data-ttu-id="cae61-112">创建一个新<xref:System.Windows.Forms.DataGridViewComboBoxColumn>和填充其<xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="cae61-112">Create a new <xref:System.Windows.Forms.DataGridViewComboBoxColumn> and populate its <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> collection.</span></span> <span data-ttu-id="cae61-113">或者，可以将列设置<xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>到业务对象集合的属性。</span><span class="sxs-lookup"><span data-stu-id="cae61-113">Alternatively, you can set the column <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property to the collection of business objects.</span></span> <span data-ttu-id="cae61-114">在这种情况下，但是，你不能添加"未分配"下拉列表而无需在你的集合中创建相应的业务对象。</span><span class="sxs-lookup"><span data-stu-id="cae61-114">In that case, however, you cannot add "unassigned" to the drop-down list without creating a corresponding business object in your collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2.  <span data-ttu-id="cae61-115">设置 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> 和 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="cae61-115">Set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> and <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> properties.</span></span> <span data-ttu-id="cae61-116"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> 指示要在下拉列表中显示的业务对象的属性。</span><span class="sxs-lookup"><span data-stu-id="cae61-116"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> indicates the property of the business object to display in the drop-down list.</span></span> <span data-ttu-id="cae61-117"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> 指示返回到业务对象的引用的属性。</span><span class="sxs-lookup"><span data-stu-id="cae61-117"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> indicates the property that returns a reference to the business object.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3.  <span data-ttu-id="cae61-118">请确保你的业务对象类型包含一个属性，返回对当前实例的引用。</span><span class="sxs-lookup"><span data-stu-id="cae61-118">Make sure that your business object type contains a property that returns a reference to the current instance.</span></span> <span data-ttu-id="cae61-119">此属性必须具有值分配给名为<xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>上一步中。</span><span class="sxs-lookup"><span data-stu-id="cae61-119">This property must be named with the value assigned to <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> in the previous step.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a><span data-ttu-id="cae61-120">若要检索当前所选的业务对象</span><span class="sxs-lookup"><span data-stu-id="cae61-120">To retrieve the currently selected business object</span></span>  
  
-   <span data-ttu-id="cae61-121">获取单元格<xref:System.Windows.Forms.DataGridViewCell.Value%2A>属性并将其转换到业务对象类型。</span><span class="sxs-lookup"><span data-stu-id="cae61-121">Get the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property and cast it to the business object type.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a><span data-ttu-id="cae61-122">示例</span><span class="sxs-lookup"><span data-stu-id="cae61-122">Example</span></span>  
 <span data-ttu-id="cae61-123">完整的示例演示如何使用下拉列表中的业务对象。</span><span class="sxs-lookup"><span data-stu-id="cae61-123">The complete example demonstrates the use of business objects in a drop-down list.</span></span> <span data-ttu-id="cae61-124">在示例中，<xref:System.Windows.Forms.DataGridView>控件绑定到的集合`Task`对象。</span><span class="sxs-lookup"><span data-stu-id="cae61-124">In the example, a <xref:System.Windows.Forms.DataGridView> control is bound to a collection of `Task` objects.</span></span> <span data-ttu-id="cae61-125">每个`Task`对象具有`AssignedTo`属性，指示`Employee`对象当前分配给该任务。</span><span class="sxs-lookup"><span data-stu-id="cae61-125">Each `Task` object has an `AssignedTo` property that indicates the `Employee` object currently assigned to that task.</span></span> <span data-ttu-id="cae61-126">`Assigned To`列显示`Name`每个属性值分配员工或"未分配"如果`Task.AssignedTo`属性值是`null`。</span><span class="sxs-lookup"><span data-stu-id="cae61-126">The `Assigned To` column displays the `Name` property value for each assigned employee, or "unassigned" if the `Task.AssignedTo` property value is `null`.</span></span>  
  
 <span data-ttu-id="cae61-127">若要查看此示例的行为，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cae61-127">To view the behavior of this example, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="cae61-128">更改分配给在`Assigned To`通过从下拉列表中选择不同的值或按 CTRL + 0，在组合框单元格的列。</span><span class="sxs-lookup"><span data-stu-id="cae61-128">Change assignments in the `Assigned To` column by selecting different values from the drop-down lists or pressing CTRL+0 in a combo-box cell.</span></span>  
  
2.  <span data-ttu-id="cae61-129">单击`Generate Report`以显示当前的分配。</span><span class="sxs-lookup"><span data-stu-id="cae61-129">Click `Generate Report` to display the current assignments.</span></span> <span data-ttu-id="cae61-130">此示例，演示中的更改`Assigned To`列自动更新`tasks`集合。</span><span class="sxs-lookup"><span data-stu-id="cae61-130">This demonstrates that a change in the `Assigned To` column automatically updates the `tasks` collection.</span></span>  
  
3.  <span data-ttu-id="cae61-131">单击`Request Status`按钮以调用`RequestStatus`当前方法`Employee`该行的对象。</span><span class="sxs-lookup"><span data-stu-id="cae61-131">Click a `Request Status` button to call the `RequestStatus` method of the current `Employee` object for that row.</span></span> <span data-ttu-id="cae61-132">此示例演示已成功检索所选的对象。</span><span class="sxs-lookup"><span data-stu-id="cae61-132">This demonstrates that the selected object has been successfully retrieved.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cae61-133">编译代码</span><span class="sxs-lookup"><span data-stu-id="cae61-133">Compiling the Code</span></span>  
 <span data-ttu-id="cae61-134">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="cae61-134">This example requires:</span></span>  
  
-   <span data-ttu-id="cae61-135">对 System 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="cae61-135">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cae61-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="cae61-136">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.DataSource%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell.Value%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ComboBox>  
 [<span data-ttu-id="cae61-137">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="cae61-137">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
