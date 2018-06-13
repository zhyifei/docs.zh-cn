---
title: WPF 中的代码隐藏和 XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: 09d4f010ca53c5e3d2d9dede172e7ae2102261b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541543"
---
# <a name="code-behind-and-xaml-in-wpf"></a>WPF 中的代码隐藏和 XAML
<a name="introduction"></a> 代码隐藏是一个术语用于描述与采用标记定义的对象联接的代码时[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]页进行标记编译。 本主题介绍隐藏代码的要求以及中的代码的可选内联代码机制[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。  
  
 本主题包含以下各节：  
  
-   [先决条件](#Prerequisites)  
  
-   [代码隐藏和 XAML 语言](#codebehind_and_the_xaml_language)  
  
-   [代码隐藏、 事件处理程序和 WPF 中的分部类要求](#Code_behind__Event_Handler__and_Partial_Class)  
  
-   [x： 代码](#x_Code)  
  
-   [内联代码限制](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>系统必备  
 本主题假定你已阅读[XAML 概述 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)及具有一些基本知识的[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]和面向对象的编程。  
  
<a name="codebehind_and_the_xaml_language"></a>   
## <a name="code-behind-and-the-xaml-language"></a>代码隐藏和 XAML 语言  
 XAML 语言包括语言级别功能，使它可以将代码文件与标记文件，从标记文件端相关联。 具体而言，XAML 语言定义的语言功能[X:class 指令](../../../../docs/framework/xaml-services/x-class-directive.md)， [X:subclass 指令](../../../../docs/framework/xaml-services/x-subclass-directive.md)，和[X:classmodifier 指令](../../../../docs/framework/xaml-services/x-classmodifier-directive.md)。 完全应生成代码的方式，以及如何将标记和代码，进行不是 XAML 语言指定的一部分。 它处于框架，例如 WPF 来确定如何将代码集成到，如何使用 XAML 在应用程序的编程模型和生成操作或其他支持的所有这些要求。  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>   
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>代码隐藏、 事件处理程序和 WPF 中的分部类要求  
  
-   分部类必须派生自支持的根元素的类型。  
  
-   请注意下的标记编译生成操作的默认行为，你可以将派生留空的分部类定义中的代码隐藏端。 编译的结果将假定页面根的后备类型是分部类中，作为基础，即使未指定。 但是，依赖于此行为不是一种最佳做法。  
  
-   在后面的代码中编写的事件处理程序必须是实例方法，并且不能为静态方法。 这些方法必须由标识的 CLR 命名空间中的分部类定义`x:Class`。 您不能限定事件处理程序，以指示名称[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器的事件处理程序事件布线，另一个类作用域中查找。  
  
-   处理程序必须在后备类型系统中匹配相应的事件的委托。  
  
-   对于 Microsoft Visual Basic 语言具体而言，你使用的是特定于语言的`Handles`关键字将与实例和处理程序声明，而不是附加处理程序中的属性中的事件的处理程序[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。 但是，此技术也存在一些限制，因为`Handles`关键字不能支持所有的特定功能[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]事件系统，如某些路由事件方案或附加事件。 有关详细信息，请参阅[Visual Basic 和 WPF 的事件处理](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md)。  
  
<a name="x_Code"></a>   
## <a name="xcode"></a>x： 代码  
 [X:code](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md)中定义的指令元素[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。 `x:Code`指令元素可以包含内联编程代码。 以内联方式定义的代码可以与进行交互[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]同一页面上。 下面的示例阐释了内联 C# 代码。 请注意，代码是内部`x:Code`元素和代码必须用引起`<CDATA[`...`]]>`进行转义的内容[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]，以便[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器 (解释[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]架构或[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]架构) 不会尝试解释内容按原义作为[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]。  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>   
## <a name="inline-code-limitations"></a>内联代码限制  
 你应考虑避免或限制使用内联代码。 在体系结构和编码原理，方面维护标记和代码隐藏之间的分隔保留设计器和开发人员角色得更为明显。 在更多技术级，为内联代码编写的代码可能难以编写，因为始终写入[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]生成分部类中，并且只能使用默认的 XML 命名空间映射。 因为不能添加`using`语句，您必须完全限定的许多[!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]所做的调用。 默认值[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]映射包括大多数而非全部[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]命名空间中存在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]程序集; 你将需要完全限定的类型和成员的其他 CLR 命名空间中包含的调用。 你还不能定义分部类以外在内联代码中，并且你引用的所有用户代码实体必须都存在作为成员或生成的分部类中的变量。 其他语言特定编程功能，例如宏或`#ifdef`对全局变量或生成变量，也是可用。 有关详细信息，请参阅[X:code 内部 XAML 类型](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md)。  
  
## <a name="see-also"></a>请参阅  
 [XAML 概述 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [x:Code 内部 XAML 类型](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md)  
 [生成 WPF 应用程序](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [XAML 语法详述](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)
