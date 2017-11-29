---
title: "如何：用 DataGrid 控件实现验证"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], validation
- validation [WPF], DataGrid
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8c611919b5702877db34e9a02e367312678a1b27
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a><span data-ttu-id="667f2-102">如何：用 DataGrid 控件实现验证</span><span class="sxs-lookup"><span data-stu-id="667f2-102">How to: Implement Validation with the DataGrid Control</span></span>
<span data-ttu-id="667f2-103"><xref:System.Windows.Controls.DataGrid>控制，你可以执行的单元格和行级别的验证。</span><span class="sxs-lookup"><span data-stu-id="667f2-103">The <xref:System.Windows.Controls.DataGrid> control enables you to perform validation at both the cell and row level.</span></span> <span data-ttu-id="667f2-104">与单元格级别验证时用户更新的值验证绑定的数据对象的各个属性。</span><span class="sxs-lookup"><span data-stu-id="667f2-104">With cell-level validation, you validate individual properties of a bound data object when a user updates a value.</span></span> <span data-ttu-id="667f2-105">与行级别验证用户提交更改的行时验证整个数据对象。</span><span class="sxs-lookup"><span data-stu-id="667f2-105">With row-level validation, you validate entire data objects when a user commits changes to a row.</span></span> <span data-ttu-id="667f2-106">也可以为验证错误，提供自定义的可视反馈，或使用默认的视觉反馈，<xref:System.Windows.Controls.DataGrid>控件提供。</span><span class="sxs-lookup"><span data-stu-id="667f2-106">You can also provide customized visual feedback for validation errors, or use the default visual feedback that the <xref:System.Windows.Controls.DataGrid> control provides.</span></span>  
  
 <span data-ttu-id="667f2-107">下面的过程介绍如何验证将规则应用到<xref:System.Windows.Controls.DataGrid>绑定和自定义的可视反馈。</span><span class="sxs-lookup"><span data-stu-id="667f2-107">The following procedures describe how to apply validation rules to <xref:System.Windows.Controls.DataGrid> bindings and customize the visual feedback.</span></span>  
  
### <a name="to-validate-individual-cell-values"></a><span data-ttu-id="667f2-108">若要验证各个单元格的值</span><span class="sxs-lookup"><span data-stu-id="667f2-108">To validate individual cell values</span></span>  
  
-   <span data-ttu-id="667f2-109">用于列绑定上指定一个或多个验证规则。</span><span class="sxs-lookup"><span data-stu-id="667f2-109">Specify one or more validation rules on the binding used with a column.</span></span> <span data-ttu-id="667f2-110">这是类似于验证简单控件中的数据中所述[数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="667f2-110">This is similar to validating data in simple controls, as described in [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
     <span data-ttu-id="667f2-111">下面的示例演示<xref:System.Windows.Controls.DataGrid>其中包含四列绑定到不同的业务对象的属性的控件。</span><span class="sxs-lookup"><span data-stu-id="667f2-111">The following example shows a <xref:System.Windows.Controls.DataGrid> control with four columns bound to different properties of a business object.</span></span> <span data-ttu-id="667f2-112">三个列指定<xref:System.Windows.Controls.ExceptionValidationRule>通过设置<xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="667f2-112">Three of the columns specify the <xref:System.Windows.Controls.ExceptionValidationRule> by setting the <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> property to `true`.</span></span>  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     <span data-ttu-id="667f2-113">当用户输入无效值 （如非整数课程 ID 列中） 时，围绕单元格将出现一个红色边框。</span><span class="sxs-lookup"><span data-stu-id="667f2-113">When a user enters an invalid value (such as a non-integer in the Course ID column), a red border appears around the cell.</span></span> <span data-ttu-id="667f2-114">你可以更改此默认验证反馈以下过程中所述。</span><span class="sxs-lookup"><span data-stu-id="667f2-114">You can change this default validation feedback as described in the following procedure.</span></span>  
  
### <a name="to-customize-cell-validation-feedback"></a><span data-ttu-id="667f2-115">若要自定义单元格验证反馈</span><span class="sxs-lookup"><span data-stu-id="667f2-115">To customize cell validation feedback</span></span>  
  
-   <span data-ttu-id="667f2-116">设置列的<xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A>为样式属性适用于列的编辑控件。</span><span class="sxs-lookup"><span data-stu-id="667f2-116">Set the column's <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> property to a style appropriate for the column's editing control.</span></span> <span data-ttu-id="667f2-117">在运行时创建编辑控件，因为不能使用<xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType>附加就像处理简单控件的属性。</span><span class="sxs-lookup"><span data-stu-id="667f2-117">Because the editing controls are created at run time, you cannot use the <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> attached property like you would with simple controls.</span></span>  
  
     <span data-ttu-id="667f2-118">下面的示例通过将通过使用验证规则的三个列共享的错误样式更新前面的示例。</span><span class="sxs-lookup"><span data-stu-id="667f2-118">The following example updates the previous example by adding an error style shared by the three columns with validation rules.</span></span> <span data-ttu-id="667f2-119">当用户输入值无效时的样式的单元格背景色更改以及添加工具提示。</span><span class="sxs-lookup"><span data-stu-id="667f2-119">When a user enters an invalid value, the style changes the cell background color and adds a ToolTip.</span></span> <span data-ttu-id="667f2-120">请注意，使用的触发器，以确定是否有验证错误。</span><span class="sxs-lookup"><span data-stu-id="667f2-120">Note the use of a trigger to determine whether there is a validation error.</span></span> <span data-ttu-id="667f2-121">这是必需的因为当前单元格没有专用的错误模板。</span><span class="sxs-lookup"><span data-stu-id="667f2-121">This is required because there is currently no dedicated error template for cells.</span></span>  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     <span data-ttu-id="667f2-122">你可以通过将实现更广泛的自定义<xref:System.Windows.Controls.DataGridColumn.CellStyle%2A>使用的列。</span><span class="sxs-lookup"><span data-stu-id="667f2-122">You can implement more extensive customization by replacing the <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> used by the column.</span></span>  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a><span data-ttu-id="667f2-123">若要验证的单个行中的多个值</span><span class="sxs-lookup"><span data-stu-id="667f2-123">To validate multiple values in a single row</span></span>  
  
1.  <span data-ttu-id="667f2-124">实现<xref:System.Windows.Controls.ValidationRule>检查多个属性的绑定的数据对象的子类。</span><span class="sxs-lookup"><span data-stu-id="667f2-124">Implement a <xref:System.Windows.Controls.ValidationRule> subclass that checks multiple properties of the bound data object.</span></span> <span data-ttu-id="667f2-125">在你<xref:System.Windows.Controls.ValidationRule.Validate%2A>方法实现中，强制转换`value`参数值以<xref:System.Windows.Data.BindingGroup>实例。</span><span class="sxs-lookup"><span data-stu-id="667f2-125">In your <xref:System.Windows.Controls.ValidationRule.Validate%2A> method implementation, cast the `value` parameter value to a <xref:System.Windows.Data.BindingGroup> instance.</span></span> <span data-ttu-id="667f2-126">然后，就可以访问数据对象，通过<xref:System.Windows.Data.BindingGroup.Items%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="667f2-126">You can then access the data object through the <xref:System.Windows.Data.BindingGroup.Items%2A> property.</span></span>  
  
     <span data-ttu-id="667f2-127">下面的示例演示此过程以验证是否`StartDate`属性值`Course`对象是早于其`EndDate`属性值。</span><span class="sxs-lookup"><span data-stu-id="667f2-127">The following example demonstrates this process to validate whether the `StartDate` property value for a `Course` object is earlier than its `EndDate` property value.</span></span>  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2.  <span data-ttu-id="667f2-128">向其添加验证规则<xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType>集合。</span><span class="sxs-lookup"><span data-stu-id="667f2-128">Add the validation rule to the <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> collection.</span></span> <span data-ttu-id="667f2-129"><xref:System.Windows.Controls.DataGrid.RowValidationRules%2A>属性提供直接访问权限<xref:System.Windows.Data.BindingGroup.ValidationRules%2A>属性<xref:System.Windows.Data.BindingGroup>组控件使用的所有绑定的实例。</span><span class="sxs-lookup"><span data-stu-id="667f2-129">The <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> property provides direct access to the <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> property of a <xref:System.Windows.Data.BindingGroup> instance that groups all the bindings used by the control.</span></span>  
  
     <span data-ttu-id="667f2-130">下面的示例设置<xref:System.Windows.Controls.DataGrid.RowValidationRules%2A>在 XAML 中的属性。</span><span class="sxs-lookup"><span data-stu-id="667f2-130">The following example sets the <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> property in XAML.</span></span> <span data-ttu-id="667f2-131"><xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>属性设置为<xref:System.Windows.Controls.ValidationStep.UpdatedValue>，以便仅在更新绑定的数据对象后出现的有效性。</span><span class="sxs-lookup"><span data-stu-id="667f2-131">The <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> property is set to <xref:System.Windows.Controls.ValidationStep.UpdatedValue> so that the validation occurs only after the bound data object is updated.</span></span>  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     <span data-ttu-id="667f2-132">当用户指定的结束日期早于开始日期时，行标题中将显示一个红色感叹号 （！）。</span><span class="sxs-lookup"><span data-stu-id="667f2-132">When a user specifies an end date that is earlier than the start date, a red exclamation mark (!) appears in the row header.</span></span> <span data-ttu-id="667f2-133">你可以更改此默认验证反馈以下过程中所述。</span><span class="sxs-lookup"><span data-stu-id="667f2-133">You can change this default validation feedback as described in the following procedure.</span></span>  
  
### <a name="to-customize-row-validation-feedback"></a><span data-ttu-id="667f2-134">若要自定义行验证反馈</span><span class="sxs-lookup"><span data-stu-id="667f2-134">To customize row validation feedback</span></span>  
  
-   <span data-ttu-id="667f2-135">设置 <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="667f2-135">Set the <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="667f2-136">此属性使您能够自定义为单个行验证反馈<xref:System.Windows.Controls.DataGrid>控件。</span><span class="sxs-lookup"><span data-stu-id="667f2-136">This property enables you to customize row validation feedback for individual <xref:System.Windows.Controls.DataGrid> controls.</span></span> <span data-ttu-id="667f2-137">此外可以通过使用隐式行样式设置影响多个控件<xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="667f2-137">You can also affect multiple controls by using an implicit row style to set the <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     <span data-ttu-id="667f2-138">下面的示例将默认行验证反馈替换更直观的指示器。</span><span class="sxs-lookup"><span data-stu-id="667f2-138">The following example replaces the default row validation feedback with a more visible indicator.</span></span> <span data-ttu-id="667f2-139">当用户输入值无效时，红色圆圈及白色感叹号显示行标题中。</span><span class="sxs-lookup"><span data-stu-id="667f2-139">When a user enters an invalid value, a red circle with a white exclamation mark appears in the row header.</span></span> <span data-ttu-id="667f2-140">行和单元格的验证错误发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="667f2-140">This occurs for both row and cell validation errors.</span></span> <span data-ttu-id="667f2-141">工具提示中显示相关联的错误消息。</span><span class="sxs-lookup"><span data-stu-id="667f2-141">The associated error message is displayed in a ToolTip.</span></span>  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a><span data-ttu-id="667f2-142">示例</span><span class="sxs-lookup"><span data-stu-id="667f2-142">Example</span></span>  
 <span data-ttu-id="667f2-143">下面的示例提供单元格和行验证的完整的演示。</span><span class="sxs-lookup"><span data-stu-id="667f2-143">The following example provides a complete demonstration for cell and row validation.</span></span> <span data-ttu-id="667f2-144">`Course`类提供用于实现的示例数据对象<xref:System.ComponentModel.IEditableObject>为支持事务。</span><span class="sxs-lookup"><span data-stu-id="667f2-144">The `Course` class provides a sample data object that implements <xref:System.ComponentModel.IEditableObject> to support transactions.</span></span> <span data-ttu-id="667f2-145"><xref:System.Windows.Controls.DataGrid>与控件交互<xref:System.ComponentModel.IEditableObject>以便用户可以通过按 ESC 还原更改。</span><span class="sxs-lookup"><span data-stu-id="667f2-145">The <xref:System.Windows.Controls.DataGrid> control interacts with <xref:System.ComponentModel.IEditableObject> to enable users to revert changes by pressing ESC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="667f2-146">如果使用的 Visual Basic 中，在 MainWindow.xaml 的第一行中，将`x:Class="DataGridValidation.MainWindow"`与`x:Class="MainWindow"`。</span><span class="sxs-lookup"><span data-stu-id="667f2-146">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="DataGridValidation.MainWindow"` with `x:Class="MainWindow"`.</span></span>  
  
 <span data-ttu-id="667f2-147">若要测试验证，请尝试以下方法：</span><span class="sxs-lookup"><span data-stu-id="667f2-147">To test the validation, try the following:</span></span>  
  
-   <span data-ttu-id="667f2-148">在过程 ID 列中，输入一个非整数值。</span><span class="sxs-lookup"><span data-stu-id="667f2-148">In the Course ID column, enter a non-integer value.</span></span>  
  
-   <span data-ttu-id="667f2-149">在结束日期列中，输入日期早于开始日期。</span><span class="sxs-lookup"><span data-stu-id="667f2-149">In the End Date column, enter a date that is earlier than the Start Date.</span></span>  
  
-   <span data-ttu-id="667f2-150">删除课程 ID、 开始日期或结束日期中的值。</span><span class="sxs-lookup"><span data-stu-id="667f2-150">Delete the value in Course ID, Start Date, or End Date.</span></span>  
  
-   <span data-ttu-id="667f2-151">若要撤消无效的单元格值，将光标置于返回单元格中，然后按 ESC 键。</span><span class="sxs-lookup"><span data-stu-id="667f2-151">To undo an invalid cell value, put the cursor back in the cell and press the ESC key.</span></span>  
  
-   <span data-ttu-id="667f2-152">若要撤消整个行的更改，当前单元格处于编辑模式时，请按 ESC 键两次。</span><span class="sxs-lookup"><span data-stu-id="667f2-152">To undo changes for an entire row when the current cell is in edit mode, press the ESC key twice.</span></span>  
  
-   <span data-ttu-id="667f2-153">出现验证错误时，将鼠标指针移到行标题，以查看关联的错误消息中的指示器。</span><span class="sxs-lookup"><span data-stu-id="667f2-153">When a validation error occurs, move your mouse pointer over the indicator in the row header to see the associated error message.</span></span>  
  
 [!code-csharp[DataGrid_Validation#FullCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="667f2-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="667f2-154">See Also</span></span>  
 <xref:System.Windows.Controls.DataGrid>  
 [<span data-ttu-id="667f2-155">数据网格</span><span class="sxs-lookup"><span data-stu-id="667f2-155">DataGrid</span></span>](../../../../docs/framework/wpf/controls/datagrid.md)  
 [<span data-ttu-id="667f2-156">数据绑定</span><span class="sxs-lookup"><span data-stu-id="667f2-156">Data Binding</span></span>](../../../../docs/framework/wpf/data/data-binding-wpf.md)  
 [<span data-ttu-id="667f2-157">实现绑定验证</span><span class="sxs-lookup"><span data-stu-id="667f2-157">Implement Binding Validation</span></span>](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [<span data-ttu-id="667f2-158">在自定义对象上实现验证逻辑</span><span class="sxs-lookup"><span data-stu-id="667f2-158">Implement Validation Logic on Custom Objects</span></span>](../../../../docs/framework/wpf/data/how-to-implement-validation-logic-on-custom-objects.md)
