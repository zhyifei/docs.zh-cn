---
title: "PresentationOptions:Freeze 特性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d8f1a876f65941afb159d4c3d8904ab4426d9177
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="presentationoptionsfreeze-attribute"></a><span data-ttu-id="c269f-102">PresentationOptions:Freeze 特性</span><span class="sxs-lookup"><span data-stu-id="c269f-102">PresentationOptions:Freeze Attribute</span></span>
<span data-ttu-id="c269f-103">集<xref:System.Windows.Freezable.IsFrozen%2A>状态`true`上包含<xref:System.Windows.Freezable>元素。</span><span class="sxs-lookup"><span data-stu-id="c269f-103">Sets the <xref:System.Windows.Freezable.IsFrozen%2A> state to `true` on the containing <xref:System.Windows.Freezable> element.</span></span> <span data-ttu-id="c269f-104">默认行为<xref:System.Windows.Freezable>而无需`PresentationOptions:Freeze`指定的属性是<xref:System.Windows.Freezable.IsFrozen%2A>是`false`加载时间和依赖于一般<xref:System.Windows.Freezable>在运行时的行为。</span><span class="sxs-lookup"><span data-stu-id="c269f-104">Default behavior for a <xref:System.Windows.Freezable> without the `PresentationOptions:Freeze` attribute specified is that <xref:System.Windows.Freezable.IsFrozen%2A> is `false` at load time, and dependent on general <xref:System.Windows.Freezable> behavior at runtime.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="c269f-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="c269f-105">XAML Attribute Usage</span></span>  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="c269f-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="c269f-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`PresentationOptions`|<span data-ttu-id="c269f-107">XML 命名空间前缀，这可以是任何有效的前缀字符串，根据 XML 1.0 规范。</span><span class="sxs-lookup"><span data-stu-id="c269f-107">An XML namespace prefix, which can be any valid prefix string, per the XML 1.0 specification.</span></span> <span data-ttu-id="c269f-108">前缀`PresentationOptions`用于本文档中的标识目的。</span><span class="sxs-lookup"><span data-stu-id="c269f-108">The prefix `PresentationOptions` is used for identification purposes in this documentation.</span></span>|  
|`freezableElement`|<span data-ttu-id="c269f-109">实例化任何元素派生的类<xref:System.Windows.Freezable>。</span><span class="sxs-lookup"><span data-stu-id="c269f-109">An element that instantiates any derived class of <xref:System.Windows.Freezable>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c269f-110">备注</span><span class="sxs-lookup"><span data-stu-id="c269f-110">Remarks</span></span>  
 <span data-ttu-id="c269f-111">`Freeze`属性是唯一的属性或其他编程元素中定义`http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="c269f-111">The `Freeze` attribute is the only attribute or other programming element defined in the `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML namespace.</span></span> <span data-ttu-id="c269f-112">`Freeze`属性存在此特殊的命名空间中，具体而言，以便可以将其指定为可忽略，使用[mc： 可忽略属性](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)作为根元素声明的一部分。</span><span class="sxs-lookup"><span data-stu-id="c269f-112">The `Freeze` attribute exists in this special namespace specifically so that it can be designated as ignorable, using [mc:Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) as part of the root element declarations.</span></span> <span data-ttu-id="c269f-113">原因，`Freeze`必须能够可忽略是因为并非所有[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器实现都能冻结<xref:System.Windows.Freezable>在加载时; 此功能不属于[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]规范。</span><span class="sxs-lookup"><span data-stu-id="c269f-113">The reason that `Freeze` must be able to be ignorable is because not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementations are able to freeze a <xref:System.Windows.Freezable> at load time; this capability is not part of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specification.</span></span>  
  
 <span data-ttu-id="c269f-114">处理的能力`Freeze`属性专门内置于[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理的处理器[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]为编译的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c269f-114">The ability to process the `Freeze` attribute is specifically built in to the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor that processes [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for compiled applications.</span></span> <span data-ttu-id="c269f-115">不支持的任何类的特性和特性语法不是扩展，也可修改。</span><span class="sxs-lookup"><span data-stu-id="c269f-115">The attribute is not supported by any class, and the attribute syntax is not extensible or modifiable.</span></span> <span data-ttu-id="c269f-116">如果你要实现您自己[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器你可以选择的并行的冻结行为[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器在处理时`Freeze`属性<xref:System.Windows.Freezable>在加载时的元素。</span><span class="sxs-lookup"><span data-stu-id="c269f-116">If you are implementing your own [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor you can choose to parallel the freezing behavior of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor when processing the `Freeze` attribute on <xref:System.Windows.Freezable> elements at load time.</span></span>  
  
 <span data-ttu-id="c269f-117">任何值`Freeze`特性，除`true`（不区分大小写） 生成加载时错误。</span><span class="sxs-lookup"><span data-stu-id="c269f-117">Any value for the `Freeze` attribute other than `true` (not case sensitive) generates a load time error.</span></span> <span data-ttu-id="c269f-118">(指定`Freeze`属性为`false`不是一个错误，但这已是默认值，因此将设置为`false`不执行任何操作)。</span><span class="sxs-lookup"><span data-stu-id="c269f-118">(Specifying the `Freeze` attribute as `false` is not an error, but that is already the default, so setting to `false` does nothing).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c269f-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c269f-119">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 [<span data-ttu-id="c269f-120">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="c269f-120">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="c269f-121">mc:Ignorable 特性</span><span class="sxs-lookup"><span data-stu-id="c269f-121">mc:Ignorable Attribute</span></span>](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)
