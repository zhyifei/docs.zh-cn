---
title: x:ClassModifier 指令
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: a24277a4d5fbc4870157b6c8ba00ba71ba61e656
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837228"
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier 指令
如果同时提供了 `x:Class`，则修改 XAML 编译行为。 具体而言，而不是创建具有 `Public` 访问级别（默认值）的部分 `class`，而是使用 `NotPublic` 访问级别创建提供的 `x:Class`。 此行为会影响生成的程序集中类的访问级别。  
  
## <a name="xaml-attribute-usage"></a>XAML 特性用法  
  
```xaml  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|*NotPublic*|要传递来指定 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 与 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 的确切字符串会有所不同，具体取决于所使用的代码隐藏编程语言。 请参阅“备注”。|  
  
## <a name="dependencies"></a>依赖项  
 还必须在同一元素上提供[x：Class](x-class-directive.md) ，并且该元素必须是页面中的根元素。 有关详细信息，请参阅[\[MS-XAML\] 部分 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))。  
  
## <a name="remarks"></a>备注  
 .NET Framework XAML 服务使用情况中 `x:ClassModifier` 的值因编程语言而异。 要使用的字符串取决于每种语言如何实现其 <xref:System.CodeDom.Compiler.CodeDomProvider>，以及它返回的类型转换器，用于定义 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 和 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>的含义，以及该语言是否区分大小写。  
  
- 对于C#，要传递给指定 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `internal`的字符串。  
  
- 对于 Microsoft Visual Basic .NET，传递来指定 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 的字符串 `Friend`。  
  
- 对于C++/cli，不存在支持编译 XAML 的目标;因此，传递的值未指定。  
  
 您还可以在 Visual Basic 中指定 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> C#（`public` 在 `Public` 中）;不过，指定 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 很少完成，因为 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 已是默认行为。  
  
 具有等效用户代码访问级别限制的其他值（如 `private` C#）与 `x:ClassModifier` 无关，因为 XAML 中不支持嵌套类引用，因此，<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 修饰符具有相同的效果。  
  
## <a name="security-notes"></a>安全说明  
 `x:ClassModifier` 中声明的访问级别仍受特定框架及其功能的解释。 WPF 包含加载和实例化类型的功能，其中 `x:ClassModifier` `internal`，前提是通过包 URI 引用从 WPF 资源引用此类。 这种情况与其他框架所实现的情况类似，但并不完全依赖于 `x:ClassModifier` 来阻止所有可能的实例化尝试。  
  
## <a name="see-also"></a>另请参阅

- [x:Class 指令](x-class-directive.md)
- [WPF 中的代码隐藏和 XAML](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:FieldModifier 指令](x-fieldmodifier-directive.md)
- [安全性（WPF）](../wpf/security-wpf.md)
- [从 WPF 迁移到 System.Xaml 的类型](types-migrated-from-wpf-to-system-xaml.md)
