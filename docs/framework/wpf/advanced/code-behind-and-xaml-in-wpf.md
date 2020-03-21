---
title: 代码背后和XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: 32283d5b81bf92999a97711ded13a8b533ae3028
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145340"
---
# <a name="code-behind-and-xaml-in-wpf"></a>WPF 中的代码隐藏和 XAML
<a name="introduction"></a>代码后面是一个术语，用于描述在标记编译时[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]与标记定义对象联接的代码。 本主题介绍代码后面的要求，以及 中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]代码的替代内联代码机制。  
  
 本主题包含以下各节：  
  
- [系统必备](#Prerequisites)  
  
- [代码背后和XAML语言](#codebehind_and_the_xaml_language)  
  
- [WPF 中的代码落后、事件处理程序和部分类要求](#Code_behind__Event_Handler__and_Partial_Class)  
  
- [x：代码](#x_Code)  
  
- [内联代码限制](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>
## <a name="prerequisites"></a>系统必备  
 本主题假定您已阅读[XAML 概述 （WPF），](../../../desktop-wpf/fundamentals/xaml.md)并且对 CLR 和面向对象编程有一些基本知识。  
  
<a name="codebehind_and_the_xaml_language"></a>
## <a name="code-behind-and-the-xaml-language"></a>代码背后和XAML语言  
 XAML 语言包括语言级功能，这些功能使得可以从标记文件端将代码文件与标记文件相关联。 具体来说，XAML 语言定义了语言功能[x：类指令](../../../desktop-wpf/xaml-services/xclass-directive.md) [、x：子类指令](../../../desktop-wpf/xaml-services/xsubclass-directive.md)和[x：类修改器指令](../../../desktop-wpf/xaml-services/xclassmodifier-directive.md)。 代码的生成方式以及如何集成标记和代码并不是 XAML 语言指定的部分。 由 WPF 等框架来确定如何集成代码、如何在应用程序和编程模型中使用 XAML 以及构建操作或所有所需的其他支持。  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>WPF 中的代码落后、事件处理程序和部分类要求  
  
- 部分类必须派生自支持根元素的类型。  
  
- 请注意，在标记编译生成操作的默认行为下，可以将派生留空于代码后面的部分类定义中。 编译的结果将假定页面根的背衬类型是部分类的基础，即使未指定。 但是，依赖此行为不是最佳做法。  
  
- 在代码后面编写的事件处理程序必须是实例方法，不能是静态方法。 这些方法必须由 标识`x:Class`的 CLR 命名空间中的部分类定义。 不能限定事件处理程序的名称来指示[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器查找事件处理程序以查找其他类作用域中的事件布线。  
  
- 处理程序必须匹配支持类型系统中相应事件的委托。  
  
- 具体对于 Microsoft Visual Basic 语言，可以使用特定于`Handles`语言的关键字将处理程序与处理程序声明中的实例和事件相关联，而不是将处理程序附加到 中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]的属性。 但是，此技术确实有一些限制，`Handles`因为关键字不支持[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]事件系统的所有特定功能，例如某些路由事件方案或附加事件。 有关详细信息，请参阅[可视化基本和 WPF 事件处理](visual-basic-and-wpf-event-handling.md)。  
  
<a name="x_Code"></a>
## <a name="xcode"></a>x：代码  
 [x：代码](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md)是在 中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]定义的指令元素。 `x:Code`指令元素可以包含内联编程代码。 内联定义的代码可以在同一页上与 的代码[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]进行交互。 下面的示例说明了内联 C# 代码。 请注意，代码位于元素内`x:Code`，并且代码必须由 ... `<CDATA[``]]>`以逃避 XML 的内容，以便[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器（解释[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]架构或[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]架构）不会尝试将内容从字面上解释为 XML。  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>
## <a name="inline-code-limitations"></a>内联代码限制  
 应考虑避免或限制内联代码的使用。 在体系结构和编码理念方面，保持标记和代码后面的分离使设计人员和开发人员的角色更加明显。 在更技术化的层面上，为内联代码编写的代码可能难以编写，因为您始终写入[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]生成的部分类，并且只能使用默认的 XML 命名空间映射。 由于无法添加`using`语句，因此必须完全限定您进行的许多 API 调用。 默认[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]映射包括[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]程序集中存在的大多数（但不是所有 CLR 命名空间）;您必须完全限定对其他 CLR 命名空间中包含的类型和成员的调用。 您也不能在内联代码中定义除部分类之外的任何内容，并且引用的所有用户代码实体都必须作为成员或变量存在于生成的部分类中。 其他特定于语言的编程功能（如宏或`#ifdef`针对全局变量或生成变量）也不可用。 有关详细信息，请参阅[x：代码内部 XAML 类型](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md)。  
  
## <a name="see-also"></a>另请参阅

- [XAML 概述 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [x:Code 内部 XAML 类型](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md)
- [生成 WPF 应用程序](../app-development/building-a-wpf-application-wpf.md)
- [XAML 语法详述](xaml-syntax-in-detail.md)
