---
title: 如何：使用 DataGrid 控件实现验证
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], validation
- validation [WPF], DataGrid
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
ms.openlocfilehash: 38b4c9cd7679f0d8da9b18fb5bd6bb729d33ed54
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646089"
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a><span data-ttu-id="8440a-102">如何：使用 DataGrid 控件实现验证</span><span class="sxs-lookup"><span data-stu-id="8440a-102">How to: Implement Validation with the DataGrid Control</span></span>
<span data-ttu-id="8440a-103">该<xref:System.Windows.Controls.DataGrid>控件使您能够在单元格和行级别执行验证。</span><span class="sxs-lookup"><span data-stu-id="8440a-103">The <xref:System.Windows.Controls.DataGrid> control enables you to perform validation at both the cell and row level.</span></span> <span data-ttu-id="8440a-104">使用单元格级验证，当用户更新值时，可以验证绑定数据对象的单个属性。</span><span class="sxs-lookup"><span data-stu-id="8440a-104">With cell-level validation, you validate individual properties of a bound data object when a user updates a value.</span></span> <span data-ttu-id="8440a-105">使用行级验证，当用户将更改提交到行时，可以验证整个数据对象。</span><span class="sxs-lookup"><span data-stu-id="8440a-105">With row-level validation, you validate entire data objects when a user commits changes to a row.</span></span> <span data-ttu-id="8440a-106">您还可以为验证错误提供自定义的可视反馈，或使用<xref:System.Windows.Controls.DataGrid>控件提供的默认视觉反馈。</span><span class="sxs-lookup"><span data-stu-id="8440a-106">You can also provide customized visual feedback for validation errors, or use the default visual feedback that the <xref:System.Windows.Controls.DataGrid> control provides.</span></span>  
  
 <span data-ttu-id="8440a-107">以下过程介绍如何将验证规则应用于<xref:System.Windows.Controls.DataGrid>绑定并自定义可视反馈。</span><span class="sxs-lookup"><span data-stu-id="8440a-107">The following procedures describe how to apply validation rules to <xref:System.Windows.Controls.DataGrid> bindings and customize the visual feedback.</span></span>  
  
### <a name="to-validate-individual-cell-values"></a><span data-ttu-id="8440a-108">验证单个单元格值</span><span class="sxs-lookup"><span data-stu-id="8440a-108">To validate individual cell values</span></span>  
  
- <span data-ttu-id="8440a-109">在列使用的绑定上指定一个或多个验证规则。</span><span class="sxs-lookup"><span data-stu-id="8440a-109">Specify one or more validation rules on the binding used with a column.</span></span> <span data-ttu-id="8440a-110">这类似于在简单控件中验证数据，如[数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="8440a-110">This is similar to validating data in simple controls, as described in [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>  
  
     <span data-ttu-id="8440a-111">下面的示例显示一个<xref:System.Windows.Controls.DataGrid>控件，该控件的四列绑定到业务对象的不同属性。</span><span class="sxs-lookup"><span data-stu-id="8440a-111">The following example shows a <xref:System.Windows.Controls.DataGrid> control with four columns bound to different properties of a business object.</span></span> <span data-ttu-id="8440a-112">三列<xref:System.Windows.Controls.ExceptionValidationRule>通过将<xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>属性设置为`true`指定 。</span><span class="sxs-lookup"><span data-stu-id="8440a-112">Three of the columns specify the <xref:System.Windows.Controls.ExceptionValidationRule> by setting the <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> property to `true`.</span></span>  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     <span data-ttu-id="8440a-113">当用户输入无效值（如课程 ID 列中的非整数）时，单元格周围会出现红色边框。</span><span class="sxs-lookup"><span data-stu-id="8440a-113">When a user enters an invalid value (such as a non-integer in the Course ID column), a red border appears around the cell.</span></span> <span data-ttu-id="8440a-114">您可以按照以下过程所述更改此默认验证反馈。</span><span class="sxs-lookup"><span data-stu-id="8440a-114">You can change this default validation feedback as described in the following procedure.</span></span>  
  
### <a name="to-customize-cell-validation-feedback"></a><span data-ttu-id="8440a-115">自定义单元格验证反馈</span><span class="sxs-lookup"><span data-stu-id="8440a-115">To customize cell validation feedback</span></span>  
  
- <span data-ttu-id="8440a-116">将列的属性<xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A>设置为适合列编辑控件的样式。</span><span class="sxs-lookup"><span data-stu-id="8440a-116">Set the column's <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> property to a style appropriate for the column's editing control.</span></span> <span data-ttu-id="8440a-117">由于编辑控件是在运行时创建的，因此不能像使用简单控件那样<xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType>使用附加属性。</span><span class="sxs-lookup"><span data-stu-id="8440a-117">Because the editing controls are created at run time, you cannot use the <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> attached property like you would with simple controls.</span></span>  
  
     <span data-ttu-id="8440a-118">下面的示例通过添加由三列共享的具有验证规则的错误样式来更新前面的示例。</span><span class="sxs-lookup"><span data-stu-id="8440a-118">The following example updates the previous example by adding an error style shared by the three columns with validation rules.</span></span> <span data-ttu-id="8440a-119">当用户输入无效值时，样式将更改单元格背景颜色并添加工具提示。</span><span class="sxs-lookup"><span data-stu-id="8440a-119">When a user enters an invalid value, the style changes the cell background color and adds a ToolTip.</span></span> <span data-ttu-id="8440a-120">请注意使用触发器来确定是否存在验证错误。</span><span class="sxs-lookup"><span data-stu-id="8440a-120">Note the use of a trigger to determine whether there is a validation error.</span></span> <span data-ttu-id="8440a-121">这是必需的，因为当前没有专用的单元格错误模板。</span><span class="sxs-lookup"><span data-stu-id="8440a-121">This is required because there is currently no dedicated error template for cells.</span></span>  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     <span data-ttu-id="8440a-122">您可以通过替换列使用来实现<xref:System.Windows.Controls.DataGridColumn.CellStyle%2A>更广泛的自定义。</span><span class="sxs-lookup"><span data-stu-id="8440a-122">You can implement more extensive customization by replacing the <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> used by the column.</span></span>  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a><span data-ttu-id="8440a-123">验证一行中的多个值</span><span class="sxs-lookup"><span data-stu-id="8440a-123">To validate multiple values in a single row</span></span>  
  
1. <span data-ttu-id="8440a-124">实现一<xref:System.Windows.Controls.ValidationRule>个子类，该子类检查绑定数据对象的多个属性。</span><span class="sxs-lookup"><span data-stu-id="8440a-124">Implement a <xref:System.Windows.Controls.ValidationRule> subclass that checks multiple properties of the bound data object.</span></span> <span data-ttu-id="8440a-125">在方法<xref:System.Windows.Controls.ValidationRule.Validate%2A>实现中，将`value`参数值转换为<xref:System.Windows.Data.BindingGroup>实例。</span><span class="sxs-lookup"><span data-stu-id="8440a-125">In your <xref:System.Windows.Controls.ValidationRule.Validate%2A> method implementation, cast the `value` parameter value to a <xref:System.Windows.Data.BindingGroup> instance.</span></span> <span data-ttu-id="8440a-126">然后，您可以通过<xref:System.Windows.Data.BindingGroup.Items%2A>属性访问数据对象。</span><span class="sxs-lookup"><span data-stu-id="8440a-126">You can then access the data object through the <xref:System.Windows.Data.BindingGroup.Items%2A> property.</span></span>  
  
     <span data-ttu-id="8440a-127">下面的示例演示了此过程，以验证`StartDate``Course`对象的属性值是否早于其`EndDate`属性值。</span><span class="sxs-lookup"><span data-stu-id="8440a-127">The following example demonstrates this process to validate whether the `StartDate` property value for a `Course` object is earlier than its `EndDate` property value.</span></span>  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2. <span data-ttu-id="8440a-128">将验证规则添加到<xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType>集合中。</span><span class="sxs-lookup"><span data-stu-id="8440a-128">Add the validation rule to the <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> collection.</span></span> <span data-ttu-id="8440a-129">该<xref:System.Windows.Controls.DataGrid.RowValidationRules%2A>属性提供对<xref:System.Windows.Data.BindingGroup.ValidationRules%2A><xref:System.Windows.Data.BindingGroup>实例属性的直接访问，该实例对控件使用的所有绑定进行分组。</span><span class="sxs-lookup"><span data-stu-id="8440a-129">The <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> property provides direct access to the <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> property of a <xref:System.Windows.Data.BindingGroup> instance that groups all the bindings used by the control.</span></span>  
  
     <span data-ttu-id="8440a-130">下面的示例在 XAML 中设置<xref:System.Windows.Controls.DataGrid.RowValidationRules%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="8440a-130">The following example sets the <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> property in XAML.</span></span> <span data-ttu-id="8440a-131">属性<xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>设置为<xref:System.Windows.Controls.ValidationStep.UpdatedValue>，以便验证仅在更新绑定数据对象后进行。</span><span class="sxs-lookup"><span data-stu-id="8440a-131">The <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> property is set to <xref:System.Windows.Controls.ValidationStep.UpdatedValue> so that the validation occurs only after the bound data object is updated.</span></span>  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     <span data-ttu-id="8440a-132">当用户指定早于开始日期的结束日期时，行标题中将显示一个红色感叹号 （！）。</span><span class="sxs-lookup"><span data-stu-id="8440a-132">When a user specifies an end date that is earlier than the start date, a red exclamation mark (!) appears in the row header.</span></span> <span data-ttu-id="8440a-133">您可以按照以下过程所述更改此默认验证反馈。</span><span class="sxs-lookup"><span data-stu-id="8440a-133">You can change this default validation feedback as described in the following procedure.</span></span>  
  
### <a name="to-customize-row-validation-feedback"></a><span data-ttu-id="8440a-134">自定义行验证反馈</span><span class="sxs-lookup"><span data-stu-id="8440a-134">To customize row validation feedback</span></span>  
  
- <span data-ttu-id="8440a-135">设置 <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="8440a-135">Set the <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="8440a-136">此属性使您能够为各个<xref:System.Windows.Controls.DataGrid>控件自定义行验证反馈。</span><span class="sxs-lookup"><span data-stu-id="8440a-136">This property enables you to customize row validation feedback for individual <xref:System.Windows.Controls.DataGrid> controls.</span></span> <span data-ttu-id="8440a-137">还可以通过使用隐式行样式来设置<xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType>属性来影响多个控件。</span><span class="sxs-lookup"><span data-stu-id="8440a-137">You can also affect multiple controls by using an implicit row style to set the <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     <span data-ttu-id="8440a-138">下面的示例将默认行验证反馈替换为更可见的指示器。</span><span class="sxs-lookup"><span data-stu-id="8440a-138">The following example replaces the default row validation feedback with a more visible indicator.</span></span> <span data-ttu-id="8440a-139">当用户输入无效值时，行标题中将显示一个带有白色感叹号的红色圆圈。</span><span class="sxs-lookup"><span data-stu-id="8440a-139">When a user enters an invalid value, a red circle with a white exclamation mark appears in the row header.</span></span> <span data-ttu-id="8440a-140">对于行和单元验证错误，都会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="8440a-140">This occurs for both row and cell validation errors.</span></span> <span data-ttu-id="8440a-141">关联的错误消息将显示在工具提示中。</span><span class="sxs-lookup"><span data-stu-id="8440a-141">The associated error message is displayed in a ToolTip.</span></span>  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a><span data-ttu-id="8440a-142">示例</span><span class="sxs-lookup"><span data-stu-id="8440a-142">Example</span></span>  
 <span data-ttu-id="8440a-143">下面的示例提供了单元格和行验证的完整演示。</span><span class="sxs-lookup"><span data-stu-id="8440a-143">The following example provides a complete demonstration for cell and row validation.</span></span> <span data-ttu-id="8440a-144">类`Course`提供一个示例数据对象，该<xref:System.ComponentModel.IEditableObject>对象实现以支持事务。</span><span class="sxs-lookup"><span data-stu-id="8440a-144">The `Course` class provides a sample data object that implements <xref:System.ComponentModel.IEditableObject> to support transactions.</span></span> <span data-ttu-id="8440a-145">该<xref:System.Windows.Controls.DataGrid>控件与<xref:System.ComponentModel.IEditableObject>这些控件交互，使用户能够通过按 ESC 还原更改。</span><span class="sxs-lookup"><span data-stu-id="8440a-145">The <xref:System.Windows.Controls.DataGrid> control interacts with <xref:System.ComponentModel.IEditableObject> to enable users to revert changes by pressing ESC.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8440a-146">如果使用 Visual Basic，则在 MainWindow.xaml 的第一行中`x:Class="DataGridValidation.MainWindow"`，`x:Class="MainWindow"`替换为 。</span><span class="sxs-lookup"><span data-stu-id="8440a-146">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="DataGridValidation.MainWindow"` with `x:Class="MainWindow"`.</span></span>  
  
 <span data-ttu-id="8440a-147">要测试验证，请尝试以下操作：</span><span class="sxs-lookup"><span data-stu-id="8440a-147">To test the validation, try the following:</span></span>  
  
- <span data-ttu-id="8440a-148">在"课程 ID"列中，输入非整数值。</span><span class="sxs-lookup"><span data-stu-id="8440a-148">In the Course ID column, enter a non-integer value.</span></span>  
  
- <span data-ttu-id="8440a-149">在"结束日期"列中，输入早于开始日期的日期。</span><span class="sxs-lookup"><span data-stu-id="8440a-149">In the End Date column, enter a date that is earlier than the Start Date.</span></span>  
  
- <span data-ttu-id="8440a-150">删除课程 ID、开始日期或结束日期中的值。</span><span class="sxs-lookup"><span data-stu-id="8440a-150">Delete the value in Course ID, Start Date, or End Date.</span></span>  
  
- <span data-ttu-id="8440a-151">要撤消无效的单元格值，请将光标放回单元格中，然后按 ESC 键。</span><span class="sxs-lookup"><span data-stu-id="8440a-151">To undo an invalid cell value, put the cursor back in the cell and press the ESC key.</span></span>  
  
- <span data-ttu-id="8440a-152">要在当前单元格处于编辑模式时撤消整个行的更改，请按 ESC 键两次。</span><span class="sxs-lookup"><span data-stu-id="8440a-152">To undo changes for an entire row when the current cell is in edit mode, press the ESC key twice.</span></span>  
  
- <span data-ttu-id="8440a-153">发生验证错误时，将鼠标指针移到行标题中的指示器上以查看关联的错误消息。</span><span class="sxs-lookup"><span data-stu-id="8440a-153">When a validation error occurs, move your mouse pointer over the indicator in the row header to see the associated error message.</span></span>  
  
 [!code-csharp[DataGrid_Validation#FullCode](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="8440a-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8440a-154">See also</span></span>

- <xref:System.Windows.Controls.DataGrid>
- [<span data-ttu-id="8440a-155">DataGrid</span><span class="sxs-lookup"><span data-stu-id="8440a-155">DataGrid</span></span>](datagrid.md)
- [<span data-ttu-id="8440a-156">数据绑定</span><span class="sxs-lookup"><span data-stu-id="8440a-156">Data Binding</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="8440a-157">实现绑定验证</span><span class="sxs-lookup"><span data-stu-id="8440a-157">Implement Binding Validation</span></span>](../data/how-to-implement-binding-validation.md)
- [<span data-ttu-id="8440a-158">在自定义对象上实现验证逻辑</span><span class="sxs-lookup"><span data-stu-id="8440a-158">Implement Validation Logic on Custom Objects</span></span>](../data/how-to-implement-validation-logic-on-custom-objects.md)
