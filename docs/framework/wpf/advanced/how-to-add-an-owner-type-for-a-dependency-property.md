---
title: 如何：为依赖项属性添加所有者类型
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
ms.openlocfilehash: bf3f73743d1c76145bf520ed859c27c4d3aaf662
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542771"
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a><span data-ttu-id="f267a-102">如何：为依赖项属性添加所有者类型</span><span class="sxs-lookup"><span data-stu-id="f267a-102">How to: Add an Owner Type for a Dependency Property</span></span>
<span data-ttu-id="f267a-103">此示例演示如何作为为不同类型注册依赖属性所有者添加类。</span><span class="sxs-lookup"><span data-stu-id="f267a-103">This example shows how to add a class as an owner of a dependency property registered for a different type.</span></span> <span data-ttu-id="f267a-104">通过执行此操作，请[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]读取器和属性系统都能够识别类作为其他所有者的属性。</span><span class="sxs-lookup"><span data-stu-id="f267a-104">By doing this, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader and property system are both able to recognize the class as an additional owner of the property.</span></span> <span data-ttu-id="f267a-105">（可选） 添加作为所有者可以选择添加类以提供特定类型的元数据。</span><span class="sxs-lookup"><span data-stu-id="f267a-105">Adding as owner optionally allows the adding class to provide type-specific metadata.</span></span>  
  
 <span data-ttu-id="f267a-106">在下面的示例中，`StateProperty`属性由就注册`MyStateControl`类。</span><span class="sxs-lookup"><span data-stu-id="f267a-106">In the following example, `StateProperty` is a property registered by the `MyStateControl` class.</span></span> <span data-ttu-id="f267a-107">类`UnrelatedStateControl`其自身添加的所有者为`StateProperty`使用<xref:System.Windows.DependencyProperty.AddOwner%2A>专门使用的签名，以便新的依赖项属性的元数据，因为它存在于添加类型的方法。</span><span class="sxs-lookup"><span data-stu-id="f267a-107">The class `UnrelatedStateControl` adds itself as an owner of the `StateProperty` using the <xref:System.Windows.DependencyProperty.AddOwner%2A> method, specifically using the signature that allows for new metadata for the dependency property as it exists on the adding type.</span></span> <span data-ttu-id="f267a-108">请注意，应提供[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]类似于示例中所示的属性的访问器[实现一个依赖项属性](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md)示例中，以及重新公开要添加的类上的依赖项属性标识符作为所有者。</span><span class="sxs-lookup"><span data-stu-id="f267a-108">Notice that you should provide [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] accessors for the property similar to the example shown in the [Implement a Dependency Property](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) example, as well as re-expose the dependency property identifier on the class being added as owner.</span></span>  
  
 <span data-ttu-id="f267a-109">如果没有包装器，依赖项属性将仍正常工作的以编程方式访问使用角度<xref:System.Windows.DependencyObject.GetValue%2A>或<xref:System.Windows.DependencyObject.SetValue%2A>。</span><span class="sxs-lookup"><span data-stu-id="f267a-109">Without wrappers, the dependency property would still work from the perspective of programmatic access using <xref:System.Windows.DependencyObject.GetValue%2A> or <xref:System.Windows.DependencyObject.SetValue%2A>.</span></span> <span data-ttu-id="f267a-110">但你通常想要使用此属性系统的行为的并行[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]属性包装器。</span><span class="sxs-lookup"><span data-stu-id="f267a-110">But you typically want to parallel this property-system behavior with the [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] property wrappers.</span></span> <span data-ttu-id="f267a-111">此包装器更加轻松地设置依赖项属性以编程方式，并使其可以设置属性为[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]属性。</span><span class="sxs-lookup"><span data-stu-id="f267a-111">The wrappers make it easier to set the dependency property programmatically, and make it possible to set the properties as [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributes.</span></span>  
  
 <span data-ttu-id="f267a-112">若要了解如何重写默认元数据，请参阅[重写依赖项属性的元数据](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md)。</span><span class="sxs-lookup"><span data-stu-id="f267a-112">To find out how to override default metadata, see [Override Metadata for a Dependency Property](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f267a-113">示例</span><span class="sxs-lookup"><span data-stu-id="f267a-113">Example</span></span>  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a><span data-ttu-id="f267a-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="f267a-114">See Also</span></span>  
 [<span data-ttu-id="f267a-115">自定义依赖属性</span><span class="sxs-lookup"><span data-stu-id="f267a-115">Custom Dependency Properties</span></span>](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [<span data-ttu-id="f267a-116">依赖项属性概述</span><span class="sxs-lookup"><span data-stu-id="f267a-116">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
