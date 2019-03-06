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
ms.openlocfilehash: 03ffec87c98c88452aa8fde89c64646eaf48a8da
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369586"
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a><span data-ttu-id="e447c-102">如何：为依赖项属性添加所有者类型</span><span class="sxs-lookup"><span data-stu-id="e447c-102">How to: Add an Owner Type for a Dependency Property</span></span>
<span data-ttu-id="e447c-103">此示例演示如何将类添加为所有者为不同类型注册依赖属性。</span><span class="sxs-lookup"><span data-stu-id="e447c-103">This example shows how to add a class as an owner of a dependency property registered for a different type.</span></span> <span data-ttu-id="e447c-104">通过执行此操作，请[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]读取器和属性系统都能够识别此类为附加属性的所有者。</span><span class="sxs-lookup"><span data-stu-id="e447c-104">By doing this, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader and property system are both able to recognize the class as an additional owner of the property.</span></span> <span data-ttu-id="e447c-105">（可选） 将添加为所有者可以选择添加类以提供特定于类型的元数据。</span><span class="sxs-lookup"><span data-stu-id="e447c-105">Adding as owner optionally allows the adding class to provide type-specific metadata.</span></span>  
  
 <span data-ttu-id="e447c-106">在以下示例中，`StateProperty`通过注册一个属性`MyStateControl`类。</span><span class="sxs-lookup"><span data-stu-id="e447c-106">In the following example, `StateProperty` is a property registered by the `MyStateControl` class.</span></span> <span data-ttu-id="e447c-107">该类`UnrelatedStateControl`将自身添加为所有者`StateProperty`使用<xref:System.Windows.DependencyProperty.AddOwner%2A>方法，特别使用它位于添加类型上允许进行新的依赖项属性的元数据的签名。</span><span class="sxs-lookup"><span data-stu-id="e447c-107">The class `UnrelatedStateControl` adds itself as an owner of the `StateProperty` using the <xref:System.Windows.DependencyProperty.AddOwner%2A> method, specifically using the signature that allows for new metadata for the dependency property as it exists on the adding type.</span></span> <span data-ttu-id="e447c-108">请注意，应提供[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]中所示的示例类似的属性的访问器[实现依赖属性](how-to-implement-a-dependency-property.md)示例中，以及重新公开要添加的类上的依赖项属性标识符作为所有者。</span><span class="sxs-lookup"><span data-stu-id="e447c-108">Notice that you should provide [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] accessors for the property similar to the example shown in the [Implement a Dependency Property](how-to-implement-a-dependency-property.md) example, as well as re-expose the dependency property identifier on the class being added as owner.</span></span>  
  
 <span data-ttu-id="e447c-109">未使用包装，依赖项属性仍将从以编程方式访问使用的角度来看有效<xref:System.Windows.DependencyObject.GetValue%2A>或<xref:System.Windows.DependencyObject.SetValue%2A>。</span><span class="sxs-lookup"><span data-stu-id="e447c-109">Without wrappers, the dependency property would still work from the perspective of programmatic access using <xref:System.Windows.DependencyObject.GetValue%2A> or <xref:System.Windows.DependencyObject.SetValue%2A>.</span></span> <span data-ttu-id="e447c-110">但你通常想要使用此属性系统行为的并行[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]属性包装器。</span><span class="sxs-lookup"><span data-stu-id="e447c-110">But you typically want to parallel this property-system behavior with the [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] property wrappers.</span></span> <span data-ttu-id="e447c-111">这些包装更加轻松地以编程方式设置依赖项属性，使其可以将设置为属性[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]属性。</span><span class="sxs-lookup"><span data-stu-id="e447c-111">The wrappers make it easier to set the dependency property programmatically, and make it possible to set the properties as [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributes.</span></span>  
  
 <span data-ttu-id="e447c-112">若要了解如何重写默认元数据，请参阅[重写依赖属性的元数据](how-to-override-metadata-for-a-dependency-property.md)。</span><span class="sxs-lookup"><span data-stu-id="e447c-112">To find out how to override default metadata, see [Override Metadata for a Dependency Property](how-to-override-metadata-for-a-dependency-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e447c-113">示例</span><span class="sxs-lookup"><span data-stu-id="e447c-113">Example</span></span>  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a><span data-ttu-id="e447c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e447c-114">See also</span></span>
- [<span data-ttu-id="e447c-115">自定义依赖属性</span><span class="sxs-lookup"><span data-stu-id="e447c-115">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
- [<span data-ttu-id="e447c-116">依赖项属性概述</span><span class="sxs-lookup"><span data-stu-id="e447c-116">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
