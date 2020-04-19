---
title: x:Subclass 指令
ms.date: 03/30/2017
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
ms.openlocfilehash: e85e0fb5a0e1a865ed84a93767f8152a115bbe5f
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432640"
---
# <a name="xsubclass-directive"></a>x:Subclass 指令

在提供时`x:Class`修改 XAML 标记编译行为。 提供的派生类应基于`x:Class``x:Class``x:Class`，而不是创建基于 的部分类。

## <a name="xaml-attribute-usage"></a>XAML 属性用法

```xaml
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">
   ...
</object>
```

## <a name="xaml-values"></a>XAML 值

|||
|-|-|
|`namespace`|可选。 指定包含 的`classname`CLR 命名空间。 如果`namespace`指定，点 （.） 将分隔`namespace`和`classname`。|
|`classname`|必需。 指定连接加载的 XAML 和该 XAML 的代码后面的部分类的 CLR 名称。 请参阅“备注”。|
|`subclassNamespace`|可选。 可以不同于`namespace`如果每个命名空间可以解析另一个。 指定包含 的`subclassName`CLR 命名空间。 如果`subclassName`指定，点 （.） 将分隔`subclassNamespace`和`subclassName`。|
|`subclassName`|必需。 指定子类的 CLR 名称。|

## <a name="dependencies"></a>依赖项

[x：类指令](xclass-directive.md)也必须在同一对象上提供，并且该对象必须是 XAML 生产的根元素。

## <a name="remarks"></a>备注

`x:Subclass`主要用于不支持部分类声明的语言。

用作 的`x:Subclass`类不能是嵌套类，并且必须`x:Subclass`引用根对象，如"依赖"部分中所述。

否则，.NET XAML 服务实现未定义 其`x:Subclass`概念含义。 这是因为 .NET XAML 服务行为未指定连接 XAML 标记和背码的总体编程模型。 与`x:Class`和`x:Subclass`相关的其他概念的实现由使用编程模型或应用程序模型来定义如何连接 XAML 标记、编译标记和基于 CLR 的代码后面的特定框架执行。 每个框架可能都有自己的生成操作，这些操作启用某些行为或必须包含在生成环境中的特定组件。 在框架中，生成操作还可以根据用于代码后面的特定 CLR 语言而变化。

## <a name="wpf-usage-notes"></a>WPF 用法说明

`x:Subclass`可以位于页面根上或应用程序定义中的<xref:System.Windows.Application>根上，该定义已具有`x:Class`。 在`x:Subclass`页面或应用程序根以外的任何元素上声明，或在不存在`x:Class`时指定它，会导致编译时错误。

创建正确适用于该方案的`x:Subclass`派生类相当复杂。 您可能需要检查中间文件（通过标记编译项目 obj 文件夹中生成的 .g 文件，以及包含 .xaml 文件名的名称）。 这些中间文件可以帮助您确定编译应用程序中联接部分类中某些编程构造的来源。

派生类中的事件处理程序必须`internal override`（`Friend Overrides`在 Microsoft Visual Basic 中）才能覆盖在编译过程中中间类中创建的处理程序的存根。 否则，派生类实现将隐藏（阴影）中间类实现，并且不会调用中间类处理程序。

定义 和`x:Class``x:Subclass`时，不需要为 引用`x:Class`的类提供任何实现。 您只需通过`x:Class`属性为其指定名称，以便编译器对它在中间文件中创建的类具有一些指导（在这种情况下，编译器不会选择默认名称）。 您可以为`x:Class`类提供一个实现;但是，这不是使用 和`x:Class``x:Subclass`的典型方案。

## <a name="see-also"></a>请参阅

- [x:Class 指令](xclass-directive.md)
- [XAML 及 WPF 的自定义类](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
