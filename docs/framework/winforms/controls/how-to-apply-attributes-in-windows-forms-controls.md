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
ms.openlocfilehash: 273d32927582f4467a92cd3b8f87e699c1f167d7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922782"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a>如何：应用 Windows 窗体控件中的特性
若要开发正确与设计环境进行交互并在运行时正确执行的组件和控件, 需要正确地将特性应用于类和成员。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何在自定义控件上使用多个特性。 控件说明了简单的日志记录功能。 当控件绑定到数据源时, 它将在<xref:System.Windows.Forms.DataGridView>控件中显示数据源发送的值。 如果某个值超出了由`Threshold`属性指定的值`ThresholdExceeded` , 则会引发事件。  
  
 `AttributesDemoControl` 使用`LogEntry`类记录值。 `LogEntry`类是一个模板类, 这意味着它将在它所记录的类型中进行参数化。 例如, 如果`AttributesDemoControl`是日志记录值类型`float`, 则按如下`LogEntry`方式声明并使用每个实例。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> 由于`LogEntry`是由任意类型参数化的, 因此它必须使用反射来对参数类型进行操作。 要使阈值功能正常工作, 参数类型`T`必须<xref:System.IComparable>实现接口。  
  
 托管`AttributesDemoControl`查询性能计数器的窗体会定期执行。 每个值都打包为`LogEntry`适当类型的, 并添加到窗体的<xref:System.Windows.Forms.BindingSource>中。 通过数据绑定<xref:System.Windows.Forms.DataGridView>接收值并在控件中显示值。 `AttributesDemoControl`  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 第一个代码示例是`AttributesDemoControl`实现。 第二个代码示例演示使用的`AttributesDemoControl`窗体。  
  
## <a name="class-level-attributes"></a>类级属性  
 某些属性应用于类级别。 下面的代码示例演示通常应用于 Windows 窗体控件的特性。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a>TypeConverter 特性  
 <xref:System.ComponentModel.TypeConverterAttribute>是另一种常用的类级属性。 下面的代码示例演示如何使用`LogEntry`类。 此示例还演示<xref:System.ComponentModel.TypeConverter> `LogEntry`类型的的实现, 该类型名`LogEntryTypeConverter`为。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a>成员级特性  
 某些属性应用于成员级别。 下面的代码示例演示一些通常应用于 Windows 窗体控件的属性的属性。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a>AmbientValue 特性  
 下面的示例演示<xref:System.ComponentModel.AmbientValueAttribute>并显示支持与设计环境交互的代码。 这种交互称为 "*环境*"。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a>数据绑定属性  
 下面的示例演示如何实现复杂数据绑定。 前面所示的<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>类级别指定了用于数据`DataSource`绑定`DataMember`的和属性。 <xref:System.ComponentModel.AttributeProviderAttribute>指定`DataSource`属性将绑定到的类型。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a>编译代码  
  
- 承载的`AttributesDemoControl`窗体需要引用`AttributesDemoControl`程序集才能生成。  
  
## <a name="see-also"></a>请参阅

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [使用 .NET Framework 开发自定义 Windows 窗体控件](developing-custom-windows-forms-controls.md)
- [Windows 窗体控件中的特性](attributes-in-windows-forms-controls.md)
- [如何：用 DesignerSerializationVisibilityAttribute 序列化标准类型的集合](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))
