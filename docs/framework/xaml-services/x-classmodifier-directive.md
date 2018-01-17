---
title: "x:ClassModifier 指令"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
caps.latest.revision: "22"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1a4918e23a915ee07eace388ea2cea512c2e479d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier 指令
修改 XAML 编译行为时`x:Class`还提供。 具体而言，而不是创建一个分部`class`具有`Public`访问级别 （默认值），提供`x:Class`使用创建`NotPublic`访问级别。 此行为会影响中生成的程序集的类的访问级别。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|*NotPublic*|确切的字符串传递的用于指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>与<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>各不相同，具体取决于你使用的代码隐藏编程语言。 请参阅“备注”。|  
  
## <a name="dependencies"></a>依赖项  
 [X:class](../../../docs/framework/xaml-services/x-class-directive.md)还必须提供在同一元素上并且该元素必须在页中的根元素。 有关详细信息，请参阅[ \[MS-XAML\]部分 4.3.1.8](http://go.microsoft.com/fwlink/?LinkId=114525)。  
  
## <a name="remarks"></a>备注  
 值`x:ClassModifier`.NET Framework XAML 服务中使用情况因编程语言。 要使用的字符串取决于每种语言的实现方式其<xref:System.CodeDom.Compiler.CodeDomProvider>和它将返回定义的含义的类型转换器<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>和<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>，以及该语言是区分大小写。  
  
-   有关[!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)]，要传递的用于指定的字符串<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>是`internal`。  
  
-   有关[!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)]，要传递的用于指定的字符串<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>是`Friend`。  
  
-   有关[!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)]，没有目标存在编译 XAML 支持，; 因此，未指定要传递的值。  
  
 你还可以指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>(`public`中[!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)]，`Public`中[!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]); 但是，指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>不常做是因为<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>已是默认行为。  
  
 其他值与等效的用户代码访问级别限制，如`private`中[!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)]，不相关的`x:ClassModifier`因为在 XAML 中，不支持嵌套的类引用，因此，<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>修饰符有相同的效果。  
  
## <a name="security-notes"></a>安全说明  
 中声明的访问级别`x:ClassModifier`仍将受到由特定框架和其功能的解释。 WPF 包括功能，可加载和实例化类型其中`x:ClassModifier`是`internal`，如果从 WPF 通过包 URI 引用资源引用该类。 这种情况并且可能由其他框架实现类似的其他人，因此不依赖于以独占方式在`x:ClassModifier`若要阻止所有可能的实例化尝试。  
  
## <a name="see-also"></a>请参阅  
 [x:Class 指令](../../../docs/framework/xaml-services/x-class-directive.md)  
 [WPF 中的代码隐藏和 XAML](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [x:FieldModifier 指令](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md)  
 [安全性 (WPF)](../../../docs/framework/wpf/security-wpf.md)  
 [从 WPF 迁移到 System.Xaml 的类型](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
