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
# <a name="how-to-implement-validation-with-the-datagrid-control"></a>如何：使用 DataGrid 控件实现验证
该<xref:System.Windows.Controls.DataGrid>控件使您能够在单元格和行级别执行验证。 使用单元格级验证，当用户更新值时，可以验证绑定数据对象的单个属性。 使用行级验证，当用户将更改提交到行时，可以验证整个数据对象。 您还可以为验证错误提供自定义的可视反馈，或使用<xref:System.Windows.Controls.DataGrid>控件提供的默认视觉反馈。  
  
 以下过程介绍如何将验证规则应用于<xref:System.Windows.Controls.DataGrid>绑定并自定义可视反馈。  
  
### <a name="to-validate-individual-cell-values"></a>验证单个单元格值  
  
- 在列使用的绑定上指定一个或多个验证规则。 这类似于在简单控件中验证数据，如[数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)中所述。  
  
     下面的示例显示一个<xref:System.Windows.Controls.DataGrid>控件，该控件的四列绑定到业务对象的不同属性。 三列<xref:System.Windows.Controls.ExceptionValidationRule>通过将<xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>属性设置为`true`指定 。  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     当用户输入无效值（如课程 ID 列中的非整数）时，单元格周围会出现红色边框。 您可以按照以下过程所述更改此默认验证反馈。  
  
### <a name="to-customize-cell-validation-feedback"></a>自定义单元格验证反馈  
  
- 将列的属性<xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A>设置为适合列编辑控件的样式。 由于编辑控件是在运行时创建的，因此不能像使用简单控件那样<xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType>使用附加属性。  
  
     下面的示例通过添加由三列共享的具有验证规则的错误样式来更新前面的示例。 当用户输入无效值时，样式将更改单元格背景颜色并添加工具提示。 请注意使用触发器来确定是否存在验证错误。 这是必需的，因为当前没有专用的单元格错误模板。  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     您可以通过替换列使用来实现<xref:System.Windows.Controls.DataGridColumn.CellStyle%2A>更广泛的自定义。  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a>验证一行中的多个值  
  
1. 实现一<xref:System.Windows.Controls.ValidationRule>个子类，该子类检查绑定数据对象的多个属性。 在方法<xref:System.Windows.Controls.ValidationRule.Validate%2A>实现中，将`value`参数值转换为<xref:System.Windows.Data.BindingGroup>实例。 然后，您可以通过<xref:System.Windows.Data.BindingGroup.Items%2A>属性访问数据对象。  
  
     下面的示例演示了此过程，以验证`StartDate``Course`对象的属性值是否早于其`EndDate`属性值。  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2. 将验证规则添加到<xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType>集合中。 该<xref:System.Windows.Controls.DataGrid.RowValidationRules%2A>属性提供对<xref:System.Windows.Data.BindingGroup.ValidationRules%2A><xref:System.Windows.Data.BindingGroup>实例属性的直接访问，该实例对控件使用的所有绑定进行分组。  
  
     下面的示例在 XAML 中设置<xref:System.Windows.Controls.DataGrid.RowValidationRules%2A>属性。 属性<xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>设置为<xref:System.Windows.Controls.ValidationStep.UpdatedValue>，以便验证仅在更新绑定数据对象后进行。  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     当用户指定早于开始日期的结束日期时，行标题中将显示一个红色感叹号 （！）。 您可以按照以下过程所述更改此默认验证反馈。  
  
### <a name="to-customize-row-validation-feedback"></a>自定义行验证反馈  
  
- 设置 <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType> 属性。 此属性使您能够为各个<xref:System.Windows.Controls.DataGrid>控件自定义行验证反馈。 还可以通过使用隐式行样式来设置<xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType>属性来影响多个控件。  
  
     下面的示例将默认行验证反馈替换为更可见的指示器。 当用户输入无效值时，行标题中将显示一个带有白色感叹号的红色圆圈。 对于行和单元验证错误，都会发生这种情况。 关联的错误消息将显示在工具提示中。  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a>示例  
 下面的示例提供了单元格和行验证的完整演示。 类`Course`提供一个示例数据对象，该<xref:System.ComponentModel.IEditableObject>对象实现以支持事务。 该<xref:System.Windows.Controls.DataGrid>控件与<xref:System.ComponentModel.IEditableObject>这些控件交互，使用户能够通过按 ESC 还原更改。  
  
> [!NOTE]
> 如果使用 Visual Basic，则在 MainWindow.xaml 的第一行中`x:Class="DataGridValidation.MainWindow"`，`x:Class="MainWindow"`替换为 。  
  
 要测试验证，请尝试以下操作：  
  
- 在"课程 ID"列中，输入非整数值。  
  
- 在"结束日期"列中，输入早于开始日期的日期。  
  
- 删除课程 ID、开始日期或结束日期中的值。  
  
- 要撤消无效的单元格值，请将光标放回单元格中，然后按 ESC 键。  
  
- 要在当前单元格处于编辑模式时撤消整个行的更改，请按 ESC 键两次。  
  
- 发生验证错误时，将鼠标指针移到行标题中的指示器上以查看关联的错误消息。  
  
 [!code-csharp[DataGrid_Validation#FullCode](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.DataGrid>
- [DataGrid](datagrid.md)
- [数据绑定](../../../desktop-wpf/data/data-binding-overview.md)
- [实现绑定验证](../data/how-to-implement-binding-validation.md)
- [在自定义对象上实现验证逻辑](../data/how-to-implement-validation-logic-on-custom-objects.md)
