---
title: "x:FieldModifier 指令"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
caps.latest.revision: "15"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 77745744c0da1e4b4425af6d8e4319faaf524908
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xfieldmodifier-directive"></a>x:FieldModifier 指令
修改 XAML 编译行为，以便与定义的已命名的对象引用的字段<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>而不是访问<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>默认行为。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|*Public*|确切的字符串将传递以指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>与<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>各不相同，具体取决于使用的代码隐藏编程语言。 请参阅“备注”。|  
  
## <a name="dependencies"></a>依赖项  
 如果 XAML 生产使用`x:FieldModifier`必须声明该 XAML 生产的根元素的任意位置， [X:class 指令](../../../docs/framework/xaml-services/x-class-directive.md)。  
  
## <a name="remarks"></a>备注  
 `x:FieldModifier`不适用于声明一个类或其成员的常规访问级别。 当是 XAML 生产的一部分的特定 XAML 对象处理时，并成为一个对象，它可以访问应用程序的对象图中，它是仅适用于的 XAML 处理行为。 默认情况下，此类对象的字段引用将保持私有，从而防止控件使用者直接修改对象图。 相反，控件使用者需要使用标准模式由所支持的编程模型，如获取布局根、 子元素集合，专用的公共属性，修改的对象图，依次类推。  
  
 值`x:FieldModifier`属性因编程语言中，并在特定框架其用途而异。 要使用的字符串取决于每种语言的实现方式其<xref:System.CodeDom.Compiler.CodeDomProvider>和它将返回定义的含义的类型转换器<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>和<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>，以及该语言是区分大小写。  
  
-   有关[!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)]，要传递的用于指定的字符串<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>是`public`。  
  
-   有关[!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)]，要传递的用于指定的字符串<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>是`Public`。  
  
-   有关[!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)]，XAML 没有目标当前存在; 因此，要传递的字符串未定义。  
  
 你还可以指定<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>(`internal`中[!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)]，`Friend`中[!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]) 但指定<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>不常见因为`NotPublic`因为行为已默认值。  
  
 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>是默认行为，因为它是很少编译 XAML 程序集外部的代码需要对 XAML 创建的元素的访问。 WPF 安全体系结构以及 XAML 编译行为将声明为公共，存储元素实例的字段，除非专门设置`x:FieldModifier`为允许公共访问。  
  
 `x:FieldModifier`才具有的元素相关[X:name 指令](../../../docs/framework/xaml-services/x-name-directive.md)因为该名称用于引用后它是公共的字段。  
  
 默认情况下，根元素的分部类是公共的则但是，您可以通过使其非公共使用[X:classmodifier 指令](../../../docs/framework/xaml-services/x-classmodifier-directive.md)。 [X:classmodifier 指令](../../../docs/framework/xaml-services/x-classmodifier-directive.md)还会影响根元素类的实例的访问级别。 你可以同时放置`x:Name`和`x:FieldModifier`上根元素，但这只是使公共字段副本的根元素，使用真正的根元素类的访问级别仍然受[X:classmodifier 指令](../../../docs/framework/xaml-services/x-classmodifier-directive.md)。  
  
## <a name="see-also"></a>另请参阅  
 [XAML 及 WPF 的自定义类](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)  
 [WPF 中的代码隐藏和 XAML](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [x:Name 指令](../../../docs/framework/xaml-services/x-name-directive.md)  
 [Building a WPF Application (WPF)](../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)（生成 WPF 应用程序 (WPF)）  
 [x:ClassModifier 指令](../../../docs/framework/xaml-services/x-classmodifier-directive.md)
