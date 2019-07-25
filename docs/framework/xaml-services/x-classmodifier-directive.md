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
ms.openlocfilehash: c3c08f61b49a6367663cf02099dda86d1a692284
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484744"
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier 指令
如果`x:Class`还提供了, 则修改 XAML 编译行为。 具体而言, 而不是创建`class` `Public`具有访问级别 ( `x:Class`默认值) 的部分, 而是创建具有`NotPublic`访问级别的。 此行为会影响生成的程序集中类的访问级别。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|*NotPublic*|要传递给指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>的确切字符串与<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>不同, 具体取决于所使用的代码隐藏编程语言。 请参阅“备注”。|  
  
## <a name="dependencies"></a>依赖项  
 还必须在同一元素上提供[x:Class](x-class-directive.md) , 并且该元素必须是页面中的根元素。 有关详细信息, 请参阅[ \[\] 4.3.1.8 部分](https://go.microsoft.com/fwlink/?LinkId=114525)。  
  
## <a name="remarks"></a>备注  
 .NET Framework XAML 服务`x:ClassModifier`用法的值因编程语言而异。 要使用的字符串取决于每种语言如何实现<xref:System.CodeDom.Compiler.CodeDomProvider>其和返回的类型转换器, 以定义<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>和<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>的含义, 以及该语言是否区分大小写。  
  
- 对于C#, 要传递的要传递<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>的字符串为。 `internal`  
  
- 对于 Microsoft Visual Basic .net, 要传递<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `Friend`的字符串为。  
  
- 对于C++/cli, 不存在支持编译 XAML 的目标;因此, 传递的值未指定。  
  
 你还可以在<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> Visual Basic`public`中C#指定`Public` (在中为); 但是<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> , 由于已是<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>默认行为, 因此不常指定。  
  
 具有等效用户代码访问级别限制的其他`private`值 (如在中C#) 与不相关`x:ClassModifier` , 因为 XAML 中不支持嵌套类引用, 因此, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>修饰符具有相同的效果.  
  
## <a name="security-notes"></a>安全说明  
 中`x:ClassModifier`声明的访问级别仍受特定框架及其功能的解释。 Wpf 包含加载和实例化类型的功能`x:ClassModifier` , `internal`其中, 如果通过包 URI 引用从 WPF 资源引用此类, 则为。 这种情况与其他框架所实现的情况类似, 但并不依赖`x:ClassModifier`于阻止所有可能的实例化尝试。  
  
## <a name="see-also"></a>请参阅

- [x:Class 指令](x-class-directive.md)
- [WPF 中的代码隐藏和 XAML](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:FieldModifier 指令](x-fieldmodifier-directive.md)
- [安全性 (WPF)](../wpf/security-wpf.md)
- [从 WPF 迁移到 System.Xaml 的类型](types-migrated-from-wpf-to-system-xaml.md)
