---
title: TemplateBinding 标记扩展
ms.date: 03/30/2017
f1_keywords:
- TemplateBinding
- TemplateBindingExtension
helpviewer_keywords:
- XAML [WPF], TemplateBinding markup extension
- TemplateBinding markup extensions [WPF]
ms.assetid: 1d25bbfc-dbc2-499d-9f12-419d23d4ac6a
ms.openlocfilehash: 8cebbf717f66b072bc84b2068193ff2fe76ea87b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187284"
---
# <a name="templatebinding-markup-extension"></a><span data-ttu-id="03293-102">TemplateBinding 标记扩展</span><span class="sxs-lookup"><span data-stu-id="03293-102">TemplateBinding Markup Extension</span></span>
<span data-ttu-id="03293-103">连接某一控件模板中的属性值，使之成为模板化控件上另一个属性的值。</span><span class="sxs-lookup"><span data-stu-id="03293-103">Links the value of a property in a control template to be the value of another property on the templated control.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="03293-104">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="03293-104">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-attribute-usage-for-setter-property-in-template-or-style"></a><span data-ttu-id="03293-105">XAML 特性用法（适用于模板或样式的 Setter 属性）</span><span class="sxs-lookup"><span data-stu-id="03293-105">XAML Attribute Usage (for Setter property in template or style)</span></span>  
  
```xml  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="03293-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="03293-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`propertyName`|<span data-ttu-id="03293-107">在资源库语法中设置的属性的 <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="03293-107"><xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> of the property being set in the setter syntax.</span></span>|  
|`sourceProperty`|<span data-ttu-id="03293-108">另一个在要模板化的类型上存在的依赖项属性，由其 <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> 来指定。</span><span class="sxs-lookup"><span data-stu-id="03293-108">Another dependency property that exists on the type being templated, specified by its <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.</span></span><br /><br /> <span data-ttu-id="03293-109">- 或 -</span><span class="sxs-lookup"><span data-stu-id="03293-109">- or -</span></span><br /><br /> <span data-ttu-id="03293-110">由要模板化的目标类型之外的类型所定义的“dotted-down”属性名称。</span><span class="sxs-lookup"><span data-stu-id="03293-110">A "dotted-down" property name that is defined by a different type than the target type being templated.</span></span> <span data-ttu-id="03293-111">这实际上是 <xref:System.Windows.PropertyPath>。</span><span class="sxs-lookup"><span data-stu-id="03293-111">This is actually a <xref:System.Windows.PropertyPath>.</span></span> <span data-ttu-id="03293-112">请参阅[属性路径 XAML 语法](propertypath-xaml-syntax.md)。</span><span class="sxs-lookup"><span data-stu-id="03293-112">See [PropertyPath XAML Syntax](propertypath-xaml-syntax.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03293-113">备注</span><span class="sxs-lookup"><span data-stu-id="03293-113">Remarks</span></span>  
 <span data-ttu-id="03293-114">A`TemplateBinding`是模板方案[绑定](binding-markup-extension.md)的优化形式，类似于 使用`Binding``{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=OneWay}`构造的 绑定。</span><span class="sxs-lookup"><span data-stu-id="03293-114">A `TemplateBinding` is an optimized form of a [Binding](binding-markup-extension.md) for template scenarios, analogous to a `Binding` constructed with `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=OneWay}`.</span></span> <span data-ttu-id="03293-115">`TemplateBinding` 始终为单向绑定，即使所涉及的属性默认为双向绑定。</span><span class="sxs-lookup"><span data-stu-id="03293-115">A `TemplateBinding` is always a one-way binding, even if properties involved default to two-way binding.</span></span> <span data-ttu-id="03293-116">所涉及的两个属性都必须是依赖项属性。</span><span class="sxs-lookup"><span data-stu-id="03293-116">Both properties involved must be dependency properties.</span></span> <span data-ttu-id="03293-117">为了实现对模板化父级的双向绑定，请使用`{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`以下绑定语句。</span><span class="sxs-lookup"><span data-stu-id="03293-117">In order to achieve two-way binding to a templated parent use the following binding statement instead `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`.</span></span>
  
 <span data-ttu-id="03293-118">[相对源](relativesource-markupextension.md)是另一个标记扩展，有时用于与模板中执行相对属性绑定`TemplateBinding`，而不是一起使用。</span><span class="sxs-lookup"><span data-stu-id="03293-118">[RelativeSource](relativesource-markupextension.md) is another markup extension that is sometimes used in conjunction with or instead of `TemplateBinding` in order to perform relative property binding within a template.</span></span>  
  
 <span data-ttu-id="03293-119">此处未介绍将控件模板描述为概念;有关详细信息，请参阅[控件样式和模板](../controls/control-styles-and-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="03293-119">Describing control templates as a concept is not covered here; for more information, see [Control Styles and Templates](../controls/control-styles-and-templates.md).</span></span>  
  
 <span data-ttu-id="03293-120">特性语法是最常用于该标记扩展的语法。</span><span class="sxs-lookup"><span data-stu-id="03293-120">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="03293-121">在 `TemplateBinding` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.TemplateBindingExtension.Property%2A> 扩展类的 <xref:System.Windows.TemplateBindingExtension> 值。</span><span class="sxs-lookup"><span data-stu-id="03293-121">The string token provided after the `TemplateBinding` identifier string is assigned as the <xref:System.Windows.TemplateBindingExtension.Property%2A> value of the underlying <xref:System.Windows.TemplateBindingExtension> extension class.</span></span>  
  
 <span data-ttu-id="03293-122">对象元素语法也可行，但因为没有实际的应用，所以未进行演示。</span><span class="sxs-lookup"><span data-stu-id="03293-122">Object element syntax is possible, but it is not shown because it has no realistic application.</span></span> <span data-ttu-id="03293-123">`TemplateBinding` 用于使用计算的表达式来填充资源库内的值，因此使用 `TemplateBinding` 的对象元素语法来填充 `<Setter.Property>` 属性元素语法就会变得繁冗而多余。</span><span class="sxs-lookup"><span data-stu-id="03293-123">`TemplateBinding` is used to fill values within setters, using evaluated expressions, and using object element syntax for `TemplateBinding` to fill `<Setter.Property>` property element syntax is unnecessarily verbose.</span></span>  
  
 <span data-ttu-id="03293-124">`TemplateBinding` 还可以在详细特性用法中使用，以便将 <xref:System.Windows.TemplateBindingExtension.Property%2A> 属性指定为一个 property=value 对：</span><span class="sxs-lookup"><span data-stu-id="03293-124">`TemplateBinding` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.TemplateBindingExtension.Property%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 <span data-ttu-id="03293-125">如果扩展具有一个以上的可设置属性，或者某些属性是可选的，则详细用法通常会很有用。</span><span class="sxs-lookup"><span data-stu-id="03293-125">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="03293-126">由于 `TemplateBinding` 仅有一个可设置的属性，并且此属性是必需的，因此该详细用法不具有典型性。</span><span class="sxs-lookup"><span data-stu-id="03293-126">Because `TemplateBinding` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="03293-127">在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]XAML 处理器实现中，此标记扩展的处理由<xref:System.Windows.TemplateBindingExtension>类定义。</span><span class="sxs-lookup"><span data-stu-id="03293-127">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.TemplateBindingExtension> class.</span></span>  
  
 <span data-ttu-id="03293-128">`TemplateBinding` 是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="03293-128">`TemplateBinding` is a markup extension.</span></span> <span data-ttu-id="03293-129">当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。</span><span class="sxs-lookup"><span data-stu-id="03293-129">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="03293-130">XAML 中的所有标记扩展在其属性语法中使用`{``}`和 字符，这是 XAML 处理器识别标记扩展必须处理该属性的约定。</span><span class="sxs-lookup"><span data-stu-id="03293-130">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="03293-131">有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="03293-131">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03293-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="03293-132">See also</span></span>

- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="03293-133">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="03293-133">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="03293-134">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="03293-134">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="03293-135">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="03293-135">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="03293-136">RelativeSource MarkupExtension</span><span class="sxs-lookup"><span data-stu-id="03293-136">RelativeSource MarkupExtension</span></span>](relativesource-markupextension.md)
- [<span data-ttu-id="03293-137">Binding 标记扩展</span><span class="sxs-lookup"><span data-stu-id="03293-137">Binding Markup Extension</span></span>](binding-markup-extension.md)
