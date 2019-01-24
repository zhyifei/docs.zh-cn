---
title: 如何：定义和引用资源
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: 39cde252ce98e55f155edfb7a4c2268219d6858e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692868"
---
# <a name="how-to-define-and-reference-a-resource"></a><span data-ttu-id="e3ad5-102">如何：定义和引用资源</span><span class="sxs-lookup"><span data-stu-id="e3ad5-102">How to: Define and Reference a Resource</span></span>
<span data-ttu-id="e3ad5-103">此示例演示如何定义资源，通过使用中的一个属性引用该[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e3ad5-103">This example shows how to define a resource and reference it by using an attribute in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3ad5-104">示例</span><span class="sxs-lookup"><span data-stu-id="e3ad5-104">Example</span></span>  
 <span data-ttu-id="e3ad5-105">下面的示例定义两种类型的资源：<xref:System.Windows.Media.SolidColorBrush>资源和多个<xref:System.Windows.Style>资源。</span><span class="sxs-lookup"><span data-stu-id="e3ad5-105">The following example defines two types of resources: a <xref:System.Windows.Media.SolidColorBrush> resource, and several <xref:System.Windows.Style> resources.</span></span> <span data-ttu-id="e3ad5-106"><xref:System.Windows.Media.SolidColorBrush>资源`MyBrush`用于提供多个属性的值，每个需要<xref:System.Windows.Media.Brush>键入值。</span><span class="sxs-lookup"><span data-stu-id="e3ad5-106">The <xref:System.Windows.Media.SolidColorBrush> resource `MyBrush` is used to provide the value of several properties that each take a <xref:System.Windows.Media.Brush> type value.</span></span> <span data-ttu-id="e3ad5-107"><xref:System.Windows.Style>资源`PageBackground`，`TitleText`和`Label`每个目标特定控件类型。</span><span class="sxs-lookup"><span data-stu-id="e3ad5-107">The <xref:System.Windows.Style> resources `PageBackground`, `TitleText` and `Label` each target a particular control type.</span></span> <span data-ttu-id="e3ad5-108">样式时设置的各种不同的属性上的目标控件，该样式资源引用的资源键，用于设置<xref:System.Windows.FrameworkElement.Style%2A>属性中定义的多个特定的控件元素[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e3ad5-108">The styles set a variety of different properties on the targeted controls, when that style resource is referenced by resource key and is used to set the <xref:System.Windows.FrameworkElement.Style%2A> property of several specific control elements defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="e3ad5-109">第一个属性的 setter 中注意`Label`样式也引用`MyBrush`前面定义的资源。</span><span class="sxs-lookup"><span data-stu-id="e3ad5-109">Note that one of the properties within the setters of the `Label` style also references the `MyBrush` resource defined earlier.</span></span> <span data-ttu-id="e3ad5-110">这是一种常用技术，但请务必记住，资源是分析，并输入到的资源字典中，系统将提供的顺序。</span><span class="sxs-lookup"><span data-stu-id="e3ad5-110">This is a common technique, but it is important to remember that resources are parsed and entered into a resource dictionary in the order that they are given.</span></span> <span data-ttu-id="e3ad5-111">如果使用的字典中找到的顺序也请求资源[StaticResource 标记扩展](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)另一个资源中引用它们。</span><span class="sxs-lookup"><span data-stu-id="e3ad5-111">Resources are also requested by the order found within the dictionary if you use the [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) to reference them from within another resource.</span></span> <span data-ttu-id="e3ad5-112">请确保你引用的任何资源比然后请求该资源所在的资源集合中之前定义。</span><span class="sxs-lookup"><span data-stu-id="e3ad5-112">Make sure that any resource that you reference is defined earlier within the resources collection than where that resource is then requested.</span></span> <span data-ttu-id="e3ad5-113">如果有必要，您可以解决资源这样的严格的创建顺序通过使用[DynamicResource 标记扩展](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)相反，引用在运行时的资源，但应注意，此 DynamicResource方法对性能产生影响。</span><span class="sxs-lookup"><span data-stu-id="e3ad5-113">If necessary, you can work around the strict creation order of resource refererences by using a [DynamicResource Markup Extension](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) to reference the resource at runtime instead, but you should be aware that this DynamicResource technique has performance consequences.</span></span> <span data-ttu-id="e3ad5-114">有关详细信息，请参阅[XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="e3ad5-114">For details, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
 [!code-xaml[FEResource#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]  
  
## <a name="see-also"></a><span data-ttu-id="e3ad5-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3ad5-115">See also</span></span>
- [<span data-ttu-id="e3ad5-116">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="e3ad5-116">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)
- [<span data-ttu-id="e3ad5-117">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="e3ad5-117">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
