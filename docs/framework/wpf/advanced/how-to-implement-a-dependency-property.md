---
title: 如何：实现依赖属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: e2f18cb3941be2ebf4315a844c05b91ff49c6aa2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757451"
---
# <a name="how-to-implement-a-dependency-property"></a><span data-ttu-id="4ea5f-102">如何：实现依赖属性</span><span class="sxs-lookup"><span data-stu-id="4ea5f-102">How to: Implement a Dependency Property</span></span>
<span data-ttu-id="4ea5f-103">此示例演示如何重新[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]具有属性<xref:System.Windows.DependencyProperty>字段，从而定义依赖项属性。</span><span class="sxs-lookup"><span data-stu-id="4ea5f-103">This example shows how to back a [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] property with a <xref:System.Windows.DependencyProperty> field, thus defining a dependency property.</span></span> <span data-ttu-id="4ea5f-104">定义自己的属性并需要其支持 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 功能的诸多方面（包括样式、数据绑定、继承、动画和默认值）时，应将其作为依赖属性实现。</span><span class="sxs-lookup"><span data-stu-id="4ea5f-104">When you define your own properties and want them to support many aspects of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] functionality, including styles, data binding, inheritance, animation, and default values, you should implement them as a dependency property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ea5f-105">示例</span><span class="sxs-lookup"><span data-stu-id="4ea5f-105">Example</span></span>  
 <span data-ttu-id="4ea5f-106">下面的示例第一次注册依赖属性通过调用<xref:System.Windows.DependencyProperty.Register%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="4ea5f-106">The following example first registers a dependency property by calling the <xref:System.Windows.DependencyProperty.Register%2A> method.</span></span> <span data-ttu-id="4ea5f-107">用于存储名称，并且必须依赖项属性的特征的标识符字段的名称<xref:System.Windows.DependencyProperty.Name%2A>作为的一部分为依赖属性选择了<xref:System.Windows.DependencyProperty.Register%2A>调用中，文字字符串由追加`Property`。</span><span class="sxs-lookup"><span data-stu-id="4ea5f-107">The name of the identifier field that you use to store the name and characteristics of the dependency property must be the <xref:System.Windows.DependencyProperty.Name%2A> you chose for the dependency property as part of the <xref:System.Windows.DependencyProperty.Register%2A> call, appended by the literal string `Property`.</span></span> <span data-ttu-id="4ea5f-108">例如，如果你注册具有的依赖关系属性<xref:System.Windows.DependencyProperty.Name%2A>的`Location`，则定义的依赖项属性标识符字段必须命名为`LocationProperty`。</span><span class="sxs-lookup"><span data-stu-id="4ea5f-108">For instance, if you register a dependency property with a <xref:System.Windows.DependencyProperty.Name%2A> of `Location`, then the identifier field that you define for the dependency property must be named `LocationProperty`.</span></span>  
  
 <span data-ttu-id="4ea5f-109">在此示例中，依赖项属性的名称并将其[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]访问器已`State`; 标识符字段`StateProperty`; 属性的类型是<xref:System.Boolean>; 注册依赖属性的类型是`MyStateControl`。</span><span class="sxs-lookup"><span data-stu-id="4ea5f-109">In this example, the name of the dependency property and its [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] accessor is `State`; the identifier field is `StateProperty`; the type of the property is <xref:System.Boolean>; and the type that registers the dependency property is `MyStateControl`.</span></span>  
  
 <span data-ttu-id="4ea5f-110">如果不遵循此命名模式，则设计器可能无法正确地报告属性，而且属性系统样式应用程序的某些方面可能不会以预期的方式工作。</span><span class="sxs-lookup"><span data-stu-id="4ea5f-110">If you fail to follow this naming pattern, designers might not report your property correctly, and certain aspects of property system style application might not behave as expected.</span></span>  
  
 <span data-ttu-id="4ea5f-111">还可为依赖属性指定默认元数据。</span><span class="sxs-lookup"><span data-stu-id="4ea5f-111">You can also specify default metadata for a dependency property.</span></span> <span data-ttu-id="4ea5f-112">此示例将 `State` 依赖属性的默认值注册为 `false`。</span><span class="sxs-lookup"><span data-stu-id="4ea5f-112">This example registers the default value of the `State` dependency property to be `false`.</span></span>  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 <span data-ttu-id="4ea5f-113">若要深入了解实现依赖属性而非仅使用私有字段支持 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 属性的原因及其实现方式，请参阅[依赖属性概述](dependency-properties-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4ea5f-113">For more information about how and why to implement a dependency property, as opposed to just backing a [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] property with a private field, see [Dependency Properties Overview](dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ea5f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ea5f-114">See also</span></span>

- [<span data-ttu-id="4ea5f-115">依赖项属性概述</span><span class="sxs-lookup"><span data-stu-id="4ea5f-115">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="4ea5f-116">帮助主题</span><span class="sxs-lookup"><span data-stu-id="4ea5f-116">How-to Topics</span></span>](properties-how-to-topics.md)
