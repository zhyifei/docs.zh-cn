---
title: 如何：添加依赖属性的所有者类型
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
ms.openlocfilehash: 5ddc85d159b4bf81751428c13c234c5e53be8ad4
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401130"
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a><span data-ttu-id="7c22d-102">如何：添加依赖属性的所有者类型</span><span class="sxs-lookup"><span data-stu-id="7c22d-102">How to: Add an Owner Type for a Dependency Property</span></span>
<span data-ttu-id="7c22d-103">此示例演示如何将类添加为为不同类型注册的依赖项属性的所有者。</span><span class="sxs-lookup"><span data-stu-id="7c22d-103">This example shows how to add a class as an owner of a dependency property registered for a different type.</span></span> <span data-ttu-id="7c22d-104">通过执行此操作, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]读取器和属性系统都能将该类识别为属性的其他所有者。</span><span class="sxs-lookup"><span data-stu-id="7c22d-104">By doing this, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader and property system are both able to recognize the class as an additional owner of the property.</span></span> <span data-ttu-id="7c22d-105">添加为所有者可以选择允许添加类提供特定于类型的元数据。</span><span class="sxs-lookup"><span data-stu-id="7c22d-105">Adding as owner optionally allows the adding class to provide type-specific metadata.</span></span>  
  
 <span data-ttu-id="7c22d-106">在下面的示例中`StateProperty` , 是`MyStateControl`由类注册的属性。</span><span class="sxs-lookup"><span data-stu-id="7c22d-106">In the following example, `StateProperty` is a property registered by the `MyStateControl` class.</span></span> <span data-ttu-id="7c22d-107">类`UnrelatedStateControl` `StateProperty`使用方法<xref:System.Windows.DependencyProperty.AddOwner%2A>将自身添加为的所有者, 特别是使用签名, 该签名允许依赖项属性的新元数据, 因为它存在于添加类型中。</span><span class="sxs-lookup"><span data-stu-id="7c22d-107">The class `UnrelatedStateControl` adds itself as an owner of the `StateProperty` using the <xref:System.Windows.DependencyProperty.AddOwner%2A> method, specifically using the signature that allows for new metadata for the dependency property as it exists on the adding type.</span></span> <span data-ttu-id="7c22d-108">请注意, 应为属性提供公共语言运行时 (CLR) 访问器, 与[实现依赖项属性](how-to-implement-a-dependency-property.md)示例中所示的示例类似, 并重新公开作为所有者添加的类的依赖项属性标识符。</span><span class="sxs-lookup"><span data-stu-id="7c22d-108">Notice that you should provide common language runtime (CLR) accessors for the property similar to the example shown in the [Implement a Dependency Property](how-to-implement-a-dependency-property.md) example, as well as re-expose the dependency property identifier on the class being added as owner.</span></span>  
  
 <span data-ttu-id="7c22d-109">如果不使用包装, 依赖属性仍将从使用<xref:System.Windows.DependencyObject.GetValue%2A>或<xref:System.Windows.DependencyObject.SetValue%2A>的编程访问角度来处理。</span><span class="sxs-lookup"><span data-stu-id="7c22d-109">Without wrappers, the dependency property would still work from the perspective of programmatic access using <xref:System.Windows.DependencyObject.GetValue%2A> or <xref:System.Windows.DependencyObject.SetValue%2A>.</span></span> <span data-ttu-id="7c22d-110">但是, 您通常需要将此属性系统行为与 CLR 属性包装器进行并行处理。</span><span class="sxs-lookup"><span data-stu-id="7c22d-110">But you typically want to parallel this property-system behavior with the CLR property wrappers.</span></span> <span data-ttu-id="7c22d-111">利用这些包装, 可以以编程方式轻松设置依赖属性, 并可以将属性设置为[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]属性。</span><span class="sxs-lookup"><span data-stu-id="7c22d-111">The wrappers make it easier to set the dependency property programmatically, and make it possible to set the properties as [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributes.</span></span>  
  
 <span data-ttu-id="7c22d-112">若要了解如何重写默认元数据, 请参阅[重写依赖属性的元数据](how-to-override-metadata-for-a-dependency-property.md)。</span><span class="sxs-lookup"><span data-stu-id="7c22d-112">To find out how to override default metadata, see [Override Metadata for a Dependency Property](how-to-override-metadata-for-a-dependency-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c22d-113">示例</span><span class="sxs-lookup"><span data-stu-id="7c22d-113">Example</span></span>  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a><span data-ttu-id="7c22d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c22d-114">See also</span></span>

- [<span data-ttu-id="7c22d-115">自定义依赖属性</span><span class="sxs-lookup"><span data-stu-id="7c22d-115">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
- [<span data-ttu-id="7c22d-116">依赖项属性概述</span><span class="sxs-lookup"><span data-stu-id="7c22d-116">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
