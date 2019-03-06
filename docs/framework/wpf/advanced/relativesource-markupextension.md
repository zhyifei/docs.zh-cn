---
title: RelativeSource MarkupExtension
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: d96a00afc08f2c5593dad5a3a47ab46045ff6b0f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365104"
---
# <a name="relativesource-markupextension"></a><span data-ttu-id="03815-102">RelativeSource MarkupExtension</span><span class="sxs-lookup"><span data-stu-id="03815-102">RelativeSource MarkupExtension</span></span>
<span data-ttu-id="03815-103">指定的属性<xref:System.Windows.Data.RelativeSource>绑定源中使用[绑定标记扩展](binding-markup-extension.md)，或设置时<xref:System.Windows.Data.Binding.RelativeSource%2A>属性<xref:System.Windows.Data.Binding>建立在 XAML 中的元素。</span><span class="sxs-lookup"><span data-stu-id="03815-103">Specifies properties of a <xref:System.Windows.Data.RelativeSource> binding source, to be used within a [Binding Markup Extension](binding-markup-extension.md), or when setting the <xref:System.Windows.Data.Binding.RelativeSource%2A> property of a <xref:System.Windows.Data.Binding> element established in XAML.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="03815-104">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="03815-104">XAML Attribute Usage</span></span>  
  
```xml  
<Binding RelativeSource="{RelativeSource modeEnumValue}" .../>  
```  
  
## <a name="xaml-attribute-usage-nested-within-binding-extension"></a><span data-ttu-id="03815-105">XAML 属性用法（嵌套在 Binding 扩展内）</span><span class="sxs-lookup"><span data-stu-id="03815-105">XAML Attribute Usage (nested within Binding extension)</span></span>  
  
```xml  
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="03815-106">XAML 对象元素用法</span><span class="sxs-lookup"><span data-stu-id="03815-106">XAML Object Element Usage</span></span>  
  
```xml  
<Binding>  
  <Binding.RelativeSource>  
    <RelativeSource Mode="modeEnumValue"/>  
  </Binding.RelativeSource>  
</Binding>  
```
<span data-ttu-id="03815-107">或</span><span class="sxs-lookup"><span data-stu-id="03815-107">-or-</span></span>  
```xml
<Binding>  
  <Binding.RelativeSource>  
    <RelativeSource  
      Mode="FindAncestor"  
      AncestorType="{x:Type typeName}"  
      AncestorLevel="intLevel"  
    />  
  </Binding.RelativeSource>  
</Binding>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="03815-108">XAML 值</span><span class="sxs-lookup"><span data-stu-id="03815-108">XAML Values</span></span>  
  
|||  
|-|-|  
|`modeEnumValue`|<span data-ttu-id="03815-109">以下项之一：</span><span class="sxs-lookup"><span data-stu-id="03815-109">One of the following:</span></span><br /><br /> <span data-ttu-id="03815-110">字符串标记`Self`; 对应于<xref:System.Windows.Data.RelativeSource>创建具有其<xref:System.Windows.Data.RelativeSource.Mode%2A>属性设置为<xref:System.Windows.Data.RelativeSourceMode.Self>。</span><span class="sxs-lookup"><span data-stu-id="03815-110">-   The string token `Self`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.Self>.</span></span><br /><span data-ttu-id="03815-111">字符串标记`TemplatedParent`; 对应于<xref:System.Windows.Data.RelativeSource>创建具有其<xref:System.Windows.Data.RelativeSource.Mode%2A>属性设置为<xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>。</span><span class="sxs-lookup"><span data-stu-id="03815-111">-   The string token `TemplatedParent`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.</span></span><br /><span data-ttu-id="03815-112">字符串标记`PreviousData`; 对应于<xref:System.Windows.Data.RelativeSource>创建具有其<xref:System.Windows.Data.RelativeSource.Mode%2A>属性设置为<xref:System.Windows.Data.RelativeSourceMode.PreviousData>。</span><span class="sxs-lookup"><span data-stu-id="03815-112">-   The string token `PreviousData`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.</span></span><br /><span data-ttu-id="03815-113">-请参阅下面的信息有关`FindAncestor`模式。</span><span class="sxs-lookup"><span data-stu-id="03815-113">-   See below for information on `FindAncestor` mode.</span></span>|  
|`FindAncestor`|<span data-ttu-id="03815-114">字符串标记 `FindAncestor`。</span><span class="sxs-lookup"><span data-stu-id="03815-114">The string token `FindAncestor`.</span></span> <span data-ttu-id="03815-115">使用此标记可输入一个模式，以便 `RelativeSource` 指定上级类型和可选的上级级别。</span><span class="sxs-lookup"><span data-stu-id="03815-115">Using this token enters a mode whereby a `RelativeSource` specifies an ancestor type and optionally an ancestor level.</span></span> <span data-ttu-id="03815-116">它对应于通过将 <xref:System.Windows.Data.RelativeSource> 属性设置为 <xref:System.Windows.Data.RelativeSource.Mode%2A> 而创建的 <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>。</span><span class="sxs-lookup"><span data-stu-id="03815-116">This corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.</span></span>|  
|`typeName`|<span data-ttu-id="03815-117">对于 `FindAncestor` 模式是必需的。</span><span class="sxs-lookup"><span data-stu-id="03815-117">Required for `FindAncestor` mode.</span></span> <span data-ttu-id="03815-118">类型的名称，用于填充 <xref:System.Windows.Data.RelativeSource.AncestorType%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="03815-118">The name of a type, which fills the <xref:System.Windows.Data.RelativeSource.AncestorType%2A> property.</span></span>|  
|`intLevel`|<span data-ttu-id="03815-119">对于 `FindAncestor` 模式是可选的。</span><span class="sxs-lookup"><span data-stu-id="03815-119">Optional for `FindAncestor` mode.</span></span> <span data-ttu-id="03815-120">上级级别（在逻辑树中向父级方向计算）。</span><span class="sxs-lookup"><span data-stu-id="03815-120">An ancestor level (evaluated towards the parent direction in the logical tree).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03815-121">备注</span><span class="sxs-lookup"><span data-stu-id="03815-121">Remarks</span></span>  
 <span data-ttu-id="03815-122">`{RelativeSource TemplatedParent}` 绑定用法是一项关键技术的一大概念的控件的用户界面和控件的逻辑分离。</span><span class="sxs-lookup"><span data-stu-id="03815-122">`{RelativeSource TemplatedParent}` binding usages are a key technique that addresses a larger concept of the separation of a control's UI and a control's logic.</span></span> <span data-ttu-id="03815-123">这可以实现从模板定义内绑定到模板化父级（在其中应用模板的运行时对象实例）。</span><span class="sxs-lookup"><span data-stu-id="03815-123">This enables binding from within the template definition to the templated parent (the run time object instance where the template is applied).</span></span> <span data-ttu-id="03815-124">这种情况下， [TemplateBinding 标记扩展](templatebinding-markup-extension.md)实际上是以下绑定表达式的简写形式： `{Binding RelativeSource={RelativeSource TemplatedParent}}`。</span><span class="sxs-lookup"><span data-stu-id="03815-124">For this case, the [TemplateBinding Markup Extension](templatebinding-markup-extension.md) is in fact a shorthand for the following binding expression: `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span></span> <span data-ttu-id="03815-125">`TemplateBinding` 或`{RelativeSource TemplatedParent}`用法都仅定义了一个模板 XAML 内部适用。</span><span class="sxs-lookup"><span data-stu-id="03815-125">`TemplateBinding` or `{RelativeSource TemplatedParent}` usages are both only relevant within the XAML that defines a template.</span></span> <span data-ttu-id="03815-126">有关详细信息，请参阅[TemplateBinding 标记扩展](templatebinding-markup-extension.md)</span><span class="sxs-lookup"><span data-stu-id="03815-126">For more information, see [TemplateBinding Markup Extension](templatebinding-markup-extension.md)</span></span>  
  
 <span data-ttu-id="03815-127">`{RelativeSource FindAncestor}` 主要用于控件模板或可预测的自包含的 UI 组合，其中一个控件始终应位于某个上级类型的可视树的情况。</span><span class="sxs-lookup"><span data-stu-id="03815-127">`{RelativeSource FindAncestor}` is mainly used in control templates or predictable self-contained UI compositions, for cases where a control is always expected to be in a visual tree of a certain ancestor type.</span></span> <span data-ttu-id="03815-128">例如，项控件的项可能使用 `FindAncestor` 用法绑定到其项控件父级/祖先级。</span><span class="sxs-lookup"><span data-stu-id="03815-128">For example, items of an items control might use `FindAncestor` usages to bind to properties of their items control parent ancestor.</span></span> <span data-ttu-id="03815-129">或者，属于模板中控件组合一部分的元素可使用 `FindAncestor` 绑定到同一组合结构中的父元素。</span><span class="sxs-lookup"><span data-stu-id="03815-129">Or, elements that are part of control composition in a template can use `FindAncestor` bindings to the parent elements in that same composition structure.</span></span>  
  
 <span data-ttu-id="03815-130">在 XAML 语法章节显示的 `FindAncestor` 模式的对象元素语法中，第二个对象元素语法专门用于 `FindAncestor` 模式。</span><span class="sxs-lookup"><span data-stu-id="03815-130">In the object element syntax for `FindAncestor` mode shown in the XAML Syntax sections, the second object element syntax is used specifically for `FindAncestor` mode.</span></span> <span data-ttu-id="03815-131">`FindAncestor` 模式需要 <xref:System.Windows.Data.RelativeSource.AncestorType%2A> 值。</span><span class="sxs-lookup"><span data-stu-id="03815-131">`FindAncestor` mode requires an <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value.</span></span> <span data-ttu-id="03815-132">必须设置<xref:System.Windows.Data.RelativeSource.AncestorType%2A>作为属性使用[X:type 标记扩展](../../xaml-services/x-type-markup-extension.md)要查找的上级节点的类型引用。</span><span class="sxs-lookup"><span data-stu-id="03815-132">You must set <xref:System.Windows.Data.RelativeSource.AncestorType%2A> as an attribute using an [x:Type Markup Extension](../../xaml-services/x-type-markup-extension.md) reference to the type of ancestor to look for.</span></span> <span data-ttu-id="03815-133">当在运行时处理绑定请求时，将会用到 <xref:System.Windows.Data.RelativeSource.AncestorType%2A> 值。</span><span class="sxs-lookup"><span data-stu-id="03815-133">The <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value is used when the binding request is processed at run-time.</span></span>  
  
 <span data-ttu-id="03815-134">对于 `FindAncestor` 模式，当元素树中可能存在多个该类型的上级时，可以使用可选属性 <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> 帮助消除上级查找的歧义。</span><span class="sxs-lookup"><span data-stu-id="03815-134">For `FindAncestor` mode, the optional property <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> can help disambiguate the ancestor lookup in cases where there is possibly more than one ancestor of that type existing in the element tree.</span></span>  
  
 <span data-ttu-id="03815-135">有关如何使用 `FindAncestor` 模式的详细信息，请参阅 <xref:System.Windows.Data.RelativeSource>。</span><span class="sxs-lookup"><span data-stu-id="03815-135">For more information on how to use the `FindAncestor` mode, see <xref:System.Windows.Data.RelativeSource>.</span></span>  
  
 <span data-ttu-id="03815-136">`{RelativeSource Self}` 适用于方案这两个属性之间的一个实例属性应依赖于同一个实例，并 （如强制） 任何一般依赖属性关系的另一个属性的值已存在。</span><span class="sxs-lookup"><span data-stu-id="03815-136">`{RelativeSource Self}` is useful for scenarios where one property of an instance should depend on the value of another property of the same instance, and no general dependency property relationship (such as coercion) already exists between those two properties.</span></span> <span data-ttu-id="03815-137">虽然很少见，对象上存在两个属性值可以说完全相同 （并以相同方式键入），您还可以应用`Converter`具有一个绑定到参数`{RelativeSource Self}`，并使用此转换器转换源之间和目标类型。</span><span class="sxs-lookup"><span data-stu-id="03815-137">Although it is rare that two properties exist on an object such that the values are literally identical (and are identically typed), you can also apply a `Converter` parameter to a binding that has `{RelativeSource Self}`, and use the converter to convert between source and target types.</span></span> <span data-ttu-id="03815-138">另一方案`{RelativeSource Self}`作为的一部分是<xref:System.Windows.MultiDataTrigger>。</span><span class="sxs-lookup"><span data-stu-id="03815-138">Another scenario for `{RelativeSource Self}` is as part of a <xref:System.Windows.MultiDataTrigger>.</span></span>  
  
 <span data-ttu-id="03815-139">例如，以下 XAML 定义了一个 <xref:System.Windows.Shapes.Rectangle> 元素，以便无论为 <xref:System.Windows.FrameworkElement.Width%2A> 输入什么值，都确保 <xref:System.Windows.Shapes.Rectangle> 始终是一个方形：`<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span><span class="sxs-lookup"><span data-stu-id="03815-139">For example, the following XAML defines a <xref:System.Windows.Shapes.Rectangle> element such that no matter what value is entered for <xref:System.Windows.FrameworkElement.Width%2A>, the <xref:System.Windows.Shapes.Rectangle> is always a square: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span></span>  
  
 <span data-ttu-id="03815-140">`{RelativeSource PreviousData}` 数据模板中或在其中绑定将使用集合作为数据源的情况下非常有用。</span><span class="sxs-lookup"><span data-stu-id="03815-140">`{RelativeSource PreviousData}` is useful either in data templates, or in cases where bindings are using a collection as the data source.</span></span> <span data-ttu-id="03815-141">可以使用`{RelativeSource PreviousData}`以突出显示集合中相邻数据项之间的关系。</span><span class="sxs-lookup"><span data-stu-id="03815-141">You can use `{RelativeSource PreviousData}` to highlight relationships between adjacent data items in the collection.</span></span> <span data-ttu-id="03815-142">相关技术是在数据源中的当前项和前一个项之间建立 <xref:System.Windows.Data.MultiBinding>，并使用此绑定上的转换器来确定这两个项及其属性的差异。</span><span class="sxs-lookup"><span data-stu-id="03815-142">A related technique is to establish a <xref:System.Windows.Data.MultiBinding> between the current and previous items in the data source, and use a converter on that binding to determine the difference between the two items and their properties.</span></span>  
  
 <span data-ttu-id="03815-143">在下面的示例中，项目模板中的第一个 <xref:System.Windows.Controls.TextBlock> 可显示当前编号。</span><span class="sxs-lookup"><span data-stu-id="03815-143">In the following example, the first <xref:System.Windows.Controls.TextBlock> in the items template displays the current number.</span></span> <span data-ttu-id="03815-144">第二个<xref:System.Windows.Controls.TextBlock>绑定<xref:System.Windows.Data.MultiBinding>，名义上有两个<xref:System.Windows.Data.Binding>构成要素： 当前记录，并刻意采用前一个数据记录使用的绑定`{RelativeSource PreviousData}`。</span><span class="sxs-lookup"><span data-stu-id="03815-144">The second <xref:System.Windows.Controls.TextBlock> binding is a <xref:System.Windows.Data.MultiBinding> that nominally has two <xref:System.Windows.Data.Binding> consistuents: the current record, and a binding that deliberately uses the previous data record by using `{RelativeSource PreviousData}`.</span></span> <span data-ttu-id="03815-145">然后，<xref:System.Windows.Data.MultiBinding> 上的转换器将计算差异，并将其返回到绑定。</span><span class="sxs-lookup"><span data-stu-id="03815-145">Then, a converter on the <xref:System.Windows.Data.MultiBinding> calculates the difference and returns it to the binding.</span></span>  
  
```xml  
<ListBox Name="fibolist">  
    <ListBox.ItemTemplate>  
        <DataTemplate>  
            <StackPanel Orientation="Horizontal">  
            <TextBlock Text="{Binding}"/>  
            <TextBlock>, difference = </TextBlock>  
                <TextBlock>  
                    <TextBlock.Text>  
                        <MultiBinding Converter="{StaticResource DiffConverter}">  
                            <Binding/>  
                            <Binding RelativeSource="{RelativeSource PreviousData}"/>  
                        </MultiBinding>  
                    </TextBlock.Text>  
                </TextBlock>  
            </StackPanel>  
        </DataTemplate>  
    </ListBox.ItemTemplate>  
```  
  
 <span data-ttu-id="03815-146">数据绑定概念未在此处，请参阅[数据绑定概述](../data/data-binding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="03815-146">Describing data binding as a concept is not covered here, see [Data Binding Overview](../data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="03815-147">在中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]XAML 处理器实现中，对此标记扩展的处理由定义<xref:System.Windows.Data.RelativeSource>类。</span><span class="sxs-lookup"><span data-stu-id="03815-147">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.Data.RelativeSource> class.</span></span>  
  
 <span data-ttu-id="03815-148">`RelativeSource` 是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="03815-148">`RelativeSource` is a markup extension.</span></span> <span data-ttu-id="03815-149">当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。</span><span class="sxs-lookup"><span data-stu-id="03815-149">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="03815-150">在 XAML 使用的所有标记扩展`{`和`}`约定所依据的 XAML 处理器识别标记扩展必须处理该属性其特性语法中的字符。</span><span class="sxs-lookup"><span data-stu-id="03815-150">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="03815-151">有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="03815-151">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03815-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="03815-152">See also</span></span>
- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="03815-153">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="03815-153">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="03815-154">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="03815-154">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="03815-155">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="03815-155">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="03815-156">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="03815-156">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="03815-157">绑定声明概述</span><span class="sxs-lookup"><span data-stu-id="03815-157">Binding Declarations Overview</span></span>](../data/binding-declarations-overview.md)
- [<span data-ttu-id="03815-158">x:Type 标记扩展</span><span class="sxs-lookup"><span data-stu-id="03815-158">x:Type Markup Extension</span></span>](../../xaml-services/x-type-markup-extension.md)
