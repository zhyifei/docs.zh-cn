---
title: "依赖项属性的安全性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wrappers [WPF], access
- wrappers [WPF], security
- dependency properties [WPF], security
- security [WPF], wrappers
- validation [WPF], dependency properties
- dependency properties [WPF], access
- security [WPF], dependency properties
ms.assetid: d10150ec-90c5-4571-8d35-84bafa2429a4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9cd6f9d7025de9f5deb836d48a8ce9c7134973d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="dependency-property-security"></a><span data-ttu-id="80814-102">依赖项属性的安全性</span><span class="sxs-lookup"><span data-stu-id="80814-102">Dependency Property Security</span></span>
<span data-ttu-id="80814-103">依赖属性通常应当被视为公共属性。</span><span class="sxs-lookup"><span data-stu-id="80814-103">Dependency properties should generally be considered to be public properties.</span></span> <span data-ttu-id="80814-104">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 属性系统在本质上无法对依赖属性值提供安全保证。</span><span class="sxs-lookup"><span data-stu-id="80814-104">The nature of the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] property system prevents the ability to make security guarantees about a dependency property value.</span></span>  
  
  
<a name="AccessSecurity"></a>   
## <a name="access-and-security-of-wrappers-and-dependency-properties"></a><span data-ttu-id="80814-105">包装器和依赖属性的访问和安全性</span><span class="sxs-lookup"><span data-stu-id="80814-105">Access and Security of Wrappers and Dependency Properties</span></span>  
 <span data-ttu-id="80814-106">通常，依赖属性是随“包装器”[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 属性一起实现的，这些包装器属性可以简化从实例获取或设置属性的过程。</span><span class="sxs-lookup"><span data-stu-id="80814-106">Typically, dependency properties are implemented along with "wrapper" [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] properties that simplify getting or setting the property from an instance.</span></span> <span data-ttu-id="80814-107">但是，包装实际上只是方便的方法，实现基础<xref:System.Windows.DependencyObject.GetValue%2A>和<xref:System.Windows.DependencyObject.SetValue%2A>交互具有依赖项属性时所使用的静态调用。</span><span class="sxs-lookup"><span data-stu-id="80814-107">But the wrappers are really just convenience methods that implement the underlying <xref:System.Windows.DependencyObject.GetValue%2A> and <xref:System.Windows.DependencyObject.SetValue%2A> static calls that are used when interacting with dependency properties.</span></span> <span data-ttu-id="80814-108">从另外一个角度考虑，这些属性作为恰好由依赖属性（而非私有字段）支持的[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 属性公开。</span><span class="sxs-lookup"><span data-stu-id="80814-108">Thinking of it in another way, the properties are exposed as [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] properties that happen to be backed by a dependency property rather than by a private field.</span></span> <span data-ttu-id="80814-109">应用于包装器的安全机制与属性系统行为以及基础依赖属性的访问并不可比。</span><span class="sxs-lookup"><span data-stu-id="80814-109">Security mechanisms applied to the wrappers do not parallel the property system behavior and access of the underlying dependency property.</span></span> <span data-ttu-id="80814-110">放置在包装上的安全要求会仅阻止以便捷方法的使用情况，但将不会阻止对调用<xref:System.Windows.DependencyObject.GetValue%2A>或<xref:System.Windows.DependencyObject.SetValue%2A>。</span><span class="sxs-lookup"><span data-stu-id="80814-110">Placing a security demand on the wrapper will only prevent the usage of the convenience method but will not prevent calls to <xref:System.Windows.DependencyObject.GetValue%2A> or <xref:System.Windows.DependencyObject.SetValue%2A>.</span></span> <span data-ttu-id="80814-111">同样，为包装器设置受保护或私有访问级别也不会提供任何有效的安全性。</span><span class="sxs-lookup"><span data-stu-id="80814-111">Similarly, placing protected or private access level on the wrappers does not provide any effective security.</span></span>  
  
 <span data-ttu-id="80814-112">如果你正在编写自己的依赖项属性，则应声明包装器和<xref:System.Windows.DependencyProperty>标识符字段，为公共成员，以便调用方执行不获取具有误导性，有关该属性的实际访问级别的信息 （由于其存储在实现为依赖项属性）。</span><span class="sxs-lookup"><span data-stu-id="80814-112">If you are writing your own dependency properties, you should declare the wrappers and the <xref:System.Windows.DependencyProperty> identifier field as public members, so that callers do not get misleading information about the true access level of that property (because of its store being implemented as a dependency property).</span></span>  
  
 <span data-ttu-id="80814-113">对于自定义的依赖项属性，可以注册你的属性，为只读依赖属性，而且这确实提供阻止不保存对引用的任何人设置的属性的有效方式<xref:System.Windows.DependencyPropertyKey>该属性。</span><span class="sxs-lookup"><span data-stu-id="80814-113">For a custom dependency property, you can register your property as a read-only dependency property, and this does provide an effective means of preventing a property being set by anyone that does not hold a reference to the <xref:System.Windows.DependencyPropertyKey> for that property.</span></span> <span data-ttu-id="80814-114">有关详细信息，请参阅[只读依赖属性](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="80814-114">For more information, see [Read-Only Dependency Properties](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80814-115">声明<xref:System.Windows.DependencyProperty>标识符字段私有不已禁止，和拿可以用于帮助减少立即公开命名空间的自定义类，但这样的属性不应被认为在相同的意义上为"私有" [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]语言定义将定义该访问级别下, 一节中描述的原因。</span><span class="sxs-lookup"><span data-stu-id="80814-115">Declaring a <xref:System.Windows.DependencyProperty> identifier field private is not forbidden, and it can conceivably be used to help reduce the immediately exposed namespace of a custom class, but such a property should not be considered "private" in the same sense as the [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] language definitions define that access level, for reasons described in the next section.</span></span>  
  
<a name="PropertySystemExposure"></a>   
## <a name="property-system-exposure-of-dependency-properties"></a><span data-ttu-id="80814-116">依赖属性的属性系统公开</span><span class="sxs-lookup"><span data-stu-id="80814-116">Property System Exposure of Dependency Properties</span></span>  
 <span data-ttu-id="80814-117">它并不通常很有用，并且它有可能误导性，若要声明<xref:System.Windows.DependencyProperty>任何访问级别不是公共。</span><span class="sxs-lookup"><span data-stu-id="80814-117">It is not generally useful, and it is potentially misleading, to declare a <xref:System.Windows.DependencyProperty> as any access level other than public.</span></span> <span data-ttu-id="80814-118">该访问级别设置只是防止某人从声明类获得对实例的引用。</span><span class="sxs-lookup"><span data-stu-id="80814-118">That access level setting only prevents someone from being able to get a reference to the instance from the declaring class.</span></span> <span data-ttu-id="80814-119">但有几个方面的属性系统的将返回<xref:System.Windows.DependencyProperty>来标识的特定属性，它存在于类的实例或派生的类实例，以及此标识符在仍可用于为<xref:System.Windows.DependencyObject.SetValue%2A>甚至调用如果原始的静态标识符声明为公共。</span><span class="sxs-lookup"><span data-stu-id="80814-119">But there are several aspects of the property system that will return a <xref:System.Windows.DependencyProperty> as the means of identifying a particular property as it exists on an instance of a class or a derived class instance, and this identifier is still usable in a <xref:System.Windows.DependencyObject.SetValue%2A> call even if the original static identifier is declared as nonpublic.</span></span> <span data-ttu-id="80814-120">此外，<xref:System.Windows.DependencyObject.OnPropertyChanged%2A>虚方法接收的值更改任何现有依赖项属性的信息。</span><span class="sxs-lookup"><span data-stu-id="80814-120">Also, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> virtual methods receive information of any existing dependency property that changed value.</span></span> <span data-ttu-id="80814-121">此外，<xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A>方法返回与本地设置的实例上的任何属性的标识符值。</span><span class="sxs-lookup"><span data-stu-id="80814-121">In addition, the <xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A> method returns identifiers for any property on instances with a locally set value.</span></span>  
  
### <a name="validation-and-security"></a><span data-ttu-id="80814-122">验证和安全</span><span class="sxs-lookup"><span data-stu-id="80814-122">Validation and Security</span></span>  
 <span data-ttu-id="80814-123">应用到一个要求<xref:System.Windows.DependencyProperty.ValidateValueCallback%2A>和应请求失败，以防止属性设置为验证失败不是足够的安全性机制。</span><span class="sxs-lookup"><span data-stu-id="80814-123">Applying a demand to a <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> and expecting the validation failure on a demand failure to prevent a property from being set is not an adequate security mechanism.</span></span> <span data-ttu-id="80814-124">通过强制设置值失效<xref:System.Windows.DependencyProperty.ValidateValueCallback%2A>还可禁止显示由恶意调用方，如果在应用程序域内操作这些调用方。</span><span class="sxs-lookup"><span data-stu-id="80814-124">Set-value invalidation enforced through <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> could also be suppressed by malicious callers, if those callers are operating within the application domain.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80814-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="80814-125">See Also</span></span>  
 [<span data-ttu-id="80814-126">自定义依赖属性</span><span class="sxs-lookup"><span data-stu-id="80814-126">Custom Dependency Properties</span></span>](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
