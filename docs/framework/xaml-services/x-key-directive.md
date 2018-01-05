---
title: "x:Key 指令"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xKey
- Key
- x:Key
helpviewer_keywords:
- x:Key attribute [XAML Services]
- Key attribute in XAML [XAML Services]
- XAML [XAML Services], x:Key attribute
ms.assetid: 1985cd45-f197-42d5-b75e-886add64b248
caps.latest.revision: "25"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2c73cf28905e1dd0f3056ab0eed953d6f05b0a7f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="xkey-directive"></a><span data-ttu-id="fc51a-102">x:Key 指令</span><span class="sxs-lookup"><span data-stu-id="fc51a-102">x:Key Directive</span></span>
<span data-ttu-id="fc51a-103">唯一标识元素创建和引用 XAML 定义的字典中。</span><span class="sxs-lookup"><span data-stu-id="fc51a-103">Uniquely identifies elements that are created and referenced in a XAML-defined dictionary.</span></span> <span data-ttu-id="fc51a-104">添加`x:Key`到 XAML 对象元素的值是标识资源字典中，例如在 WPF 中的资源的最常见方法<xref:System.Windows.ResourceDictionary>。</span><span class="sxs-lookup"><span data-stu-id="fc51a-104">Adding an `x:Key` value to a XAML object element is the most common way to identify a resource in a resource dictionary, for example in a WPF <xref:System.Windows.ResourceDictionary>.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="fc51a-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="fc51a-105">XAML Attribute Usage</span></span>  
  
```  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a><span data-ttu-id="fc51a-106">XAML 属性用法 （特定于 WPF）</span><span class="sxs-lookup"><span data-stu-id="fc51a-106">XAML Attribute Usage (WPF-specific)</span></span>  
  
```  
<object.Resources>  
  <object x:Key="stringKeyValue".../>  
</object.Resources>  
-or-  
<object.Resources>  
  <object x:Key="{markupExtensionUsage}".../>  
</object.Resources>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="fc51a-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="fc51a-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`stringKeyValue`|<span data-ttu-id="fc51a-108">要用作键的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="fc51a-108">A text string to use as a key.</span></span> <span data-ttu-id="fc51a-109">文本字符串必须符合[XamlName 语法](../../../docs/framework/xaml-services/xamlname-grammar.md)。</span><span class="sxs-lookup"><span data-stu-id="fc51a-109">The text string must conform to the [XamlName Grammar](../../../docs/framework/xaml-services/xamlname-grammar.md).</span></span>|  
|`markupExtensionUsage`|<span data-ttu-id="fc51a-110">在标记扩展的分隔符 {} 中，标记扩展用法，提供要使用作为键的对象。</span><span class="sxs-lookup"><span data-stu-id="fc51a-110">Within the markup extension delimiters {}, a markup extension usage that provides an object to use as a key.</span></span> <span data-ttu-id="fc51a-111">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="fc51a-111">See Remarks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc51a-112">备注</span><span class="sxs-lookup"><span data-stu-id="fc51a-112">Remarks</span></span>  
 <span data-ttu-id="fc51a-113">`x:Key`支持 XAML 资源字典概念。</span><span class="sxs-lookup"><span data-stu-id="fc51a-113">`x:Key` supports the XAML resource dictionary concept.</span></span> <span data-ttu-id="fc51a-114">作为一种语言的 XAML 未定义的资源字典实现，从左到特定的 UI 框架。</span><span class="sxs-lookup"><span data-stu-id="fc51a-114">XAML as a language doesn't define a resource dictionary implementation, that is left to specific UI frameworks.</span></span> <span data-ttu-id="fc51a-115">若要了解有关如何在 WPF 中实现 XAML 资源字典的详细信息，请参阅[XAML 资源](../../../docs/framework/wpf/advanced/xaml-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="fc51a-115">To learn more about how XAML resource dictionaries are implemented in WPF, see [XAML Resources](../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
 <span data-ttu-id="fc51a-116">在 XAML 2006 和 WPF，`x:Key`必须作为属性提供。</span><span class="sxs-lookup"><span data-stu-id="fc51a-116">In XAML 2006 and WPF, `x:Key` must be provided as an attribute.</span></span> <span data-ttu-id="fc51a-117">你仍然可以使用非字符串键，但这要求以便提供属性窗体中的非字符串值的标记扩展用法。</span><span class="sxs-lookup"><span data-stu-id="fc51a-117">You can still use nonstring keys, but this requires a markup extension usage in order to provide the nonstring value in attribute form.</span></span> <span data-ttu-id="fc51a-118">如果你使用 XAML 2009`x:Key`可以被指定为元素，以显式支持键控的对象类型以外的字典字符串而无需中间的标记扩展。</span><span class="sxs-lookup"><span data-stu-id="fc51a-118">If you are using XAML 2009, `x:Key` can be specified as an element, to explicitly support dictionaries keyed by object types other than strings without requiring a markup extension intermediate.</span></span> <span data-ttu-id="fc51a-119">请参阅本主题中的"XAML 2009"一节。</span><span class="sxs-lookup"><span data-stu-id="fc51a-119">See the "XAML 2009" section in this topic.</span></span> <span data-ttu-id="fc51a-120">备注部分的其余部分特别适用于 XAML 2006 实现。</span><span class="sxs-lookup"><span data-stu-id="fc51a-120">The remainder of the Remarks section applies specifically to the XAML 2006 implementation.</span></span>  
  
 <span data-ttu-id="fc51a-121">属性值的`x:Key`可以中定义的任何字符串[XamlName 语法](../../../docs/framework/xaml-services/xamlname-grammar.md)也可以是计算通过标记扩展的对象。</span><span class="sxs-lookup"><span data-stu-id="fc51a-121">The attribute value of `x:Key` can be any string defined in the [XamlName Grammar](../../../docs/framework/xaml-services/xamlname-grammar.md) or can be an object evaluated through a markup extension.</span></span> <span data-ttu-id="fc51a-122">有关从 WPF 示例，请参阅"WPF 用法注释"。</span><span class="sxs-lookup"><span data-stu-id="fc51a-122">See "WPF Usage Notes" for an example from WPF.</span></span>  
  
 <span data-ttu-id="fc51a-123">是一个父元素的子元素<xref:System.Collections.IDictionary>实现通常必须包括`x:Key`指定唯一的键值，该字典中的属性。</span><span class="sxs-lookup"><span data-stu-id="fc51a-123">Child elements of a parent element that is an <xref:System.Collections.IDictionary> implementation must typically include an `x:Key` attribute that specifies a unique key value within that dictionary.</span></span> <span data-ttu-id="fc51a-124">框架可能实现使用别名键属性，用于替换`x:Key`对特定类型; 定义此类属性的类型应使用进行特性化<xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>。</span><span class="sxs-lookup"><span data-stu-id="fc51a-124">Frameworks might implement aliased key properties to substitute for `x:Key` on particular types; types that define such properties should be attributed with <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.</span></span>  
  
 <span data-ttu-id="fc51a-125">指定的代码等效项`x:Key`是适用于基础的关键<xref:System.Collections.IDictionary>。</span><span class="sxs-lookup"><span data-stu-id="fc51a-125">The code equivalent of specifying `x:Key` is the key that is used for the underlying <xref:System.Collections.IDictionary>.</span></span> <span data-ttu-id="fc51a-126">例如， `x:Key` ，在应用中标记的值等效 WPF 中的资源为`key`参数<xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>时将资源添加到 WPF<xref:System.Windows.ResourceDictionary>在代码中。</span><span class="sxs-lookup"><span data-stu-id="fc51a-126">For example, an `x:Key` that is applied in markup for a resource in WPF is equivalent to the value of the `key` parameter of <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> when you add the resource to a WPF <xref:System.Windows.ResourceDictionary> in code.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="fc51a-127">WPF 用法说明</span><span class="sxs-lookup"><span data-stu-id="fc51a-127">WPF Usage Notes</span></span>  
 <span data-ttu-id="fc51a-128">子对象的父对象，该对象<xref:System.Collections.IDictionary>实现，如 WPF <xref:System.Windows.ResourceDictionary>，通常必须包括`x:Key`属性和密钥值内必须是唯一的字典。</span><span class="sxs-lookup"><span data-stu-id="fc51a-128">Child objects of a parent object that is an <xref:System.Collections.IDictionary> implementation, such as the WPF <xref:System.Windows.ResourceDictionary>, must typically include an `x:Key` attribute, and the key value must be unique within that dictionary.</span></span> <span data-ttu-id="fc51a-129">有两个值得注意的例外情况：</span><span class="sxs-lookup"><span data-stu-id="fc51a-129">There are two notable exceptions:</span></span>  
  
-   <span data-ttu-id="fc51a-130">一些 WPF 类型声明用于字典使用情况的隐式密钥。</span><span class="sxs-lookup"><span data-stu-id="fc51a-130">Some WPF types declare an implicit key for dictionary usage.</span></span> <span data-ttu-id="fc51a-131">例如，<xref:System.Windows.Style>与<xref:System.Windows.Style.TargetType%2A>，或<xref:System.Windows.DataTemplate>与<xref:System.Windows.DataTemplate.DataType%2A>，可能处于<xref:System.Windows.ResourceDictionary>并使用隐式密钥。</span><span class="sxs-lookup"><span data-stu-id="fc51a-131">For example, a <xref:System.Windows.Style> with a <xref:System.Windows.Style.TargetType%2A>, or a <xref:System.Windows.DataTemplate> with a <xref:System.Windows.DataTemplate.DataType%2A>, can be  in a <xref:System.Windows.ResourceDictionary> and use the implicit key.</span></span>  
  
-   <span data-ttu-id="fc51a-132">WPF 支持合并的资源字典概念。</span><span class="sxs-lookup"><span data-stu-id="fc51a-132">WPF supports a merged resource dictionary concept.</span></span> <span data-ttu-id="fc51a-133">密钥可以共享之间合并的字典，并且可以使用访问的共享密钥行为<xref:System.Windows.FrameworkContentElement.FindResource%2A>。</span><span class="sxs-lookup"><span data-stu-id="fc51a-133">Keys can be shared between the merged dictionaries, and the shared key behavior can be accessed using <xref:System.Windows.FrameworkContentElement.FindResource%2A>.</span></span> <span data-ttu-id="fc51a-134">有关详细信息，请参阅[合并资源字典](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)。</span><span class="sxs-lookup"><span data-stu-id="fc51a-134">For more information, see [Merged Resource Dictionaries](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md).</span></span>  
  
 <span data-ttu-id="fc51a-135">总体 WPF XAML 实现和应用程序模型中，由 XAML 标记编译器进行不检查唯一性。</span><span class="sxs-lookup"><span data-stu-id="fc51a-135">In the overall WPF XAML implementation and application model, key uniqueness is not checked by the XAML markup compiler.</span></span> <span data-ttu-id="fc51a-136">相反，丢失或非唯一`x:Key`值会导致加载时间 XAML 分析器错误。</span><span class="sxs-lookup"><span data-stu-id="fc51a-136">Instead, missing or nonunique `x:Key` values cause load-time XAML parser errors.</span></span> <span data-ttu-id="fc51a-137">但是，[!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]处理的字典中的 WPF 通常可以在设计阶段注意此类错误。</span><span class="sxs-lookup"><span data-stu-id="fc51a-137">However, [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] handling of dictionaries for WPF can often note such errors in the design phase.</span></span>  
  
 <span data-ttu-id="fc51a-138">请注意，在语法中所示，<xref:System.Windows.ResourceDictionary>对象是隐式的 WPF XAML 处理器如何生成一个集合来填充<xref:System.Windows.FrameworkElement.Resources%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="fc51a-138">Note that in the syntax shown, the <xref:System.Windows.ResourceDictionary> object is implicit in how the WPF XAML processor produces a collection to populate a <xref:System.Windows.FrameworkElement.Resources%2A> collection.</span></span> <span data-ttu-id="fc51a-139">A<xref:System.Windows.ResourceDictionary>不通常用作显式的元素在标记中，但也可以是在某些情况下，如果想为清楚起见 (它将集合对象元素之间<xref:System.Windows.FrameworkElement.Resources%2A>属性元素，并在其中的项填充字典）。</span><span class="sxs-lookup"><span data-stu-id="fc51a-139">A <xref:System.Windows.ResourceDictionary> is not typically provided explicitly as an element in markup, although it can be in some cases if wanted for clarity (it would be a collection object element between the <xref:System.Windows.FrameworkElement.Resources%2A> property element and the items within that populate the dictionary).</span></span> <span data-ttu-id="fc51a-140">有关为什么集合对象几乎始终是隐式元素标记中的信息，请参阅[在详细信息的 XAML 语法](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)。</span><span class="sxs-lookup"><span data-stu-id="fc51a-140">For information about why a collection object is almost always an implicit element in markup, see [XAML Syntax In Detail](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).</span></span>  
  
 <span data-ttu-id="fc51a-141">在 WPF XAML 实现中，资源字典键的处理由定义<xref:System.Windows.ResourceKey>抽象类。</span><span class="sxs-lookup"><span data-stu-id="fc51a-141">In the WPF XAML implementation, the handling for resource dictionary keys is defined by the <xref:System.Windows.ResourceKey> abstract class.</span></span> <span data-ttu-id="fc51a-142">但是，WPF XAML 处理器生成不同基础的扩展类型，密钥基于它们的用法。</span><span class="sxs-lookup"><span data-stu-id="fc51a-142">However the WPF XAML processor produces different underlying extension types for keys based on their usages.</span></span> <span data-ttu-id="fc51a-143">例如，为项<xref:System.Windows.DataTemplate>或任何派生的类分别进行处理，并且生成一个不同<xref:System.Windows.DataTemplateKey>对象。</span><span class="sxs-lookup"><span data-stu-id="fc51a-143">For example, the key for a <xref:System.Windows.DataTemplate> or any derived class is handled separately, and produces a distinct <xref:System.Windows.DataTemplateKey> object.</span></span>  
  
 <span data-ttu-id="fc51a-144">键和名称使用不同的指令和语言元素 (`x:Key`与`x:Name`) 中的基本的 XAML 定义。</span><span class="sxs-lookup"><span data-stu-id="fc51a-144">Keys and names use different directives and language elements (`x:Key` versus `x:Name`) in the basic XAML definition.</span></span> <span data-ttu-id="fc51a-145">键和名称也使用不同的情况下的 WPF 定义和应用程序的这些概念。</span><span class="sxs-lookup"><span data-stu-id="fc51a-145">Keys and names are also used in different situations by the WPF definition and application of these concepts.</span></span> <span data-ttu-id="fc51a-146">有关详细信息，请参阅[WPF XAML Namescopes](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)。</span><span class="sxs-lookup"><span data-stu-id="fc51a-146">For details, see [WPF XAML Namescopes](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md).</span></span>  
  
 <span data-ttu-id="fc51a-147">如前面所述，键的值可以通过标记扩展提供，并且可以字符串值以外。</span><span class="sxs-lookup"><span data-stu-id="fc51a-147">As stated previously, the value of a key can be supplied through a markup extension and can be other than a string value.</span></span> <span data-ttu-id="fc51a-148">示例 WPF 方案是的值`x:Key`可能[ComponentResourceKey](../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md)。</span><span class="sxs-lookup"><span data-stu-id="fc51a-148">An example WPF scenario is that the value of `x:Key` may be a[ComponentResourceKey](../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md).</span></span> <span data-ttu-id="fc51a-149">某些控件公开样式的键的该类型的自定义样式资源的影响而不替换样式的外观的一部分，该控件的行为。</span><span class="sxs-lookup"><span data-stu-id="fc51a-149">Certain controls expose a style key of that type for a custom style resource that influences part of the appearance and behavior of that control without totally replacing the style.</span></span> <span data-ttu-id="fc51a-150">此密钥的一个示例是<xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>。</span><span class="sxs-lookup"><span data-stu-id="fc51a-150">An example of such a key is <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>.</span></span>  
  
 <span data-ttu-id="fc51a-151">WPF 合并的字典功能引入了键唯一性和键查找行为的其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="fc51a-151">The WPF merged dictionary feature introduces additional considerations for key uniqueness and key lookup behavior.</span></span> <span data-ttu-id="fc51a-152">有关详细信息，请参阅[合并资源字典](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)。</span><span class="sxs-lookup"><span data-stu-id="fc51a-152">For more information, see [Merged Resource Dictionaries](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md).</span></span>  
  
## <a name="xaml-2009"></a><span data-ttu-id="fc51a-153">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="fc51a-153">XAML 2009</span></span>  
 <span data-ttu-id="fc51a-154">XAML 2009 解除此限制，`x:Key`始终以属性形式提供。</span><span class="sxs-lookup"><span data-stu-id="fc51a-154">XAML 2009 relaxes the restriction that `x:Key` always be provided in attribute form.</span></span>  
  
 <span data-ttu-id="fc51a-155">在 WPF 中，你可以使用 XAML 2009 功能，但只针对未标记编译的 XAML。</span><span class="sxs-lookup"><span data-stu-id="fc51a-155">In WPF, you can use XAML 2009 features, but only for XAML that is not markup-compiled.</span></span> <span data-ttu-id="fc51a-156">WPF 的已编译标记的 XAML 以及 XAML 的 BAML 形式当前不支持 XAML 2009 关键字和功能。</span><span class="sxs-lookup"><span data-stu-id="fc51a-156">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>  
  
 <span data-ttu-id="fc51a-157">在 XAML 2009 中可以指定`x:Key`通过以下使用情况的元素：</span><span class="sxs-lookup"><span data-stu-id="fc51a-157">Under XAML 2009, you can specify `x:Key` elements through the following usage:</span></span>  
  
### <a name="xaml-element-usage-xaml-2009-only"></a><span data-ttu-id="fc51a-158">XAML 元素用法 （仅 XAML 2009 年）</span><span class="sxs-lookup"><span data-stu-id="fc51a-158">XAML Element Usage (XAML 2009 only)</span></span>  
  
```  
<object>  
  <x:Key>  
keyObject  
  </x:Key>  
...  
</object>  
```  
  
### <a name="xaml-values"></a><span data-ttu-id="fc51a-159">XAML 值</span><span class="sxs-lookup"><span data-stu-id="fc51a-159">XAML Values</span></span>  
  
|||  
|-|-|  
|`keyObject`|<span data-ttu-id="fc51a-160">用作键的对象的对象元素给定`object`专用字典中。</span><span class="sxs-lookup"><span data-stu-id="fc51a-160">Object element for the object that is used as the key for a given `object` in a specialized dictionary.</span></span>|  
  
-   <span data-ttu-id="fc51a-161">使用这种容器/父级不在此处显示。</span><span class="sxs-lookup"><span data-stu-id="fc51a-161">The container/parent for this kind of use is not shown here.</span></span> <span data-ttu-id="fc51a-162">`object`应为表示一种专用的字典实现对象元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="fc51a-162">`object` is expected to be a child of an object element that represents a specialized dictionary implementation.</span></span> <span data-ttu-id="fc51a-163">`keyObject`应为对象实例 （或值类型的值），适合作为该特定的专用的字典实现的密钥。</span><span class="sxs-lookup"><span data-stu-id="fc51a-163">`keyObject` is expected to be an object instance (or a value of a value type) that is appropriate as the key for that particular specialized dictionary implementation.</span></span>  
  
-   <span data-ttu-id="fc51a-164">WPF 未实现需要这种用法的字典。</span><span class="sxs-lookup"><span data-stu-id="fc51a-164">WPF does not implement dictionaries that require this usage.</span></span> <span data-ttu-id="fc51a-165">对象键是更可能有用的某些自定义词典方案在 XAML 中创建字典所需的 XAML 语言的常规功能。</span><span class="sxs-lookup"><span data-stu-id="fc51a-165">Object keys is more a general feature of the XAML language, possibly useful for certain custom dictionary scenarios where creating the dictionary in XAML is desirable.</span></span> <span data-ttu-id="fc51a-166">WPF 功能，如对资源使用非字符串键的隐式样式，用于建立或指定键的其他方法存在，因此不需要使用对象键。</span><span class="sxs-lookup"><span data-stu-id="fc51a-166">For WPF features such as implicit styles that use non-string keys for resources, other techniques for establishing or specifying the keys exist, so using an object key is not necessary.</span></span>  
  
-   <span data-ttu-id="fc51a-167">*keyObject*也可能是在对象元素窗体，而不是直接对象实例的标记扩展用法。</span><span class="sxs-lookup"><span data-stu-id="fc51a-167">*keyObject* could also be a markup extension usage in object element form, rather than a direct object instance.</span></span>  
  
## <a name="silverlight-usage-notes"></a><span data-ttu-id="fc51a-168">Silverlight 用法说明</span><span class="sxs-lookup"><span data-stu-id="fc51a-168">Silverlight Usage Notes</span></span>  
 <span data-ttu-id="fc51a-169">`x:Key`适用于 Silverlight 是分开记录。</span><span class="sxs-lookup"><span data-stu-id="fc51a-169">`x:Key` for Silverlight is documented separately.</span></span> <span data-ttu-id="fc51a-170">有关详细信息，请参阅[XAML Namespace （x:）语言功能 (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081)。</span><span class="sxs-lookup"><span data-stu-id="fc51a-170">For more information, see [XAML Namespace (x:) Language Features (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc51a-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc51a-171">See Also</span></span>  
 [<span data-ttu-id="fc51a-172">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="fc51a-172">XAML Resources</span></span>](../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="fc51a-173">资源和代码</span><span class="sxs-lookup"><span data-stu-id="fc51a-173">Resources and Code</span></span>](../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [<span data-ttu-id="fc51a-174">StaticResource 标记扩展</span><span class="sxs-lookup"><span data-stu-id="fc51a-174">StaticResource Markup Extension</span></span>](../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)
