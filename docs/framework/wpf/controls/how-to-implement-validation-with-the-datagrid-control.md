---
title: 如何：用 DataGrid 控件实现验证
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], validation
- validation [WPF], DataGrid
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
ms.openlocfilehash: 20fcc8ebafb25e4e4f176447972e7637aaa5cd7d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557870"
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a>如何：用 DataGrid 控件实现验证
<xref:System.Windows.Controls.DataGrid>控制，你可以执行的单元格和行级别的验证。 与单元格级别验证时用户更新的值验证绑定的数据对象的各个属性。 与行级别验证用户提交更改的行时验证整个数据对象。 也可以为验证错误，提供自定义的可视反馈，或使用默认的视觉反馈，<xref:System.Windows.Controls.DataGrid>控件提供。  
  
 下面的过程介绍如何验证将规则应用到<xref:System.Windows.Controls.DataGrid>绑定和自定义的可视反馈。  
  
### <a name="to-validate-individual-cell-values"></a>若要验证各个单元格的值  
  
-   用于列绑定上指定一个或多个验证规则。 这是类似于验证简单控件中的数据中所述[数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)。  
  
     下面的示例演示<xref:System.Windows.Controls.DataGrid>其中包含四列绑定到不同的业务对象的属性的控件。 三个列指定<xref:System.Windows.Controls.ExceptionValidationRule>通过设置<xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>属性`true`。  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     当用户输入无效值 （如非整数课程 ID 列中） 时，围绕单元格将出现一个红色边框。 你可以更改此默认验证反馈以下过程中所述。  
  
### <a name="to-customize-cell-validation-feedback"></a>若要自定义单元格验证反馈  
  
-   设置列的<xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A>为样式属性适用于列的编辑控件。 在运行时创建编辑控件，因为不能使用<xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType>附加就像处理简单控件的属性。  
  
     下面的示例通过将通过使用验证规则的三个列共享的错误样式更新前面的示例。 当用户输入值无效时的样式的单元格背景色更改以及添加工具提示。 请注意，使用的触发器，以确定是否有验证错误。 这是必需的因为当前单元格没有专用的错误模板。  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     你可以通过将实现更广泛的自定义<xref:System.Windows.Controls.DataGridColumn.CellStyle%2A>使用的列。  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a>若要验证的单个行中的多个值  
  
1.  实现<xref:System.Windows.Controls.ValidationRule>检查多个属性的绑定的数据对象的子类。 在你<xref:System.Windows.Controls.ValidationRule.Validate%2A>方法实现中，强制转换`value`参数值以<xref:System.Windows.Data.BindingGroup>实例。 然后，就可以访问数据对象，通过<xref:System.Windows.Data.BindingGroup.Items%2A>属性。  
  
     下面的示例演示此过程以验证是否`StartDate`属性值`Course`对象是早于其`EndDate`属性值。  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2.  向其添加验证规则<xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType>集合。 <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A>属性提供直接访问权限<xref:System.Windows.Data.BindingGroup.ValidationRules%2A>属性<xref:System.Windows.Data.BindingGroup>组控件使用的所有绑定的实例。  
  
     下面的示例设置<xref:System.Windows.Controls.DataGrid.RowValidationRules%2A>在 XAML 中的属性。 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>属性设置为<xref:System.Windows.Controls.ValidationStep.UpdatedValue>，以便仅在更新绑定的数据对象后出现的有效性。  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     当用户指定的结束日期早于开始日期时，行标题中将显示一个红色感叹号 （！）。 你可以更改此默认验证反馈以下过程中所述。  
  
### <a name="to-customize-row-validation-feedback"></a>若要自定义行验证反馈  
  
-   设置 <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType> 属性。 此属性使您能够自定义为单个行验证反馈<xref:System.Windows.Controls.DataGrid>控件。 此外可以通过使用隐式行样式设置影响多个控件<xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType>属性。  
  
     下面的示例将默认行验证反馈替换更直观的指示器。 当用户输入值无效时，红色圆圈及白色感叹号显示行标题中。 行和单元格的验证错误发生这种情况。 工具提示中显示相关联的错误消息。  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a>示例  
 下面的示例提供单元格和行验证的完整的演示。 `Course`类提供用于实现的示例数据对象<xref:System.ComponentModel.IEditableObject>为支持事务。 <xref:System.Windows.Controls.DataGrid>与控件交互<xref:System.ComponentModel.IEditableObject>以便用户可以通过按 ESC 还原更改。  
  
> [!NOTE]
>  如果使用的 Visual Basic 中，在 MainWindow.xaml 的第一行中，将`x:Class="DataGridValidation.MainWindow"`与`x:Class="MainWindow"`。  
  
 若要测试验证，请尝试以下方法：  
  
-   在过程 ID 列中，输入一个非整数值。  
  
-   在结束日期列中，输入日期早于开始日期。  
  
-   删除课程 ID、 开始日期或结束日期中的值。  
  
-   若要撤消无效的单元格值，将光标置于返回单元格中，然后按 ESC 键。  
  
-   若要撤消整个行的更改，当前单元格处于编辑模式时，请按 ESC 键两次。  
  
-   出现验证错误时，将鼠标指针移到行标题，以查看关联的错误消息中的指示器。  
  
 [!code-csharp[DataGrid_Validation#FullCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.DataGrid>  
 [数据网格](../../../../docs/framework/wpf/controls/datagrid.md)  
 [数据绑定](../../../../docs/framework/wpf/data/data-binding-wpf.md)  
 [实现绑定验证](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [在自定义对象上实现验证逻辑](../../../../docs/framework/wpf/data/how-to-implement-validation-logic-on-custom-objects.md)
