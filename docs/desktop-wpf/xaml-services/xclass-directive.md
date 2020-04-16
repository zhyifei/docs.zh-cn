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
ms.openlocfilehash: f589fa70c2ee1c56544fa0f0152990478aa3761f
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433276"
---
# <a name="xclass-directive"></a>x:Class 指令
配置 XAML 标记编译以在标记和代码后面之间联接部分类。 代码部分类以通用语言规范 （CLS） 语言在单独的代码文件中定义，而标记部分类通常在 XAML 编译期间由代码生成创建。

## <a name="xaml-attribute-usage"></a>XAML 属性用法

```xaml
<object x:Class="namespace.classname"...>
  ...
</object>
```

## <a name="xaml-values"></a>XAML 值

|||
|-|-|
|`namespace`|可选。 指定包含 由 标识`classname`的部分类的 CLR 命名空间。 如果`namespace`指定，点 （.） 将分隔`namespace`和`classname`。 请参阅“备注”。|
|`classname`|必需。 指定连接加载的 XAML 和该 XAML 的代码后面的部分类的 CLR 名称。|

## <a name="dependencies"></a>依赖项

`x:Class`只能在 XAML 生产的根元素上指定。 `x:Class`在 XAML 生产中具有父对象的任何对象上无效。 有关详细信息，请参阅[\[MS-XAML\]部分 4.3.1.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))。

## <a name="remarks"></a>备注

该`namespace`值可能包含其他点，用于将相关命名空间组织到名称层次结构中，这是 .NET 编程中的一种常见技术。 只有`x:Class`值字符串中的最后一个点被解释为分隔`namespace`，`classname.`用作类的类`x:Class`不能是嵌套类。 不允许嵌套类，因为如果允许嵌套类，则确定字符串`x:Class`的点含义不明确。

在使用`x:Class`的现有编程模型中，`x:Class`是可选的，因为 XAML 页没有代码背后，是完全有效的。 但是，该功能与使用 XAML 的框架实现的生成操作进行交互。 `x:Class`功能还受 XAML 指定内容的各种分类在应用程序模型和相应的生成操作中的角色的影响。 如果 XAML 声明事件处理属性值或实例化定义类位于代码后面类中的自定义元素，则必须向相应的类提供`x:Class`指令引用（或[x：sub 类](xsubclass-directive.md)）以进行代码后面。

`x:Class`指令的值必须是指定类完全限定名称但没有任何程序集信息（等效于 ）<xref:System.Type.FullName%2A?displayProperty=nameWithType>的字符串。 对于简单应用程序，如果代码后面也以这种方式构造（代码定义从类级别开始），则可以省略 CLR 命名空间信息。

页面或应用程序定义的代码背后的文件必须位于代码文件中，该文件包含在生成已编译的应用程序并涉及标记编译的项目的一部分中。 您必须遵循 CLR 类的名称规则。 有关详细信息，请参阅[框架设计指南](../../../api/index.md)。 默认情况下，代码后面类必须为`public`;但是，您可以使用[x：Class 修改器指令](xclassmodifier-directive.md)在不同的访问级别定义它。

该属性的`x:Class`此解释仅适用于基于 CLR 的 XAML 实现，尤其是 .NET XAML 服务。 其他不基于 CLR 且不使用 .NET XAML 服务的其他 XAML 实现可能使用不同的解析公式来连接 XAML 标记和备份运行时代码。 有关 有关 的更多一般解释的详细信息`x:Class`，请参阅[\[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))。

在一定的体系结构级别中，在 .NET XAML 服务中未定义 。 `x:Class` 这是因为 .NET XAML 服务没有指定连接 XAML 标记和备份代码的编程模型。 `x:Class`该指令的其他用途可能由使用编程模型或应用程序模型来定义如何连接 XAML 标记和基于 CLR 的代码背后的特定框架实现。 每个框架都可以有自己的生成操作，这些操作启用生成环境中必须包括的某些行为或特定组件。 在框架中，生成操作也可能因用于代码后面的特定 CLR 语言而异。

## <a name="xclass-in-the-wpf-programming-model"></a>x：WPF编程模型中的类

在 WPF 应用程序和 WPF`x:Class`应用程序模型中，可以声明为作为 XAML 文件根并正在编译的任何元素的属性（其中 XAML 包含在具有`Page`生成操作的 WPF 应用程序项目中），也可以声明为已编译<xref:System.Windows.Application>WPF 应用程序的应用程序定义中的根元素。 在`x:Class`页面根或应用程序根以外的元素上声明，或在未编译的 WPF XAML 文件中进行声明，在 .NET 框架 3.0 和 .NET 框架 3.5 WPF XAML 编译器下会导致编译时错误。 有关 WPF 中`x:Class`处理的其他方面的信息，请参阅[WPF 中的代码背后和 XAML。](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)

## <a name="xclass-for-windows-workflow-foundation"></a>x：Windows 工作流基础类
对于 Windows 工作流`x:Class`基础，请命名完全在 XAML 中组成的自定义活动的类，或者为具有代码后面的活动设计器命名 XAML 页的部分类。

## <a name="silverlight-usage-notes"></a>银光使用说明

`x:Class`银光单独记录。 有关详细信息，请参阅[XAML 命名空间 （x：）语言功能（银光）](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).

## <a name="see-also"></a>请参阅

- [x:Subclass 指令](xsubclass-directive.md)
- [XAML 及 WPF 的自定义类](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [x:ClassModifier 指令](xclassmodifier-directive.md)
- [从 WPF 迁移到 System.Xaml 的类型](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
