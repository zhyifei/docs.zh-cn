---
title: 如何：定义和引用资源
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: e33c86b03d8b18113f3a15b3ab251753958ff5b2
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646508"
---
# <a name="how-to-define-and-reference-a-resource"></a><span data-ttu-id="09434-102">如何：定义和引用资源</span><span class="sxs-lookup"><span data-stu-id="09434-102">How to: Define and Reference a Resource</span></span>

<span data-ttu-id="09434-103">此示例演示如何使用 中[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]的属性定义资源并引用它。</span><span class="sxs-lookup"><span data-stu-id="09434-103">This example shows how to define a resource and reference it by using an attribute in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>

## <a name="example"></a><span data-ttu-id="09434-104">示例</span><span class="sxs-lookup"><span data-stu-id="09434-104">Example</span></span>

<span data-ttu-id="09434-105">下面的示例定义了两种类型的资源：一种<xref:System.Windows.Media.SolidColorBrush>资源和多个<xref:System.Windows.Style>资源。</span><span class="sxs-lookup"><span data-stu-id="09434-105">The following example defines two types of resources: a <xref:System.Windows.Media.SolidColorBrush> resource, and several <xref:System.Windows.Style> resources.</span></span> <span data-ttu-id="09434-106">该<xref:System.Windows.Media.SolidColorBrush>资源`MyBrush`用于提供每个属性的值，每个属性都采用类型<xref:System.Windows.Media.Brush>值。</span><span class="sxs-lookup"><span data-stu-id="09434-106">The <xref:System.Windows.Media.SolidColorBrush> resource `MyBrush` is used to provide the value of several properties that each take a <xref:System.Windows.Media.Brush> type value.</span></span> <span data-ttu-id="09434-107">资源和<xref:System.Windows.Style>`PageBackground``TitleText`每个目标为特定的控件`Label`类型。</span><span class="sxs-lookup"><span data-stu-id="09434-107">The <xref:System.Windows.Style> resources `PageBackground`, `TitleText` and `Label` each target a particular control type.</span></span> <span data-ttu-id="09434-108">当资源键引用该样式资源并用于设置 中<xref:System.Windows.FrameworkElement.Style%2A>[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]定义的多个特定控件元素的属性时，样式在目标控件上设置各种不同的属性。</span><span class="sxs-lookup"><span data-stu-id="09434-108">The styles set a variety of different properties on the targeted controls, when that style resource is referenced by resource key and is used to set the <xref:System.Windows.FrameworkElement.Style%2A> property of several specific control elements defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>

<span data-ttu-id="09434-109">请注意，`Label`样式的 setter 中的一个属性也引用前面定义的`MyBrush`资源。</span><span class="sxs-lookup"><span data-stu-id="09434-109">Note that one of the properties within the setters of the `Label` style also references the `MyBrush` resource defined earlier.</span></span> <span data-ttu-id="09434-110">这是一种常见的技术，但请务必记住，资源按给定顺序解析并输入到资源字典中。</span><span class="sxs-lookup"><span data-stu-id="09434-110">This is a common technique, but it is important to remember that resources are parsed and entered into a resource dictionary in the order that they are given.</span></span> <span data-ttu-id="09434-111">如果使用[静态资源标记扩展](staticresource-markup-extension.md)从其他资源中引用资源，则字典中找到的顺序也会请求资源。</span><span class="sxs-lookup"><span data-stu-id="09434-111">Resources are also requested by the order found within the dictionary if you use the [StaticResource Markup Extension](staticresource-markup-extension.md) to reference them from within another resource.</span></span> <span data-ttu-id="09434-112">确保引用的任何资源在资源集合中定义的任何资源都早于请求该资源的位置。</span><span class="sxs-lookup"><span data-stu-id="09434-112">Make sure that any resource that you reference is defined earlier within the resources collection than where that resource is then requested.</span></span> <span data-ttu-id="09434-113">如有必要，可以使用[动态资源标记扩展](dynamicresource-markup-extension.md)在运行时引用资源，从而绕过资源引用的严格创建顺序，但您应该知道此动态资源技术具有性能后果。</span><span class="sxs-lookup"><span data-stu-id="09434-113">If necessary, you can work around the strict creation order of resource references by using a [DynamicResource Markup Extension](dynamicresource-markup-extension.md) to reference the resource at runtime instead, but you should be aware that this DynamicResource technique has performance consequences.</span></span> <span data-ttu-id="09434-114">有关详细信息，请参阅[XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。</span><span class="sxs-lookup"><span data-stu-id="09434-114">For details, see [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

[!code-xaml[FEResource#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]

## <a name="see-also"></a><span data-ttu-id="09434-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09434-115">See also</span></span>

- [<span data-ttu-id="09434-116">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="09434-116">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="09434-117">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="09434-117">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
