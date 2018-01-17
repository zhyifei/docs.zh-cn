---
title: "XAML 中的泛型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c0e5bfb4f327028f09e8c898cf07e5fec9a5f789
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="generics-in-xaml"></a>XAML 中的泛型
.NET Framework XAML 服务在 System.Xaml 中实现提供对使用泛型的 CLR 类型的支持。 这种支持包括作为类型参数指定的泛型约束和通过调用适当强制约束`Add`泛型集合用例的方法。 本主题描述使用和引用 XAML 中的泛型类型的方面。  
  
## <a name="xtypearguments"></a>x: TypeArguments  
 `x:TypeArguments`由 XAML 语言定义的指令。 当使用作为泛型类型，由支持的 XAML 类型的成员`x:TypeArguments`约束类型的泛型后备构造函数的参数传递。 有关适用于.NET Framework XAML 服务的引用语法用法的`x:TypeArguments`，其中包括语法示例，请参阅[X:typearguments 指令](../../../docs/framework/xaml-services/x-typearguments-directive.md)。  
  
 因为`x:TypeArguments`接收一个字符串，并具有类型转换器支持，通常将其声明中作为特性的 XAML 用法。  
  
 在 XAML 节点流中，通过声明`x:TypeArguments`可以从获取<xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType>在`StartObject`节点流中的位置。 返回值<xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType>是一份<xref:System.Xaml.XamlType>值。 可以通过调用来发出的 XAML 类型是否表示泛型类型的决定<xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>。  
  
## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a>规则和 XAML 中的泛型的语法约定  
 在 XAML 中，泛型类型必须始终表示为受约束的泛型;不受约束的泛型根本不在 XAML 类型系统或 XAML 节点流中存在且不能在 XAML 标记中表示。 可以在其所在的被引用的泛型的嵌套的类型约束的情况下用于 XAML 特性语法中引用泛型`x:TypeArguments`，或用例其中`x:Type`提供泛型类型的 CLR 类型引用。 通过支持这种情况<xref:System.Xaml.Schema.XamlTypeTypeConverter>由.NET Framework XAML 服务定义的类。  
  
 XAML 属性语法形式由启用<xref:System.Xaml.Schema.XamlTypeTypeConverter>改变典型 MSIL / 使用角度的 CLR 语法约定的类型和泛型，约束方括号，改为将约束容器的括号。 有关示例，请参阅[X:typearguments 指令](../../../docs/framework/xaml-services/x-typearguments-directive.md)。  
  
## <a name="generics-and-xaml-2009-features"></a>泛型和 XAML 2009 功能  
 如果使用 XAML 2009 而不是将 CLR 映射基类型，用于获取的公共语言基元的 XAML 类型转换，则可以使用[XAML 2009 内置类型](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)信息在中作为项`x:TypeArguments`。 例如，可以声明以下 (前缀映射未显示，但`x`是 XAML 2009 的 XAML 语言 XAML 命名空间):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
## <a name="generics-support-in-wpf-and-other-v35-frameworks"></a>WPF 和其他 v3.5 框架中的泛型支持  
 有关 XAML 2006 用法时特别面向 WPF 中， [X:class](../../../docs/framework/xaml-services/x-class-directive.md)还必须在与位于同一元素上提供`x:TypeArguments`，并且该元素必须在 XAML 文档的根元素。 根元素必须映射到具有至少一个类型参数的泛型类型。 一个示例是<xref:System.Windows.Navigation.PageFunction%601>。  
  
 可能的解决方法，以支持泛型用法包括定义自定义标记扩展可以返回的泛型类型，或提供一个包装类定义派生自泛型类型，但将在其自己的类定义中的泛型约束平展开。  
  
 在 WPF 和目标确定[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]，你可以使用 XAML 2009 功能以及`x:TypeArguments`，但仅针对宽松 XAML (未标记编译的 XAML)。 WPF 的已编译标记的 XAML 以及 XAML 的 BAML 形式当前不支持 XAML 2009 关键字和功能。  
  
 中的自定义工作流[!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)]为[!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)]不支持泛型 XAML 用法。  
  
## <a name="see-also"></a>请参阅  
 [x:TypeArguments 指令](../../../docs/framework/xaml-services/x-typearguments-directive.md)  
 [x:Class 指令](../../../docs/framework/xaml-services/x-class-directive.md)  
 [常见 XAML 语言基元的内置类型](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)
