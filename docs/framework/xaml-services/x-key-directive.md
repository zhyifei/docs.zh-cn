---
title: x:Key 指令
ms.date: 03/30/2017
f1_keywords:
- xKey
- Key
- x:Key
helpviewer_keywords:
- x:Key attribute [XAML Services]
- Key attribute in XAML [XAML Services]
- XAML [XAML Services], x:Key attribute
ms.assetid: 1985cd45-f197-42d5-b75e-886add64b248
ms.openlocfilehash: 4ffd7a2922c7f3ba35ccb9ac7ce29a6a00cd99af
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837202"
---
# <a name="xkey-directive"></a><span data-ttu-id="d0bdb-102">x:Key 指令</span><span class="sxs-lookup"><span data-stu-id="d0bdb-102">x:Key Directive</span></span>
<span data-ttu-id="d0bdb-103">唯一地标识在 XAML 定义的字典中创建和引用的元素。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-103">Uniquely identifies elements that are created and referenced in a XAML-defined dictionary.</span></span> <span data-ttu-id="d0bdb-104">将 `x:Key` 值添加到 XAML 对象元素是标识资源字典（如 WPF <xref:System.Windows.ResourceDictionary>）中资源的最常用的方法。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-104">Adding an `x:Key` value to a XAML object element is the most common way to identify a resource in a resource dictionary, for example in a WPF <xref:System.Windows.ResourceDictionary>.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="d0bdb-105">XAML 特性用法</span><span class="sxs-lookup"><span data-stu-id="d0bdb-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a><span data-ttu-id="d0bdb-106">XAML 特性用法（特定于 WPF）</span><span class="sxs-lookup"><span data-stu-id="d0bdb-106">XAML Attribute Usage (WPF-specific)</span></span>  
  
```xaml  
<object.Resources>  
  <object x:Key="stringKeyValue".../>  
</object.Resources>  
-or-  
<object.Resources>  
  <object x:Key="{markupExtensionUsage}".../>  
</object.Resources>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="d0bdb-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="d0bdb-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`stringKeyValue`|<span data-ttu-id="d0bdb-108">要用作键的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-108">A text string to use as a key.</span></span> <span data-ttu-id="d0bdb-109">文本字符串必须符合[XamlName 语法](xamlname-grammar.md)。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-109">The text string must conform to the [XamlName Grammar](xamlname-grammar.md).</span></span>|  
|`markupExtensionUsage`|<span data-ttu-id="d0bdb-110">标记扩展分隔符 {}，这是一个提供要用作键的对象的标记扩展用法。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-110">Within the markup extension delimiters {}, a markup extension usage that provides an object to use as a key.</span></span> <span data-ttu-id="d0bdb-111">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-111">See Remarks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0bdb-112">备注</span><span class="sxs-lookup"><span data-stu-id="d0bdb-112">Remarks</span></span>  
 <span data-ttu-id="d0bdb-113">`x:Key` 支持 XAML 资源字典概念。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-113">`x:Key` supports the XAML resource dictionary concept.</span></span> <span data-ttu-id="d0bdb-114">作为语言的 XAML 不定义资源字典实现，而是由具体的 UI 框架定义。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-114">XAML as a language doesn't define a resource dictionary implementation, that is left to specific UI frameworks.</span></span> <span data-ttu-id="d0bdb-115">若要了解有关如何在 WPF 中实现 XAML 资源字典的详细信息，请参阅[Xaml 资源](../../desktop-wpf/fundamentals/xaml-resources-define.md)。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-115">To learn more about how XAML resource dictionaries are implemented in WPF, see [XAML Resources](../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>  
  
 <span data-ttu-id="d0bdb-116">在 XAML 2006 和 WPF 中，`x:Key` 必须作为属性提供。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-116">In XAML 2006 and WPF, `x:Key` must be provided as an attribute.</span></span> <span data-ttu-id="d0bdb-117">您仍可以使用非字符串键，但这需要标记扩展用法来提供特性窗体中的非字符串值。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-117">You can still use nonstring keys, but this requires a markup extension usage in order to provide the nonstring value in attribute form.</span></span> <span data-ttu-id="d0bdb-118">如果你使用的是 XAML 2009，则可以将 `x:Key` 指定为元素，以显式支持由对象类型（而不是字符串）提供支持的字典，而无需使用标记扩展。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-118">If you are using XAML 2009, `x:Key` can be specified as an element, to explicitly support dictionaries keyed by object types other than strings without requiring a markup extension intermediate.</span></span> <span data-ttu-id="d0bdb-119">请参阅本主题中的 "XAML 2009" 部分。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-119">See the "XAML 2009" section in this topic.</span></span> <span data-ttu-id="d0bdb-120">备注部分的剩余部分专门适用于 XAML 2006 实现。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-120">The remainder of the Remarks section applies specifically to the XAML 2006 implementation.</span></span>  
  
 <span data-ttu-id="d0bdb-121">`x:Key` 的属性值可以是[XamlName 语法](xamlname-grammar.md)中定义的任何字符串，也可以是通过标记扩展进行计算的对象。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-121">The attribute value of `x:Key` can be any string defined in the [XamlName Grammar](xamlname-grammar.md) or can be an object evaluated through a markup extension.</span></span> <span data-ttu-id="d0bdb-122">有关来自 WPF 的示例，请参见“WPF 用法说明”。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-122">See "WPF Usage Notes" for an example from WPF.</span></span>  
  
 <span data-ttu-id="d0bdb-123">作为 <xref:System.Collections.IDictionary> 实现的父元素的子元素通常必须包括一个 `x:Key` 特性，用来指定该字典中的唯一键值。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-123">Child elements of a parent element that is an <xref:System.Collections.IDictionary> implementation must typically include an `x:Key` attribute that specifies a unique key value within that dictionary.</span></span> <span data-ttu-id="d0bdb-124">Frameworks 可以实现具有别名的键属性，以替换特定类型中的 `x:Key`；定义此类属性的类型应使用 <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute> 进行特性化。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-124">Frameworks might implement aliased key properties to substitute for `x:Key` on particular types; types that define such properties should be attributed with <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.</span></span>  
  
 <span data-ttu-id="d0bdb-125">与指定 `x:Key` 等效的代码是用于基础 <xref:System.Collections.IDictionary> 的键。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-125">The code equivalent of specifying `x:Key` is the key that is used for the underlying <xref:System.Collections.IDictionary>.</span></span> <span data-ttu-id="d0bdb-126">例如，当您向代码中的 WPF <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> 添加资源时，应用于 WPF 中的资源的标记中的 `x:Key` 等效于 <xref:System.Windows.ResourceDictionary> 的 `key` 参数值。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-126">For example, an `x:Key` that is applied in markup for a resource in WPF is equivalent to the value of the `key` parameter of <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> when you add the resource to a WPF <xref:System.Windows.ResourceDictionary> in code.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="d0bdb-127">WPF 使用说明</span><span class="sxs-lookup"><span data-stu-id="d0bdb-127">WPF Usage Notes</span></span>  
 <span data-ttu-id="d0bdb-128">作为 <xref:System.Collections.IDictionary> 实现（如 WPF <xref:System.Windows.ResourceDictionary>）的父对象的子对象通常必须包括一个 `x:Key` 特性，并且该字典中的键值必须唯一。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-128">Child objects of a parent object that is an <xref:System.Collections.IDictionary> implementation, such as the WPF <xref:System.Windows.ResourceDictionary>, must typically include an `x:Key` attribute, and the key value must be unique within that dictionary.</span></span> <span data-ttu-id="d0bdb-129">有两种值得注意的例外情况：</span><span class="sxs-lookup"><span data-stu-id="d0bdb-129">There are two notable exceptions:</span></span>  
  
- <span data-ttu-id="d0bdb-130">某些 WPF 类型声明一个隐式的字典使用键。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-130">Some WPF types declare an implicit key for dictionary usage.</span></span> <span data-ttu-id="d0bdb-131">例如，具有 <xref:System.Windows.Style> 的 <xref:System.Windows.Style.TargetType%2A> 或具有 <xref:System.Windows.DataTemplate> 的 <xref:System.Windows.DataTemplate.DataType%2A> 可以放置在 <xref:System.Windows.ResourceDictionary> 中，并使用隐式键。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-131">For example, a <xref:System.Windows.Style> with a <xref:System.Windows.Style.TargetType%2A>, or a <xref:System.Windows.DataTemplate> with a <xref:System.Windows.DataTemplate.DataType%2A>, can be  in a <xref:System.Windows.ResourceDictionary> and use the implicit key.</span></span>  
  
- <span data-ttu-id="d0bdb-132">WPF 支持一个合并的资源字典概念。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-132">WPF supports a merged resource dictionary concept.</span></span> <span data-ttu-id="d0bdb-133">键可在合并的字典之间共享，并且共享的键行为可以使用 <xref:System.Windows.FrameworkContentElement.FindResource%2A> 进行访问。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-133">Keys can be shared between the merged dictionaries, and the shared key behavior can be accessed using <xref:System.Windows.FrameworkContentElement.FindResource%2A>.</span></span> <span data-ttu-id="d0bdb-134">有关详细信息，请参阅[合并资源字典](../wpf/advanced/merged-resource-dictionaries.md)。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-134">For more information, see [Merged Resource Dictionaries](../wpf/advanced/merged-resource-dictionaries.md).</span></span>  
  
 <span data-ttu-id="d0bdb-135">在整个 WPF XAML 实现和应用程序模型中，XAML 标记编译器不会检测密钥的唯一性。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-135">In the overall WPF XAML implementation and application model, key uniqueness is not checked by the XAML markup compiler.</span></span> <span data-ttu-id="d0bdb-136">相反，丢失或非唯一的 `x:Key` 值导致加载时 XAML 分析程序错误。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-136">Instead, missing or nonunique `x:Key` values cause load-time XAML parser errors.</span></span> <span data-ttu-id="d0bdb-137">但是，Visual Studio for WPF 字典处理通常会在设计阶段记录此类错误。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-137">However, Visual Studio handling of dictionaries for WPF can often note such errors in the design phase.</span></span>  
  
 <span data-ttu-id="d0bdb-138">请注意，在所显示的语法中，<xref:System.Windows.ResourceDictionary> 对象在 WPF XAML 处理器生成一个集合来填充 <xref:System.Windows.FrameworkElement.Resources%2A> 集合的方式上是隐式的。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-138">Note that in the syntax shown, the <xref:System.Windows.ResourceDictionary> object is implicit in how the WPF XAML processor produces a collection to populate a <xref:System.Windows.FrameworkElement.Resources%2A> collection.</span></span> <span data-ttu-id="d0bdb-139"><xref:System.Windows.ResourceDictionary> 在标记中通常不以显式方式作为元素提供，尽管在某些情况下为了清楚起见希望这样做（此时它将充当 <xref:System.Windows.FrameworkElement.Resources%2A> 属性元素和其中填充字典的项之间的集合对象元素）。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-139">A <xref:System.Windows.ResourceDictionary> is not typically provided explicitly as an element in markup, although it can be in some cases if wanted for clarity (it would be a collection object element between the <xref:System.Windows.FrameworkElement.Resources%2A> property element and the items within that populate the dictionary).</span></span> <span data-ttu-id="d0bdb-140">有关集合对象在标记中几乎始终为隐式元素的原因的信息，请参阅[XAML 语法（详细](../wpf/advanced/xaml-syntax-in-detail.md)）。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-140">For information about why a collection object is almost always an implicit element in markup, see [XAML Syntax In Detail](../wpf/advanced/xaml-syntax-in-detail.md).</span></span>  
  
 <span data-ttu-id="d0bdb-141">在 WPF XAML 实现中，资源字典键的处理由 <xref:System.Windows.ResourceKey> 抽象类定义。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-141">In the WPF XAML implementation, the handling for resource dictionary keys is defined by the <xref:System.Windows.ResourceKey> abstract class.</span></span> <span data-ttu-id="d0bdb-142">但是，WPF XAML 处理器会基于键的用法为键生成不同的基础扩展类型。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-142">However the WPF XAML processor produces different underlying extension types for keys based on their usages.</span></span> <span data-ttu-id="d0bdb-143">例如，<xref:System.Windows.DataTemplate> 或任何派生类的键是单独处理的，并生成一个不同的 <xref:System.Windows.DataTemplateKey> 对象。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-143">For example, the key for a <xref:System.Windows.DataTemplate> or any derived class is handled separately, and produces a distinct <xref:System.Windows.DataTemplateKey> object.</span></span>  
  
 <span data-ttu-id="d0bdb-144">键和名称在基本 XAML 定义中使用不同的指令和语言元素（`x:Key` 与 `x:Name`）。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-144">Keys and names use different directives and language elements (`x:Key` versus `x:Name`) in the basic XAML definition.</span></span> <span data-ttu-id="d0bdb-145">键和名称还可通过 WPF 定义和应用这些概念在不同的情况中使用。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-145">Keys and names are also used in different situations by the WPF definition and application of these concepts.</span></span> <span data-ttu-id="d0bdb-146">有关详细信息，请参阅[WPF XAML 名称范围](../wpf/advanced/wpf-xaml-namescopes.md)。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-146">For details, see [WPF XAML Namescopes](../wpf/advanced/wpf-xaml-namescopes.md).</span></span>  
  
 <span data-ttu-id="d0bdb-147">如前所述，键值可以是通过标记扩展提供的值，也可以是字符串值以外的值。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-147">As stated previously, the value of a key can be supplied through a markup extension and can be other than a string value.</span></span> <span data-ttu-id="d0bdb-148">WPF 方案的一个示例是 `x:Key` 的值可能是[ComponentResourceKey](../wpf/advanced/componentresourcekey-markup-extension.md)。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-148">An example WPF scenario is that the value of `x:Key` may be a [ComponentResourceKey](../wpf/advanced/componentresourcekey-markup-extension.md).</span></span> <span data-ttu-id="d0bdb-149">某些控件公开该类型的自定义样式资源的样式键，这些资源会影响该控件的外观和行为，而不是替换整个控件的样式。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-149">Certain controls expose a style key of that type for a custom style resource that influences part of the appearance and behavior of that control without totally replacing the style.</span></span> <span data-ttu-id="d0bdb-150"><xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A> 就是这样的一个键。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-150">An example of such a key is <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>.</span></span>  
  
 <span data-ttu-id="d0bdb-151">WPF 合并的词典功能引入了关于键唯一性和键查找行为的其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-151">The WPF merged dictionary feature introduces additional considerations for key uniqueness and key lookup behavior.</span></span> <span data-ttu-id="d0bdb-152">有关详细信息，请参阅[合并资源字典](../wpf/advanced/merged-resource-dictionaries.md)。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-152">For more information, see [Merged Resource Dictionaries](../wpf/advanced/merged-resource-dictionaries.md).</span></span>  
  
## <a name="xaml-2009"></a><span data-ttu-id="d0bdb-153">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="d0bdb-153">XAML 2009</span></span>  
 <span data-ttu-id="d0bdb-154">XAML 2009 放宽了 `x:Key` 始终以属性形式提供的限制。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-154">XAML 2009 relaxes the restriction that `x:Key` always be provided in attribute form.</span></span>  
  
 <span data-ttu-id="d0bdb-155">在 WPF 中，可以使用 XAML 2009 功能，但仅针对未进行标记编译的 XAML。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-155">In WPF, you can use XAML 2009 features, but only for XAML that is not markup-compiled.</span></span> <span data-ttu-id="d0bdb-156">WPF 的已编译标记的 XAML 以及 XAML 的 BAML 形式当前不支持 XAML 2009 关键字和功能。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-156">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>  
  
 <span data-ttu-id="d0bdb-157">在 XAML 2009 下，可以通过以下用法指定 `x:Key` 元素：</span><span class="sxs-lookup"><span data-stu-id="d0bdb-157">Under XAML 2009, you can specify `x:Key` elements through the following usage:</span></span>  
  
### <a name="xaml-element-usage-xaml-2009-only"></a><span data-ttu-id="d0bdb-158">XAML 元素使用情况（仅限于 XAML 2009）</span><span class="sxs-lookup"><span data-stu-id="d0bdb-158">XAML Element Usage (XAML 2009 only)</span></span>  
  
```xaml  
<object>  
  <x:Key>  
keyObject  
  </x:Key>  
...  
</object>  
```  
  
### <a name="xaml-values"></a><span data-ttu-id="d0bdb-159">XAML 值</span><span class="sxs-lookup"><span data-stu-id="d0bdb-159">XAML Values</span></span>  
  
|||  
|-|-|  
|`keyObject`|<span data-ttu-id="d0bdb-160">在专用字典中用作给定 `object` 的键的对象的对象元素。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-160">Object element for the object that is used as the key for a given `object` in a specialized dictionary.</span></span>|  
  
- <span data-ttu-id="d0bdb-161">这种类型的用法的容器/父级不会在此处显示。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-161">The container/parent for this kind of use is not shown here.</span></span> <span data-ttu-id="d0bdb-162">`object` 应为某种表示专用的词典实现的对象元素的子级。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-162">`object` is expected to be a child of an object element that represents a specialized dictionary implementation.</span></span> <span data-ttu-id="d0bdb-163">`keyObject` 应为对象实例（或值类型的值），适合用作该特定专用的词典实现的关键字。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-163">`keyObject` is expected to be an object instance (or a value of a value type) that is appropriate as the key for that particular specialized dictionary implementation.</span></span>  
  
- <span data-ttu-id="d0bdb-164">WPF 不实现要求此用法的词典。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-164">WPF does not implement dictionaries that require this usage.</span></span> <span data-ttu-id="d0bdb-165">对象键是 XAML 语言的常规功能。对于某些要在 XAML 中创建词典的自定义词典方案而言，该功能很有用。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-165">Object keys is more a general feature of the XAML language, possibly useful for certain custom dictionary scenarios where creating the dictionary in XAML is desirable.</span></span> <span data-ttu-id="d0bdb-166">隐式样式等 WPF 功能会将非字符串键用于资源，将其他技术用于建立或指定键存在性，所以没必要使用对象键。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-166">For WPF features such as implicit styles that use non-string keys for resources, other techniques for establishing or specifying the keys exist, so using an object key is not necessary.</span></span>  
  
- <span data-ttu-id="d0bdb-167">*keyObject*也可以是对象元素窗体中的标记扩展用法，而不是直接对象实例。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-167">*keyObject* could also be a markup extension usage in object element form, rather than a direct object instance.</span></span>  
  
## <a name="silverlight-usage-notes"></a><span data-ttu-id="d0bdb-168">Silverlight Usage 备注。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-168">Silverlight Usage Notes</span></span>  
 <span data-ttu-id="d0bdb-169">单独说明了 `x:Key` for Silverlight。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-169">`x:Key` for Silverlight is documented separately.</span></span> <span data-ttu-id="d0bdb-170">有关详细信息，请参阅[XAML 命名空间（x：）语言功能（Silverlight）](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95))。</span><span class="sxs-lookup"><span data-stu-id="d0bdb-170">For more information, see [XAML Namespace (x:) Language Features (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0bdb-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0bdb-171">See also</span></span>

- [<span data-ttu-id="d0bdb-172">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="d0bdb-172">XAML Resources</span></span>](../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="d0bdb-173">资源和代码</span><span class="sxs-lookup"><span data-stu-id="d0bdb-173">Resources and Code</span></span>](../wpf/advanced/resources-and-code.md)
- [<span data-ttu-id="d0bdb-174">StaticResource 标记扩展</span><span class="sxs-lookup"><span data-stu-id="d0bdb-174">StaticResource Markup Extension</span></span>](../wpf/advanced/staticresource-markup-extension.md)
