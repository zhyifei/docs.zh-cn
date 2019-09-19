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
ms.openlocfilehash: f6f02998a7648693bd731d6b2afdfd4499abaa04
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053912"
---
# <a name="xsubclass-directive"></a>x:Subclass 指令
如果`x:Class`还提供了，则修改 XAML 标记编译行为。 不是创建基于`x:Class`的分部类，而是将提供`x:Class`的作为中间类创建，然后提供的派生类`x:Class`应基于。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xaml  
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`namespace`|可选。 指定包含`classname`的 CLR 命名空间。 如果`namespace`指定了, 则句点 (.) 分隔`namespace`和`classname`。|  
|`classname`|必需。 指定用于连接加载的 XAML 的分部类的 CLR 名称和该 XAML 的代码隐藏。 请参阅“备注”。|  
|`subclassNamespace`|可选。 如果每个命名`namespace`空间都可以解析另一个，则可以与不同。 指定包含`subclassName`的 CLR 命名空间。 如果`subclassName`指定了, 则句点 (.) 分隔`subclassNamespace`和`subclassName`。|  
|`subclassName`|必需。 指定子类的 CLR 名称。|  
  
## <a name="dependencies"></a>依赖项  
 还必须在同一对象上提供[X：Class 指令](x-class-directive.md)，该对象必须是 XAML 生产的根元素。  
  
## <a name="remarks"></a>备注  
 `x:Subclass`用法主要用于不支持分部类声明的语言。  
  
 用作的`x:Subclass`类不能是嵌套类，并且`x:Subclass`必须引用根对象，如 "依赖项" 一节中所述。  
  
 否则，.NET Framework XAML 服务实现`x:Subclass`未定义概念含义。 这是因为 .NET Framework XAML 服务行为未指定 XAML 标记和支持代码的连接总体编程模型。 与`x:Class` 和`x:Subclass`相关的进一步概念的实现由使用编程模型或应用程序模型的特定框架执行，用于定义如何连接 XAML 标记、编译的标记和基于 CLR 的代码隐藏。 每个框架可能有自己的生成操作，这些操作可实现某些行为，或必须包含在生成环境中的特定组件。 在框架中，生成操作还会根据用于代码隐藏的特定 CLR 语言而有所不同。  
  
## <a name="wpf-usage-notes"></a>WPF 使用说明  
 `x:Subclass`可以位于页根上，也<xref:System.Windows.Application>可以位于应用程序定义中已有`x:Class`的根上。 在`x:Subclass`页或应用程序根目录之外的任何元素上进行声明，或在不`x:Class`存在的位置进行声明会导致编译时错误。  
  
 创建适用于`x:Subclass`方案的派生类非常复杂。 你可能需要检查中间文件（通过标记编译在项目的 obj 文件夹中生成的 g 文件，其中包含包含 .xaml 文件名的名称）。 这些中间文件可帮助您在已编译的应用程序的已联接分部类中确定某些编程构造的源。  
  
 派生类中的事件处理程序必须`internal override`是`Friend Overrides` （在 Microsoft Visual Basic 中），以便在编译期间为在中间类中创建的处理程序重写存根。 否则，派生类实现将隐藏中间类实现，并且不调用中间类处理程序。  
  
 如果同时`x:Class`定义和`x:Subclass`，则不需要为所引用的`x:Class`类提供任何实现。 只需通过`x:Class`属性为其指定一个名称，以便编译器对它在中间文件中创建的类具有一些指导（在此例中，编译器不选择默认名称）。 您可以为`x:Class`类提供实现; 但是，这并不是`x:Class`使用和`x:Subclass`的典型方案。  
  
## <a name="see-also"></a>请参阅

- [x:Class 指令](x-class-directive.md)
- [XAML 及 WPF 的自定义类](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
