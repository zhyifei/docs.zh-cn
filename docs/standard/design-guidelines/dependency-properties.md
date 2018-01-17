---
title: "依赖项属性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b9e60f3e941dd1d7d89675f4483ae940b039ba10
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="dependency-properties"></a>依赖项属性
依赖项属性 (DP) 是将其值存储在属性存储而不是存储在类型变量 （字段），例如一个常规属性。  
  
 附加依赖项属性是一种建模为静态的 Get 和 Set 方法表示描述对象和其容器之间的关系的"属性"的依赖项属性 (例如的位置`Button`对象上`Panel`容器）。  
  
 **✓ 执行**提供的依赖项属性，如果你需要以支持诸如样式、 触发器、 数据绑定、 动画、 动态资源和继承的 WPF 功能的属性。  
  
## <a name="dependency-property-design"></a>依赖项属性设计  
 **✓ 执行**继承<xref:System.Windows.DependencyObject>，或子类型，在实现依赖项属性之一。 类型提供一个非常有效的属性存储实现，并自动支持 WPF 数据绑定。  
  
 **✓ 执行**提供正则 CLR 属性和公共的静态只读字段，存储的实例<xref:System.Windows.DependencyProperty?displayProperty=nameWithType>每个依赖属性。  
  
 **✓ 执行**实现通过调用实例方法的依赖项属性<xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType>和<xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>。  
  
 **✓ 执行**通过在"属性"。 使用属性的名称来命名依赖项属性的静态字段  
  
 **X 不**在代码中显式设置的依赖项属性的默认值; 而是将它们设置在元数据中。  
  
 如果显式设置属性默认值，则你可能会阻止通过一些隐式方式，如样式设置该属性。  
  
 **X 不**将代码放在属性访问器标准 code 之外，若要访问静态字段。  
  
 代码不会执行如果通过隐式方式，如样式，设置该属性，因为样式直接使用的静态字段。  
  
 **X 不**依赖项属性用于存储安全数据。 可以公开访问甚至私有依赖项属性。  
  
## <a name="attached-dependency-property-design"></a>附加依赖项属性设计  
 在前面部分所述的依赖项属性表示声明类型; 内部的属性例如，`Text`属性是属性的`TextButton`，其中声明它。 一种特殊的依赖项属性是附加依赖项属性。  
  
 附加属性的一个典型示例是<xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType>属性。 该属性表示按钮 （不网格的） 列位置，但它才是相关，如果按钮包含在网格中，因此它"附加"到按钮的网格。  
  
```  
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition />  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
  
    <Button Grid.Column="0">Click</Button>  
    <Button Grid.Column="1">Clack</Button>  
</Grid>  
```  
  
 附加属性的属性定义类似于主要的正则依赖项属性，只不过访问器都由静态的 Get 和 Set 方法：  
  
```  
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
 属性通常实现了称为验证。 在尝试更改属性的值时，将执行验证逻辑。  
  
 遗憾的是依赖项属性访问器不能包含任意验证代码。 相反，依赖项属性的验证逻辑，必须在注册过程中指定。  
  
 **X 不**将依赖项属性的验证逻辑放入的属性访问器。 相反，将传递到的验证回调`DependencyProperty.Register`方法。  
  
## <a name="dependency-property-change-notifications"></a>依赖项属性更改通知  
 **X 不**在依赖项属性访问器中实现更改通知逻辑。 依赖项属性具有一种内置的更改通知功能，必须通过提供更改通知回调到使用<xref:System.Windows.PropertyMetadata>。  
  
## <a name="dependency-property-value-coercion"></a>依赖项属性值强制转换  
 属性存储实际修改之前，属性 setter 到给定的值修改通过 setter 时将属性强制转换。  
  
 **X 不**在依赖项属性访问器中实现强制逻辑。  
  
 依赖项属性具有内置的强制转换功能，，但它可通过提供强制回调到`PropertyMetadata`。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [常用设计模型](../../../docs/standard/design-guidelines/common-design-patterns.md)
