---
title: PresentationOptions:Freeze 特性
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: d3e0cee293a9585b972b0145da953976ed94b74c
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991430"
---
# <a name="presentationoptionsfreeze-attribute"></a><span data-ttu-id="0e080-102">PresentationOptions:Freeze 特性</span><span class="sxs-lookup"><span data-stu-id="0e080-102">PresentationOptions:Freeze Attribute</span></span>
<span data-ttu-id="0e080-103">将包含`true` <xref:System.Windows.Freezable.IsFrozen%2A> 元素的<xref:System.Windows.Freezable>状态设置为。</span><span class="sxs-lookup"><span data-stu-id="0e080-103">Sets the <xref:System.Windows.Freezable.IsFrozen%2A> state to `true` on the containing <xref:System.Windows.Freezable> element.</span></span> <span data-ttu-id="0e080-104">如果<xref:System.Windows.Freezable>未指定属性<xref:System.Windows.Freezable.IsFrozen%2A>，则的默认行为<xref:System.Windows.Freezable> 是在加载时，并且依赖于运行时的常规行为。`false` `PresentationOptions:Freeze`</span><span class="sxs-lookup"><span data-stu-id="0e080-104">Default behavior for a <xref:System.Windows.Freezable> without the `PresentationOptions:Freeze` attribute specified is that <xref:System.Windows.Freezable.IsFrozen%2A> is `false` at load time, and dependent on general <xref:System.Windows.Freezable> behavior at runtime.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="0e080-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="0e080-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="0e080-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="0e080-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`PresentationOptions`|<span data-ttu-id="0e080-107">XML 命名空间前缀，可以是每个 XML 1.0 规范的任何有效的前缀字符串。</span><span class="sxs-lookup"><span data-stu-id="0e080-107">An XML namespace prefix, which can be any valid prefix string, per the XML 1.0 specification.</span></span> <span data-ttu-id="0e080-108">在本`PresentationOptions`文档中，前缀用于标识目的。</span><span class="sxs-lookup"><span data-stu-id="0e080-108">The prefix `PresentationOptions` is used for identification purposes in this documentation.</span></span>|  
|`freezableElement`|<span data-ttu-id="0e080-109">一个实例化的任何派生类的<xref:System.Windows.Freezable>元素。</span><span class="sxs-lookup"><span data-stu-id="0e080-109">An element that instantiates any derived class of <xref:System.Windows.Freezable>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e080-110">备注</span><span class="sxs-lookup"><span data-stu-id="0e080-110">Remarks</span></span>  
 <span data-ttu-id="0e080-111">`Freeze`特性是`http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`在 XML 命名空间中定义的唯一特性或其他编程元素。</span><span class="sxs-lookup"><span data-stu-id="0e080-111">The `Freeze` attribute is the only attribute or other programming element defined in the `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML namespace.</span></span> <span data-ttu-id="0e080-112">此特殊命名空间中存在 `Freeze` 属性，因此可将其指定为可忽略，并使用[mc：可忽略属性](mc-ignorable-attribute.md)作为根元素声明的一部分。</span><span class="sxs-lookup"><span data-stu-id="0e080-112">The `Freeze` attribute exists in this special namespace specifically so that it can be designated as ignorable, using [mc:Ignorable Attribute](mc-ignorable-attribute.md) as part of the root element declarations.</span></span> <span data-ttu-id="0e080-113">`Freeze`必须能够被忽略的原因是，并非所有[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器实现<xref:System.Windows.Freezable>都能够在加载时冻结[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ; 此功能不是规范的组成部分。</span><span class="sxs-lookup"><span data-stu-id="0e080-113">The reason that `Freeze` must be able to be ignorable is because not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementations are able to freeze a <xref:System.Windows.Freezable> at load time; this capability is not part of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specification.</span></span>  
  
 <span data-ttu-id="0e080-114">处理`Freeze`属性的功能专门内置[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]于处理[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]已编译应用程序的处理器。</span><span class="sxs-lookup"><span data-stu-id="0e080-114">The ability to process the `Freeze` attribute is specifically built in to the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor that processes [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for compiled applications.</span></span> <span data-ttu-id="0e080-115">任何类都不支持该特性，且特性语法不可扩展或可修改。</span><span class="sxs-lookup"><span data-stu-id="0e080-115">The attribute is not supported by any class, and the attribute syntax is not extensible or modifiable.</span></span> <span data-ttu-id="0e080-116">如果要实现[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]自己的处理器，可以选择在加载时并行处理元素上<xref:System.Windows.Freezable>的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] `Freeze`属性时，并行处理[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器的冻结行为。</span><span class="sxs-lookup"><span data-stu-id="0e080-116">If you are implementing your own [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor you can choose to parallel the freezing behavior of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor when processing the `Freeze` attribute on <xref:System.Windows.Freezable> elements at load time.</span></span>  
  
 <span data-ttu-id="0e080-117">`Freeze` 除`true` （不区分大小写）以外的其他属性值将生成加载时错误。</span><span class="sxs-lookup"><span data-stu-id="0e080-117">Any value for the `Freeze` attribute other than `true` (not case sensitive) generates a load time error.</span></span> <span data-ttu-id="0e080-118">（将`Freeze`属性指定为`false`不是错误，但这已是默认值，因此，将设置`false`为不执行任何操作）。</span><span class="sxs-lookup"><span data-stu-id="0e080-118">(Specifying the `Freeze` attribute as `false` is not an error, but that is already the default, so setting to `false` does nothing).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e080-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e080-119">See also</span></span>

- <xref:System.Windows.Freezable>
- [<span data-ttu-id="0e080-120">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="0e080-120">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="0e080-121">mc:Ignorable 特性</span><span class="sxs-lookup"><span data-stu-id="0e080-121">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
