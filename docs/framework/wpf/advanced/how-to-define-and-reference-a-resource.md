---
title: "如何：定义和引用资源"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 322ac3e5ebfe2d820a4711d877396b9a1a2759a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-and-reference-a-resource"></a><span data-ttu-id="02d42-102">如何：定义和引用资源</span><span class="sxs-lookup"><span data-stu-id="02d42-102">How to: Define and Reference a Resource</span></span>
<span data-ttu-id="02d42-103">此示例演示如何定义资源，通过使用中的属性引用该[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="02d42-103">This example shows how to define a resource and reference it by using an attribute in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="02d42-104">示例</span><span class="sxs-lookup"><span data-stu-id="02d42-104">Example</span></span>  
 <span data-ttu-id="02d42-105">下面的示例定义两种类型的资源：<xref:System.Windows.Media.SolidColorBrush>资源，并在几个<xref:System.Windows.Style>资源。</span><span class="sxs-lookup"><span data-stu-id="02d42-105">The following example defines two types of resources: a <xref:System.Windows.Media.SolidColorBrush> resource, and several <xref:System.Windows.Style> resources.</span></span> <span data-ttu-id="02d42-106"><xref:System.Windows.Media.SolidColorBrush>资源`MyBrush`用来提供多个属性的值在每个都采用<xref:System.Windows.Media.Brush>键入值。</span><span class="sxs-lookup"><span data-stu-id="02d42-106">The <xref:System.Windows.Media.SolidColorBrush> resource `MyBrush` is used to provide the value of several properties that each take a <xref:System.Windows.Media.Brush> type value.</span></span> <span data-ttu-id="02d42-107"><xref:System.Windows.Style>资源`PageBackground`，`TitleText`和`Label`每面向特定控件类型。</span><span class="sxs-lookup"><span data-stu-id="02d42-107">The <xref:System.Windows.Style> resources `PageBackground`, `TitleText` and `Label` each target a particular control type.</span></span> <span data-ttu-id="02d42-108">样式目标控件上设置多个不同的属性，该样式资源由资源键引用，以及用于设置<xref:System.Windows.FrameworkElement.Style%2A>属性中定义的几个特定的控件元素[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="02d42-108">The styles set a variety of different properties on the targeted controls, when that style resource is referenced by resource key and is used to set the <xref:System.Windows.FrameworkElement.Style%2A> property of several specific control elements defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="02d42-109">第一个属性的 setter 中注意`Label`样式也引用`MyBrush`前面定义的资源。</span><span class="sxs-lookup"><span data-stu-id="02d42-109">Note that one of the properties within the setters of the `Label` style also references the `MyBrush` resource defined earlier.</span></span> <span data-ttu-id="02d42-110">这是一种常用技术，但务必记住，资源是分析，并输入到的资源字典中，系统会提供的顺序。</span><span class="sxs-lookup"><span data-stu-id="02d42-110">This is a common technique, but it is important to remember that resources are parsed and entered into a resource dictionary in the order that they are given.</span></span> <span data-ttu-id="02d42-111">如果你使用在字典中找到的顺序也所请求资源[否则标记扩展](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)引用它们从另一个资源中。</span><span class="sxs-lookup"><span data-stu-id="02d42-111">Resources are also requested by the order found within the dictionary if you use the [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) to reference them from within another resource.</span></span> <span data-ttu-id="02d42-112">请确保你引用任何资源比然后请求该资源时资源集合中之前定义。</span><span class="sxs-lookup"><span data-stu-id="02d42-112">Make sure that any resource that you reference is defined earlier within the resources collection than where that resource is then requested.</span></span> <span data-ttu-id="02d42-113">如果有必要，你可以解决资源这样的严格的创建顺序使用[DynamicResource 标记扩展](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)可以引用在运行时该资源，相反，但你应注意，此 DynamicResource技术对性能产生影响。</span><span class="sxs-lookup"><span data-stu-id="02d42-113">If necessary, you can work around the strict creation order of resource refererences by using a [DynamicResource Markup Extension](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) to reference the resource at runtime instead, but you should be aware that this DynamicResource technique has performance consequences.</span></span> <span data-ttu-id="02d42-114">有关详细信息，请参阅[XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="02d42-114">For details, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
 [!code-xaml[FEResource#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]  
  
## <a name="see-also"></a><span data-ttu-id="02d42-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02d42-115">See Also</span></span>  
 [<span data-ttu-id="02d42-116">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="02d42-116">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="02d42-117">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="02d42-117">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
