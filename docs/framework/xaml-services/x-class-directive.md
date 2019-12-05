---
title: x:Class 指令
ms.date: 03/30/2017
f1_keywords:
- x:Class
- xClass
- Class
helpviewer_keywords:
- Class attribute in XAML [XAML Services]
- XAML [XAML Services], x:Class attribute
- x:Class attribute [XAML Services]
ms.assetid: bc4a3d8e-76e2-423e-a5d1-159a023e82ec
ms.openlocfilehash: d6baa6d8eb3a6d3520fb1549e2182f27ca52c36a
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837241"
---
# <a name="xclass-directive"></a>x:Class 指令
将 XAML 标记编译配置为在标记和代码隐藏之间加入分部类。 代码分部类在单独的代码文件中以公共语言规范（CLS）语言定义，而标记分部类通常在 XAML 编译过程中由代码生成创建。  
  
## <a name="xaml-attribute-usage"></a>XAML 特性用法  
  
```xaml  
<object x:Class="namespace.classname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`namespace`|可选。 指定一个 CLR 命名空间，该命名空间包含由 `classname`标识的分部类。 如果指定 `namespace`，则圆点（.）将 `namespace` 和 `classname`隔开。 请参阅“备注”。|  
|`classname`|必须的。 指定用于连接加载的 XAML 的分部类的 CLR 名称和该 XAML 的代码隐藏。|  
  
## <a name="dependencies"></a>依赖项  
 只能在 XAML 生产的根元素上指定 `x:Class`。 对于在 XAML 生产中具有父对象的任何对象，`x:Class` 无效。 有关详细信息，请参阅[\[MS-XAML\] 部分 4.3.1.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))。  
  
## <a name="remarks"></a>备注  
 `namespace` 值可能包含用于将相关命名空间组织到名称层次结构中的其他点，这是 .NET Framework 编程的一种常用技术。 只有 `x:Class` 值的字符串中的最后一个点被解释为分隔 `namespace` 并 `classname.` 用作 `x:Class` 的类不能是嵌套类。 不允许使用嵌套类，因为如果允许嵌套类，则确定 `x:Class` 字符串的点的含义不明确。  
  
 在使用 `x:Class`的现有编程模型中，`x:Class` 是可选的，因为有一个 XAML 页没有代码隐藏。 但是，该功能与使用 XAML 的框架实现的生成操作交互。 `x:Class` 功能还受 XAML 指定内容的各种分类在应用程序模型中以及对应的生成操作中的作用。 如果 XAML 声明事件处理特性值或实例化自定义元素（其中定义类在代码隐藏类中），则必须为代码隐藏提供相应类的 `x:Class` 指令引用（或[x:Subclass](x-subclass-directive.md)）。  
  
 `x:Class` 指令的值必须是一个字符串，该字符串指定类的完全限定名称，但不包含任何程序集信息（等效于 <xref:System.Type.FullName%2A?displayProperty=nameWithType>）。 对于简单应用程序，如果代码隐藏也是以这种方式构造的，则可以省略 CLR 命名空间信息（代码定义从类级别开始）。  
  
 页面或应用程序定义的代码隐藏文件必须位于代码文件中，该代码文件包含在生成已编译的应用程序并涉及标记编译的项目中。 必须遵循 CLR 类的名称规则。 有关详细信息，请参阅[框架设计准则](../../standard/design-guidelines/index.md)。 默认情况下，代码隐藏类必须 `public`;但是，可以使用[X:ClassModifier 指令](x-classmodifier-directive.md)在不同的访问级别定义它。  
  
 `x:Class` 特性的这一解释仅适用于基于 CLR 的 XAML 实现，尤其是 .NET Framework XAML 服务。 其他不基于 CLR 并且不使用 .NET Framework XAML 服务的 XAML 实现可能会使用不同的解析公式来连接 XAML 标记和支持运行时代码。 有关 `x:Class`的更一般解释的详细信息，请参阅[\[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))。  
  
 在特定的体系结构级别上，`x:Class` 在 .NET Framework XAML 服务中未定义。 这是因为 .NET Framework XAML 服务不指定用于连接 XAML 标记和支持代码的编程模型。 `x:Class` 指令的其他用法可能由使用编程模型或应用程序模型的特定框架实现，以定义如何连接 XAML 标记和基于 CLR 的代码隐藏。 每个框架都可以有自己的生成操作，这些操作可实现某些必须包括在生成环境中的行为或特定组件。 在框架中，生成操作也可能根据用于代码隐藏的特定 CLR 语言而有所不同。  
  
## <a name="xclass-in-the-wpf-programming-model"></a>WPF 编程模型中的 X：Class  
 在 WPF 应用程序和 WPF 应用程序模型中，可以将 `x:Class` 声明为作为 XAML 文件的根的任何元素的属性，并且正在编译（其中，XAML 包含在具有 `Page` 生成操作的 WPF 应用程序项目中），或者声明为编译的 WPF 应用程序的应用程序定义中的 <xref:System.Windows.Application> 根。 在不是页根或应用程序根的元素上或在未编译的 WPF XAML 文件上声明 `x:Class` 会导致在 .NET Framework 3.0 和 .NET Framework 3.5 WPF XAML 编译器下发生编译时错误。 有关 WPF 中 `x:Class` 处理的其他方面的信息，请参阅[wpf 中的代码隐藏和 XAML](../wpf/advanced/code-behind-and-xaml-in-wpf.md)。  
  
## <a name="xclass-for-windows-workflow-foundation"></a>适用于 Windows Workflow Foundation 的 X：Class  
 对于 Windows Workflow Foundation，`x:Class` 命名完全在 XAML 中构成的自定义活动的类，或使用代码隐藏来命名活动设计器的 XAML 页的分部类。  
  
## <a name="silverlight-usage-notes"></a>Silverlight Usage 备注。  
 单独说明了 `x:Class` for Silverlight。 有关详细信息，请参阅[XAML 命名空间（x：）语言功能（Silverlight）](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95))。  
  
## <a name="see-also"></a>另请参阅

- [x:Subclass 指令](x-subclass-directive.md)
- [XAML 及 WPF 的自定义类](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [x:ClassModifier 指令](x-classmodifier-directive.md)
- [从 WPF 迁移到 System.Xaml 的类型](types-migrated-from-wpf-to-system-xaml.md)
