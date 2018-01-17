---
title: "x:Subclass 指令"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
caps.latest.revision: "20"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1d620b59208b9dc852abee3dd2e4d6c58b223d70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="xsubclass-directive"></a>x:Subclass 指令
修改 XAML 标记编译行为时`x:Class`还提供。 而不是创建分部类，其中基于`x:Class`，提供`x:Class`作为中间类，创建然后预计提供的派生的类基于`x:Class`。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```  
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`namespace`|可选。 指定一个包含的 CLR 命名空间`classname`。 如果`namespace`一个点 （.） 分隔的指定`namespace`和`classname`。|  
|`classname`|必须的。 指定连接加载的 XAML 和代码隐藏该 xaml 的分部类的 CLR 名称。 请参阅“备注”。|  
|`subclassNamespace`|可选。 可以不同于`namespace`如果每个命名空间可以解决其他。 指定一个包含的 CLR 命名空间`subclassName`。 如果`subclassName`一个点 （.） 分隔的指定`subclassNamespace`和`subclassName`。|  
|`subclassName`|必须的。 指定子类的 CLR 的名称。|  
  
## <a name="dependencies"></a>依赖项  
 [X:class 指令](../../../docs/framework/xaml-services/x-class-directive.md)还必须提供对同一对象，该对象必须是 XAML 生产的根元素。  
  
## <a name="remarks"></a>备注  
 `x:Subclass`使用情况主要适用于不支持分部类声明的语言。  
  
 用作类`x:Subclass`嵌套的类，不能和`x:Subclass`必须指向根对象的"依赖关系"部分中所述。  
  
 否则为的概念含义`x:Subclass`未定义的.NET Framework XAML 服务实现。 这是因为.NET Framework XAML 服务行为并不指定的 XAML 标记和备份代码连接所用的总体编程模型。 与相关的更多概念实现`x:Class`和`x:Subclass`由特定框架，它们使用的编程模型或应用程序模型定义 XAML 标记、 已编译的标记和基于 CLR 的代码隐藏连接的方式执行。 每个框架可能具有其自己启用某些行为或必须包含在生成环境中的特定组件的生成操作。 在框架中，生成操作可以还取决于用于隐藏代码的特定 CLR 语言。  
  
## <a name="wpf-usage-notes"></a>WPF 用法说明  
 `x:Subclass`在页面根上或可以是<xref:System.Windows.Application>在应用程序定义中，已经有根`x:Class`。 声明`x:Subclass`页面或应用程序的根，或未指定它以外的任何元素`x:Class`存在，将导致编译时错误。  
  
 创建派生类为正确该工作`x:Subclass`方案是相当复杂。 你可能需要检查中间文件 （你的项目的 obj 文件夹中生成的标记编译，其名称合并.xaml 文件名称的.g 文件）。 这些中间文件可以帮助你确定在编译的应用程序中的联接分部类中的某些编程构造的源。  
  
 在派生类中的事件处理程序必须是`internal override`(`Friend Overrides`中[!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)]) 若要在编译期间创建中间类中重写处理程序的存根。 否则为派生的类实现隐藏） 的中间类实现，并且不会调用中间类处理程序。  
  
 当你同时定义`x:Class`和`x:Subclass`，不需要提供的类的引用的任何实现`x:Class`。 只需为其命名，通过`x:Class`属性，以便编译器具有它在 （编译器不会选择默认名称在这种情况下） 的中间文件中创建的类的一些指导。 你可以为提供`x:Class`类实现; 但是，这不是同时使用的典型方案`x:Class`和`x:Subclass`。  
  
## <a name="see-also"></a>请参阅  
 [x:Class 指令](../../../docs/framework/xaml-services/x-class-directive.md)  
 [XAML 及 WPF 的自定义类](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
