---
title: 在控件中应用特性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: b8ecd516cf6bb189c6ad1b208dd8e3a5444f001c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741491"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a>방법: Windows Forms 컨트롤에서 특성 적용
若要开发正确与设计环境进行交互并在运行时正确执行的组件和控件，需要正确地将特性应用于类和成员。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何在自定义控件上使用多个特性。 控件说明了简单的日志记录功能。 当控件绑定到数据源时，它将在 <xref:System.Windows.Forms.DataGridView> 控件中显示数据源发送的值。 如果某个值超出 `Threshold` 属性指定的值，则会引发 `ThresholdExceeded` 事件。  
  
 `AttributesDemoControl` 使用 `LogEntry` 类记录值。 `LogEntry` 类是一个模板类，这意味着它将在它所记录的类型中进行参数化。 例如，如果 `AttributesDemoControl` 记录 `float`类型的值，则声明每个 `LogEntry` 实例，并按如下所示使用。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> 由于 `LogEntry` 由任意类型参数化，因此它必须使用反射来对参数类型进行操作。 要使阈值功能正常工作，参数类型 `T` 必须实现 <xref:System.IComparable> 接口。  
  
 承载 `AttributesDemoControl` 的窗体定期查询性能计数器。 每个值都打包在适当类型的 `LogEntry` 中并添加到窗体的 <xref:System.Windows.Forms.BindingSource>中。 `AttributesDemoControl` 通过数据绑定接收值并在 <xref:System.Windows.Forms.DataGridView> 控件中显示值。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 第一个代码示例是 `AttributesDemoControl` 实现。 第二个代码示例演示使用 `AttributesDemoControl`的窗体。  
  
## <a name="class-level-attributes"></a>类级属性  
 某些属性应用于类级别。 下面的代码示例演示通常应用于 Windows 窗体控件的特性。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a>TypeConverter 特性  
 <xref:System.ComponentModel.TypeConverterAttribute> 是另一个常用的类级属性。 下面的代码示例演示了如何对 `LogEntry` 类使用。 此示例还演示了 `LogEntry` 类型（称为 `LogEntryTypeConverter`）的 <xref:System.ComponentModel.TypeConverter> 实现。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a>成员级特性  
 某些属性应用于成员级别。 下面的代码示例演示一些通常应用于 Windows 窗体控件的属性的属性。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a>AmbientValue 特性  
 下面的示例演示了 <xref:System.ComponentModel.AmbientValueAttribute>，并显示了支持与设计环境交互的代码。 这种交互称为 "*环境*"。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a>数据绑定属性  
 下面的示例演示如何实现复杂数据绑定。 上面所示的类级别 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>指定了用于数据绑定的 `DataSource` 和 `DataMember` 属性。 <xref:System.ComponentModel.AttributeProviderAttribute> 指定 `DataSource` 属性将绑定到的类型。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
- 承载 `AttributesDemoControl` 的窗体需要引用 `AttributesDemoControl` 的程序集才能生成。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](developing-custom-windows-forms-controls.md)
- [Windows Forms 컨트롤의 특성](attributes-in-windows-forms-controls.md)
- [如何：用 DesignerSerializationVisibilityAttribute 序列化标准类型的集合](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))
