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
ms.openlocfilehash: aead8cbd500262a4cba535fd023dd9701d50257a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086801"
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a><span data-ttu-id="bf9f9-102">如何：使用 DataGrid 控件实现验证</span><span class="sxs-lookup"><span data-stu-id="bf9f9-102">How to: Implement Validation with the DataGrid Control</span></span>
<span data-ttu-id="bf9f9-103"><xref:System.Windows.Controls.DataGrid>控件，可以在单元格和行级别执行验证。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-103">The <xref:System.Windows.Controls.DataGrid> control enables you to perform validation at both the cell and row level.</span></span> <span data-ttu-id="bf9f9-104">与单元格级别验证时用户更新的值验证绑定的数据对象的各个属性。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-104">With cell-level validation, you validate individual properties of a bound data object when a user updates a value.</span></span> <span data-ttu-id="bf9f9-105">使用行级验证时用户将更改提交到行验证整个数据对象。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-105">With row-level validation, you validate entire data objects when a user commits changes to a row.</span></span> <span data-ttu-id="bf9f9-106">此外可以为验证错误，提供自定义可视反馈，或使用默认的可视反馈的<xref:System.Windows.Controls.DataGrid>控件提供。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-106">You can also provide customized visual feedback for validation errors, or use the default visual feedback that the <xref:System.Windows.Controls.DataGrid> control provides.</span></span>  
  
 <span data-ttu-id="bf9f9-107">下面的过程介绍如何将应用到的验证规则<xref:System.Windows.Controls.DataGrid>绑定和自定义可视反馈。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-107">The following procedures describe how to apply validation rules to <xref:System.Windows.Controls.DataGrid> bindings and customize the visual feedback.</span></span>  
  
### <a name="to-validate-individual-cell-values"></a><span data-ttu-id="bf9f9-108">若要验证单个单元格的值</span><span class="sxs-lookup"><span data-stu-id="bf9f9-108">To validate individual cell values</span></span>  
  
-   <span data-ttu-id="bf9f9-109">指定的列使用绑定上的一个或多个验证规则。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-109">Specify one or more validation rules on the binding used with a column.</span></span> <span data-ttu-id="bf9f9-110">这是类似于验证简单控件中的数据，如中所述[数据绑定概述](../data/data-binding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-110">This is similar to validating data in simple controls, as described in [Data Binding Overview](../data/data-binding-overview.md).</span></span>  
  
     <span data-ttu-id="bf9f9-111">下面的示例演示<xref:System.Windows.Controls.DataGrid>具有四个列绑定到业务对象的不同属性的控件。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-111">The following example shows a <xref:System.Windows.Controls.DataGrid> control with four columns bound to different properties of a business object.</span></span> <span data-ttu-id="bf9f9-112">三个列指定<xref:System.Windows.Controls.ExceptionValidationRule>通过设置<xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-112">Three of the columns specify the <xref:System.Windows.Controls.ExceptionValidationRule> by setting the <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> property to `true`.</span></span>  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     <span data-ttu-id="bf9f9-113">当用户输入无效值 （如非整数中的课程 ID 列） 时，在单元格周围将出现一个红色边框。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-113">When a user enters an invalid value (such as a non-integer in the Course ID column), a red border appears around the cell.</span></span> <span data-ttu-id="bf9f9-114">您可以更改此默认验证反馈，如下面的过程中所述。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-114">You can change this default validation feedback as described in the following procedure.</span></span>  
  
### <a name="to-customize-cell-validation-feedback"></a><span data-ttu-id="bf9f9-115">若要自定义单元格验证反馈</span><span class="sxs-lookup"><span data-stu-id="bf9f9-115">To customize cell validation feedback</span></span>  
  
-   <span data-ttu-id="bf9f9-116">设置列的<xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A>属性设置为一种样式适用于列的编辑控件。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-116">Set the column's <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> property to a style appropriate for the column's editing control.</span></span> <span data-ttu-id="bf9f9-117">由于在运行时创建编辑控件，不能使用<xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType>附加属性，就像对简单控件。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-117">Because the editing controls are created at run time, you cannot use the <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> attached property like you would with simple controls.</span></span>  
  
     <span data-ttu-id="bf9f9-118">下面的示例通过添加由验证规则的三个列共享了错误样式更新前面的示例。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-118">The following example updates the previous example by adding an error style shared by the three columns with validation rules.</span></span> <span data-ttu-id="bf9f9-119">当用户输入的值无效时，样式更改单元格背景色，添加工具提示。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-119">When a user enters an invalid value, the style changes the cell background color and adds a ToolTip.</span></span> <span data-ttu-id="bf9f9-120">请注意，使用的触发器，以确定是否存在验证错误。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-120">Note the use of a trigger to determine whether there is a validation error.</span></span> <span data-ttu-id="bf9f9-121">这是必需的因为当前单元格没有专用的错误模板。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-121">This is required because there is currently no dedicated error template for cells.</span></span>  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     <span data-ttu-id="bf9f9-122">您可以通过替换来实现更广泛的自定义<xref:System.Windows.Controls.DataGridColumn.CellStyle%2A>列使用。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-122">You can implement more extensive customization by replacing the <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> used by the column.</span></span>  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a><span data-ttu-id="bf9f9-123">若要验证单个行中的多个值</span><span class="sxs-lookup"><span data-stu-id="bf9f9-123">To validate multiple values in a single row</span></span>  
  
1.  <span data-ttu-id="bf9f9-124">实现<xref:System.Windows.Controls.ValidationRule>检查多个属性的绑定的数据对象的子类。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-124">Implement a <xref:System.Windows.Controls.ValidationRule> subclass that checks multiple properties of the bound data object.</span></span> <span data-ttu-id="bf9f9-125">在你<xref:System.Windows.Controls.ValidationRule.Validate%2A>方法实现转换`value`参数值到<xref:System.Windows.Data.BindingGroup>实例。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-125">In your <xref:System.Windows.Controls.ValidationRule.Validate%2A> method implementation, cast the `value` parameter value to a <xref:System.Windows.Data.BindingGroup> instance.</span></span> <span data-ttu-id="bf9f9-126">然后可以访问通过此数据对象<xref:System.Windows.Data.BindingGroup.Items%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-126">You can then access the data object through the <xref:System.Windows.Data.BindingGroup.Items%2A> property.</span></span>  
  
     <span data-ttu-id="bf9f9-127">下面的示例展示了此过程来验证是否`StartDate`属性值`Course`对象是早于其`EndDate`属性值。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-127">The following example demonstrates this process to validate whether the `StartDate` property value for a `Course` object is earlier than its `EndDate` property value.</span></span>  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2.  <span data-ttu-id="bf9f9-128">添加验证规则与<xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType>集合。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-128">Add the validation rule to the <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> collection.</span></span> <span data-ttu-id="bf9f9-129"><xref:System.Windows.Controls.DataGrid.RowValidationRules%2A>属性提供直接访问权限<xref:System.Windows.Data.BindingGroup.ValidationRules%2A>属性的<xref:System.Windows.Data.BindingGroup>分组控件使用的所有绑定的实例。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-129">The <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> property provides direct access to the <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> property of a <xref:System.Windows.Data.BindingGroup> instance that groups all the bindings used by the control.</span></span>  
  
     <span data-ttu-id="bf9f9-130">下面的示例设置<xref:System.Windows.Controls.DataGrid.RowValidationRules%2A>在 XAML 中的属性。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-130">The following example sets the <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> property in XAML.</span></span> <span data-ttu-id="bf9f9-131"><xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>属性设置为<xref:System.Windows.Controls.ValidationStep.UpdatedValue>，以便仅在绑定的数据对象更新后进行的验证。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-131">The <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> property is set to <xref:System.Windows.Controls.ValidationStep.UpdatedValue> so that the validation occurs only after the bound data object is updated.</span></span>  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     <span data-ttu-id="bf9f9-132">当用户指定结束日期早于开始日期时，行标题中会显示一个红色感叹号 （！）。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-132">When a user specifies an end date that is earlier than the start date, a red exclamation mark (!) appears in the row header.</span></span> <span data-ttu-id="bf9f9-133">您可以更改此默认验证反馈，如下面的过程中所述。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-133">You can change this default validation feedback as described in the following procedure.</span></span>  
  
### <a name="to-customize-row-validation-feedback"></a><span data-ttu-id="bf9f9-134">若要自定义行验证反馈</span><span class="sxs-lookup"><span data-stu-id="bf9f9-134">To customize row validation feedback</span></span>  
  
-   <span data-ttu-id="bf9f9-135">设置 <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-135">Set the <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="bf9f9-136">此属性可以自定义为各个行验证反馈<xref:System.Windows.Controls.DataGrid>控件。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-136">This property enables you to customize row validation feedback for individual <xref:System.Windows.Controls.DataGrid> controls.</span></span> <span data-ttu-id="bf9f9-137">您也可以通过使用隐式行样式设置影响多个控件<xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-137">You can also affect multiple controls by using an implicit row style to set the <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     <span data-ttu-id="bf9f9-138">下面的示例使用一个更可见的指示符替换默认行验证反馈。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-138">The following example replaces the default row validation feedback with a more visible indicator.</span></span> <span data-ttu-id="bf9f9-139">当用户输入的值无效时，一个带有白色感叹号红色圆圈显示在行标题中。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-139">When a user enters an invalid value, a red circle with a white exclamation mark appears in the row header.</span></span> <span data-ttu-id="bf9f9-140">这是个行和单元格的验证错误。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-140">This occurs for both row and cell validation errors.</span></span> <span data-ttu-id="bf9f9-141">工具提示中显示相关联的错误消息。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-141">The associated error message is displayed in a ToolTip.</span></span>  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a><span data-ttu-id="bf9f9-142">示例</span><span class="sxs-lookup"><span data-stu-id="bf9f9-142">Example</span></span>  
 <span data-ttu-id="bf9f9-143">下面的示例提供了单元格和行验证的完整演示。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-143">The following example provides a complete demonstration for cell and row validation.</span></span> <span data-ttu-id="bf9f9-144">`Course`类提供了实现的示例数据对象<xref:System.ComponentModel.IEditableObject>以支持事务。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-144">The `Course` class provides a sample data object that implements <xref:System.ComponentModel.IEditableObject> to support transactions.</span></span> <span data-ttu-id="bf9f9-145"><xref:System.Windows.Controls.DataGrid>控件与交互<xref:System.ComponentModel.IEditableObject>以使用户能够通过按 esc 键还原更改。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-145">The <xref:System.Windows.Controls.DataGrid> control interacts with <xref:System.ComponentModel.IEditableObject> to enable users to revert changes by pressing ESC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf9f9-146">如果使用的 Visual Basic 中，在 MainWindow.xaml 的第一行中，替换`x:Class="DataGridValidation.MainWindow"`与`x:Class="MainWindow"`。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-146">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="DataGridValidation.MainWindow"` with `x:Class="MainWindow"`.</span></span>  
  
 <span data-ttu-id="bf9f9-147">若要测试验证，请尝试以下操作：</span><span class="sxs-lookup"><span data-stu-id="bf9f9-147">To test the validation, try the following:</span></span>  
  
-   <span data-ttu-id="bf9f9-148">在课程 ID 列中，输入一个非整数值。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-148">In the Course ID column, enter a non-integer value.</span></span>  
  
-   <span data-ttu-id="bf9f9-149">在结束日期列中，输入日期早于开始日期。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-149">In the End Date column, enter a date that is earlier than the Start Date.</span></span>  
  
-   <span data-ttu-id="bf9f9-150">删除课程 ID、 开始日期或结束日期中的值。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-150">Delete the value in Course ID, Start Date, or End Date.</span></span>  
  
-   <span data-ttu-id="bf9f9-151">若要撤消了无效的单元值，请将光标放回该单元格，然后按 ESC 键。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-151">To undo an invalid cell value, put the cursor back in the cell and press the ESC key.</span></span>  
  
-   <span data-ttu-id="bf9f9-152">若要撤消整个行的更改，当前单元格处于编辑模式时，请按 ESC 键两次。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-152">To undo changes for an entire row when the current cell is in edit mode, press the ESC key twice.</span></span>  
  
-   <span data-ttu-id="bf9f9-153">出现验证错误时，将鼠标指针移动行标题以查看相关联的错误消息中的指示符。</span><span class="sxs-lookup"><span data-stu-id="bf9f9-153">When a validation error occurs, move your mouse pointer over the indicator in the row header to see the associated error message.</span></span>  
  
 [!code-csharp[DataGrid_Validation#FullCode](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="bf9f9-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf9f9-154">See also</span></span>

- <xref:System.Windows.Controls.DataGrid>
- [<span data-ttu-id="bf9f9-155">DataGrid</span><span class="sxs-lookup"><span data-stu-id="bf9f9-155">DataGrid</span></span>](datagrid.md)
- [<span data-ttu-id="bf9f9-156">数据绑定</span><span class="sxs-lookup"><span data-stu-id="bf9f9-156">Data Binding</span></span>](../data/data-binding-wpf.md)
- [<span data-ttu-id="bf9f9-157">实现绑定验证</span><span class="sxs-lookup"><span data-stu-id="bf9f9-157">Implement Binding Validation</span></span>](../data/how-to-implement-binding-validation.md)
- [<span data-ttu-id="bf9f9-158">在自定义对象上实现验证逻辑</span><span class="sxs-lookup"><span data-stu-id="bf9f9-158">Implement Validation Logic on Custom Objects</span></span>](../data/how-to-implement-validation-logic-on-custom-objects.md)
