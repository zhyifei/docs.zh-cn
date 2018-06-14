---
title: 如何：应用 Windows 窗体控件中的特性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: 49c2aaa48a48e33a71b5112db31991975011551d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529631"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a>如何：应用 Windows 窗体控件中的特性
若要开发组件和控件的设计环境与正确交互，并在运行时正确执行，您需要正确将特性应用于类和成员。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何使用一个自定义控件上的多个特性。 控件演示简单的日志记录功能。 当控件绑定到数据源时，它显示发送中的数据源的值<xref:System.Windows.Forms.DataGridView>控件。 如果值超出指定的值`Threshold`属性，`ThresholdExceeded`引发事件。  
  
 `AttributesDemoControl`记录值`LogEntry`类。 `LogEntry`类是一种模板类，这意味着它参数化的类型的记录。 例如，如果`AttributesDemoControl`是类型的日志记录值`float`，每个`LogEntry`实例声明并在使用，如下所示。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
>  因为`LogEntry`进行参数化由任意类型，它必须使用反射来操作的参数类型。 该阈值功能起作用，参数类型的`T`必须实现<xref:System.IComparable>接口。  
  
 承载的窗体`AttributesDemoControl`定期查询性能计数器。 每个值并打包在`LogEntry`适当类型的并且添加到窗体的<xref:System.Windows.Forms.BindingSource>。 `AttributesDemoControl`通过其数据绑定接收的值并显示中的值<xref:System.Windows.Forms.DataGridView>控件。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 第一个代码示例是`AttributesDemoControl`实现。 第二个代码示例演示使用的窗体`AttributesDemoControl`。  
  
## <a name="class-level-attributes"></a>类级别特性  
 某些属性是在类级别应用。 下面的代码示例显示通常适用于在 Windows 窗体控件的特性。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a>TypeConverter 属性  
 <xref:System.ComponentModel.TypeConverterAttribute> 是另一个常用的类级别特性。 下面的代码示例演示它的使用`LogEntry`类。 此示例还演示如何实现<xref:System.ComponentModel.TypeConverter>为`LogEntry`类型，调用`LogEntryTypeConverter`。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a>成员级别的属性  
 某些属性是在成员级别应用。 下面的代码示例显示某些通常应用于的 Windows 窗体控件属性的属性。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a>AmbientValue 属性  
 下面的示例演示<xref:System.ComponentModel.AmbientValueAttribute>并显示支持该产品与设计环境交互的代码。 此交互称为*环境*。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a>数据绑定特性  
 下面的示例演示复杂数据绑定的实现。 类级别<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>显示以前，指定`DataSource`和`DataMember`用于数据绑定属性。 <xref:System.ComponentModel.AttributeProviderAttribute>指定为的类型`DataSource`属性将绑定。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a>编译代码  
  
-   承载的窗体`AttributesDemoControl`需要引用`AttributesDemoControl`以生成的程序集。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.IComparable>  
 <xref:System.Windows.Forms.DataGridView>  
 [使用 .NET Framework 开发自定义 Windows 窗体控件](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Windows 窗体控件中的特性](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 [如何： 序列化与 DesignerSerializationVisibilityAttribute 标准类型的集合](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)
