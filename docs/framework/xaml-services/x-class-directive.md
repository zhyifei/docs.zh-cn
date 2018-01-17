---
title: "x:Class 指令"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:Class
- xClass
- Class
helpviewer_keywords:
- Class attribute in XAML [XAML Services]
- XAML [XAML Services], x:Class attribute
- x:Class attribute [XAML Services]
ms.assetid: bc4a3d8e-76e2-423e-a5d1-159a023e82ec
caps.latest.revision: "27"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b894a56caa3644bae140e7ec37cf5b55ab093a59
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="xclass-directive"></a>x:Class 指令
配置 XAML 标记编译标记和代码隐藏之间联接分部类。 代码的分部类定义在单独的代码文件中[!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]语言中，而在 XAML 编译过程的代码生成由通常创建标记分部类。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```  
<object x:Class="namespace.classname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`namespace`|可选。 指定[!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)]命名空间包含由标识的分部类`classname`。 如果`namespace`一个点 （.） 分隔的指定`namespace`和`classname`。 请参阅“备注”。|  
|`classname`|必须的。 指定[!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)]连接加载的 XAML 和代码隐藏该 xaml 的分部类的名称。|  
  
## <a name="dependencies"></a>依赖项  
 `x:Class`仅可以在 XAML 生产的根元素上指定。 `x:Class`在任何具有在 XAML 生产环境中的父对象上无效。 有关详细信息，请参阅[ \[MS-XAML\]部分 4.3.1.6](http://go.microsoft.com/fwlink/?LinkId=114525)。  
  
## <a name="remarks"></a>备注  
 `namespace`值可能包含其他的点，可以将相关命名空间组织成名称层次结构，这是一种在.NET Framework 编程中的常用技术。 仅字符串中的最后一个点`x:Class`值解释为隔开`namespace`和`classname.`用作类`x:Class`不能为嵌套的类。 不允许嵌套的类，因为确定个点构成的含义`x:Class`是允许嵌套的类的情况下不明确的字符串。  
  
 在存在的编程模型，可使用`x:Class`，`x:Class`意义上说，它是完全有效，能够不有任何代码隐藏的 XAML 页中是可选的。 但是，该功能与生成操作交互，使用 XAML 的框架的实施方式。 `x:Class`功能也会影响应用程序模型中有以及生成操作中相应的 XAML 指定内容的各种类型的角色。 如果你的 XAML 声明事件处理特性值，或者实例化自定义元素定义的类在代码隐藏类中的位置，你需要提供`x:Class`指令引用 (或[X:subclass](../../../docs/framework/xaml-services/x-subclass-directive.md)) 到相应的代码隐藏的类。  
  
 值`x:Class`指令必须是一个字符串，指定完全限定的名称的类，但不包含任何程序集信息 (等效于<xref:System.Type.FullName%2A?displayProperty=nameWithType>)。 对于简单的应用程序，则可以忽略 CLR 命名空间信息，如果代码隐藏的构建这种方式 （在类级别的代码定义开始）。  
  
 页面或应用程序定义的代码隐藏文件必须是生成已编译的应用程序和涉及标记编译的项目的一部分包括代码文件中。 你必须遵循 CLR 类的命名规则。 有关详细信息，请参阅[Framework 设计准则](../../../docs/standard/design-guidelines/index.md)。 默认情况下，代码隐藏类必须是`public`; 但是，可以通过使用而在不同的访问级别定义[X:classmodifier 指令](../../../docs/framework/xaml-services/x-classmodifier-directive.md)。  
  
 此解释`x:Class`属性仅适用于基于 CLR 的 XAML 实现中，尤其是到.NET Framework XAML 服务。 其他 XAML 实现不基于 CLR 和未使用.NET Framework XAML 服务可能使用不同的分辨率公式用于连接 XAML 标记和备份运行时代码。 有关更多常规解释的详细信息`x:Class`，请参阅[ \[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525)。  
  
 体系结构的含义某一级别`x:Class`.NET Framework XAML 服务中未定义。 这是因为.NET Framework XAML 服务未指定的 XAML 标记和备份代码连接所用的编程模型。 其他用法`x:Class`可能由特定框架，它们使用的编程模型或应用程序模型定义如何连接 XAML 标记和基于 CLR 的代码隐藏实现指令。 每个框架可以自己启用一些行为或必须包含在生成环境中的特定组件的生成操作。 在框架中，生成操作也可能因具体取决于用于隐藏代码的特定 CLR 语言。  
  
## <a name="xclass-in-the-wpf-programming-model"></a>WPF 编程模型中的 x： 类  
 在 WPF 应用程序和 WPF 应用程序模型，`x:Class`可以声明为属性，其中是 XAML 文件的根和正在编译的任何元素 (其中具有的 WPF 应用程序项目中包含 XAML`Page`生成操作)，或为 <c4 1> <xref:System.Windows.Application> 中编译的 WPF 应用程序的应用程序定义的根。 声明`x:Class`页面根或应用程序根目录以外的元素上或在未编译的 WPF XAML 文件，将导致编译时错误下的[!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)]和[!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)]WPF XAML 编译器。 有关的其他方面`x:Class`处理在 WPF 中，请参阅[代码隐藏和 XAML 在 WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)。  
  
## <a name="xclass-for-windows-workflow-foundation"></a>X:class for Windows Workflow Foundation  
 对于 Windows Workflow Foundation，`x:Class`命名完全在 XAML 中，构成的自定义活动的类或具有隐藏代码的活动设计器命名 XAML 页面，该分部类。  
  
## <a name="silverlight-usage-notes"></a>Silverlight 用法说明  
 `x:Class`适用于 Silverlight 是分开记录。 有关详细信息，请参阅[XAML Namespace （x:）语言功能 (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081)。  
  
## <a name="see-also"></a>请参阅  
 [x:Subclass 指令](../../../docs/framework/xaml-services/x-subclass-directive.md)  
 [XAML 及 WPF 的自定义类](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)  
 [x:ClassModifier 指令](../../../docs/framework/xaml-services/x-classmodifier-directive.md)  
 [从 WPF 迁移到 System.Xaml 的类型](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
