---
title: 依赖项属性
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75c83dc75d1c86c89169fcc54220ced2a195bfbe
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44079082"
---
# <a name="dependency-properties"></a>依赖项属性
依赖项属性 (DP) 是将其值存储在属性存储，而不是将其存储在类型变量 （字段），例如一个常规属性。  
  
 非附加依赖项属性是一种依赖关系属性建模为表示描述的对象和其容器之间的关系的"属性"的静态 Get 和 Set 方法 (例如，位置`Button`对象上`Panel`容器）。  
  
 **✓ DO** 提供的依赖项属性，如果你需要以支持诸如样式、 触发器、 数据绑定、 动画、 动态资源和继承的 WPF 功能的属性。  
  
## <a name="dependency-property-design"></a>依赖项属性设计  
 **✓ DO** 继承<xref:System.Windows.DependencyObject>，或子类型，在实现依赖项属性之一。 类型提供了一个非常有效的属性存储实现，并且自动支持 WPF 数据绑定。  
  
 **✓ DO** 提供正则 CLR 属性和公共的静态只读字段，存储的实例<xref:System.Windows.DependencyProperty?displayProperty=nameWithType>每个依赖属性。  
  
 **✓ DO** 实现通过调用实例方法的依赖项属性<xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType>和<xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>。  
  
 **✓ DO** 通过在"属性"。 使用属性的名称来命名依赖项属性的静态字段  
  
 **X DO NOT** 在代码中显式设置的依赖项属性的默认值; 而是将它们设置在元数据中。  
  
 如果显式设置属性默认值，可能会阻止通过某些隐式的方式，如样式设置该属性。  
  
 **X DO NOT** 将代码放在属性访问器标准 code 之外，若要访问静态字段。  
  
 代码不会执行如果通过隐式的方式，如样式，设置该属性，因为样式直接使用静态字段。  
  
 **X DO NOT** 依赖项属性用于存储安全数据。 可公开访问甚至私有依赖项属性。  
  
## <a name="attached-dependency-property-design"></a>附加依赖项属性设计  
 在上一部分中所述的依赖项属性表示内部属性的声明类型;例如，`Text`属性是属性的`TextButton`，该声明。 一种特殊的依赖项属性是附加依赖项属性。  
  
 附加属性的一个典型示例是<xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType>属性。 该属性表示按钮 （不网格的） 列的位置，但它才是相关，如果按钮包含在一个网格，因此它"附加到"按钮的网格。  
  
```xaml
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition />  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
  
    <Button Grid.Column="0">Click</Button>  
    <Button Grid.Column="1">Clack</Button>  
</Grid>  
```  
  
 附加属性的定义类似于主要的常规依赖关系属性，只不过访问器都是静态的 Get 和 Set 方法：  
  
```csharp
public class Grid {  
  
    public static int GetColumn(DependencyObject obj) {  
        return (int)obj.GetValue(ColumnProperty);  
    }  
  
    public static void SetColumn(DependencyObject obj, int value) {  
        obj.SetValue(ColumnProperty,value);  
    }  
  
    public static readonly DependencyProperty ColumnProperty =  
        DependencyProperty.RegisterAttached(  
            "Column",  
            typeof(int),  
            typeof(Grid)  
    );  
}  
```  
  
## <a name="dependency-property-validation"></a>依赖项属性验证  
 属性通常实现所谓的验证。 当尝试将属性的值更改时执行验证逻辑。  
  
 遗憾的是依赖项属性访问器不能包含任意验证代码。 相反，需要在注册过程中指定依赖项属性验证逻辑。  
  
 **X DO NOT** 将依赖项属性的验证逻辑放入的属性访问器。 相反，传递验证回调到`DependencyProperty.Register`方法。  
  
## <a name="dependency-property-change-notifications"></a>依赖项属性更改通知  
 **X DO NOT** 在依赖项属性访问器中实现更改通知逻辑。 依赖项属性具有一个内置更改通知功能，必须使用通过提供到的更改通知回调<xref:System.Windows.PropertyMetadata>。  
  
## <a name="dependency-property-value-coercion"></a>依赖项属性值强制转换  
 属性强制转换发生时实际上修改的属性存储之前，setter 修改指定的属性 setter 的值。  
  
 **X DO NOT** 在依赖项属性访问器中实现强制逻辑。  
  
 依赖项属性具有一个内置的强制转换的功能，且可通过提供强制回调到`PropertyMetadata`。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [常用设计模型](../../../docs/standard/design-guidelines/common-design-patterns.md)
