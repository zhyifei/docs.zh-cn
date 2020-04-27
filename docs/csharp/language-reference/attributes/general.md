---
title: C# 保留的特性：Conditional, Obsolete, AttributeUsage
ms.date: 04/09/2020
description: 这些特性由编译器解释，以影响编译器生成的代码
ms.openlocfilehash: c6d697dd08233ffc88900949998047137ee170a9
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021761"
---
# <a name="reserved-attributes-conditionalattribute-obsoleteattribute-attributeusageattribute"></a><span data-ttu-id="82a64-103">保留的特性：ConditionalAttribute, ObsoleteAttribute, AttributeUsageAttribute</span><span class="sxs-lookup"><span data-stu-id="82a64-103">Reserved attributes: ConditionalAttribute, ObsoleteAttribute, AttributeUsageAttribute</span></span>

<span data-ttu-id="82a64-104">这些特性可应用于代码中的元素。</span><span class="sxs-lookup"><span data-stu-id="82a64-104">These attributes can be applied to elements in your code.</span></span> <span data-ttu-id="82a64-105">它们为这些元素添加语义。</span><span class="sxs-lookup"><span data-stu-id="82a64-105">They add semantic meaning to those elements.</span></span> <span data-ttu-id="82a64-106">编译器使用这些语义来更改其输出，并报告使用你的代码的开发人员可能犯的错误。</span><span class="sxs-lookup"><span data-stu-id="82a64-106">The compiler uses those semantic meanings to alter its output and report possible mistakes by developers using your code.</span></span>

## <a name="conditional-attribute"></a><span data-ttu-id="82a64-107">`Conditional` 特性</span><span class="sxs-lookup"><span data-stu-id="82a64-107">`Conditional` attribute</span></span>

<span data-ttu-id="82a64-108">`Conditional` 特性使得方法执行依赖于预处理标识符。</span><span class="sxs-lookup"><span data-stu-id="82a64-108">The `Conditional` attribute makes the execution of a method dependent on a preprocessing identifier.</span></span> <span data-ttu-id="82a64-109">`Conditional` 属性是 <xref:System.Diagnostics.ConditionalAttribute> 的别名，可以应用于方法或特性类。</span><span class="sxs-lookup"><span data-stu-id="82a64-109">The `Conditional` attribute is an alias for <xref:System.Diagnostics.ConditionalAttribute>, and can be applied to a method or an attribute class.</span></span>

<span data-ttu-id="82a64-110">在以下示例中，`Conditional` 应用于启用或禁用显示特定于程序的诊断信息的方法：</span><span class="sxs-lookup"><span data-stu-id="82a64-110">In the following example, `Conditional` is applied to a method to enable or disable the display of program-specific diagnostic information:</span></span>

:::code language="csharp" source="snippets/trace.cs" interactive="try-dotnet" :::

<span data-ttu-id="82a64-111">如果未定义 `TRACE_ON` 标识符，则不会显示跟踪输出。</span><span class="sxs-lookup"><span data-stu-id="82a64-111">If the `TRACE_ON` identifier isn't defined, the trace output isn't displayed.</span></span> <span data-ttu-id="82a64-112">在交互式窗口中自己探索。</span><span class="sxs-lookup"><span data-stu-id="82a64-112">Explore for yourself in the interactive window.</span></span>

<span data-ttu-id="82a64-113">`Conditional` 特性通常与 `DEBUG` 标识符一起使用，以启用调试生成（而非发布生成）中的跟踪和日志记录功能，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="82a64-113">The `Conditional` attribute is often used with the `DEBUG` identifier to enable trace and logging features for debug builds but not in release builds, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetConditional" :::

<span data-ttu-id="82a64-114">当调用标记为条件的方法时，指定的预处理符号是否存在将决定是包含还是省略该调用。</span><span class="sxs-lookup"><span data-stu-id="82a64-114">When a method marked conditional is called, the presence or absence of the specified preprocessing symbol determines whether the call is included or omitted.</span></span> <span data-ttu-id="82a64-115">如果定义了符号，则将包括调用；否则，将忽略该调用。</span><span class="sxs-lookup"><span data-stu-id="82a64-115">If the symbol is defined, the call is included; otherwise, the call is omitted.</span></span> <span data-ttu-id="82a64-116">条件方法必须是类或结构声明中的方法，而且必须具有 `void` 返回类型。</span><span class="sxs-lookup"><span data-stu-id="82a64-116">A conditional method must be a method in a class or struct declaration and must have a `void` return type.</span></span> <span data-ttu-id="82a64-117">与将方法封闭在 `#if…#endif` 块内相比，`Conditional` 更简洁且较不容易出错。</span><span class="sxs-lookup"><span data-stu-id="82a64-117">Using `Conditional` is cleaner, more elegant, and less error-prone than enclosing methods inside `#if…#endif` blocks.</span></span>

<span data-ttu-id="82a64-118">如果某个方法具有多个 `Conditional` 特性，则如果定义了一个或多个条件符号（通过使用 OR 运算符将这些符号逻辑链接在一起），则包含对该方法的调用。</span><span class="sxs-lookup"><span data-stu-id="82a64-118">If a method has multiple `Conditional` attributes, a call to the method is included if at one or more conditional symbols is defined (the symbols are logically linked together by using the OR operator).</span></span> <span data-ttu-id="82a64-119">在以下示例中，存在 `A` 或 `B` 将导致方法调用：</span><span class="sxs-lookup"><span data-stu-id="82a64-119">In the following example, the presence of either `A` or `B` results in a method call:</span></span>

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetMultipleConditions" :::

### <a name="using-conditional-with-attribute-classes"></a><span data-ttu-id="82a64-120">使用带有特性类的 `Conditional`</span><span class="sxs-lookup"><span data-stu-id="82a64-120">Using `Conditional` with attribute classes</span></span>

<span data-ttu-id="82a64-121">`Conditional` 特性还可应用于特性类定义。</span><span class="sxs-lookup"><span data-stu-id="82a64-121">The `Conditional` attribute can also be applied to an attribute class definition.</span></span> <span data-ttu-id="82a64-122">在以下示例中，如果定义了 `DEBUG`，则自定义特性 `Documentation` 将仅向元数据添加信息。</span><span class="sxs-lookup"><span data-stu-id="82a64-122">In the following example, the custom attribute `Documentation` will only add information to the metadata if `DEBUG` is defined.</span></span>

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetConditionalConditionalAttribute" :::

## <a name="obsolete-attribute"></a><span data-ttu-id="82a64-123">`Obsolete` 特性</span><span class="sxs-lookup"><span data-stu-id="82a64-123">`Obsolete` attribute</span></span>

<span data-ttu-id="82a64-124">`Obsolete` 特性将代码元素标记为不再推荐使用。</span><span class="sxs-lookup"><span data-stu-id="82a64-124">The `Obsolete` attribute marks a code element as no longer recommended for use.</span></span> <span data-ttu-id="82a64-125">使用标记为已过时的实体会生成警告或错误。</span><span class="sxs-lookup"><span data-stu-id="82a64-125">Use of an entity marked obsolete generates a warning or an error.</span></span> <span data-ttu-id="82a64-126">`Obsolete` 特性是一次性特性，可以应用于任何允许特性的实体。</span><span class="sxs-lookup"><span data-stu-id="82a64-126">The `Obsolete` attribute is a single-use attribute and can be applied to any entity that allows attributes.</span></span> <span data-ttu-id="82a64-127">`Obsolete` 是 <xref:System.ObsoleteAttribute> 的别名。</span><span class="sxs-lookup"><span data-stu-id="82a64-127">`Obsolete` is an alias for <xref:System.ObsoleteAttribute>.</span></span>

<span data-ttu-id="82a64-128">在以下示例中，`Obsolete` 特性应用于类 `A` 和方法 `B.OldMethod`。</span><span class="sxs-lookup"><span data-stu-id="82a64-128">In the following example the `Obsolete` attribute is applied to class `A` and to method `B.OldMethod`.</span></span> <span data-ttu-id="82a64-129">因为应用于 `B.OldMethod` 的特性构造函数的第二个参数设置为 `true`，所以此方法将导致编译器错误，而使用类 `A` 只会生成警告。</span><span class="sxs-lookup"><span data-stu-id="82a64-129">Because the second argument of the attribute constructor applied to `B.OldMethod` is set to `true`, this method will cause a compiler error, whereas using class `A` will just produce a warning.</span></span> <span data-ttu-id="82a64-130">但是，调用 `B.NewMethod` 不会生成任何警告或错误。</span><span class="sxs-lookup"><span data-stu-id="82a64-130">Calling `B.NewMethod`, however, produces no warning or error.</span></span> <span data-ttu-id="82a64-131">例如，将其与先前的定义一起使用时，以下代码会生成两个警告和一个错误：</span><span class="sxs-lookup"><span data-stu-id="82a64-131">For example, when you use it with the previous definitions, the following code generates two warnings and one error:</span></span>

:::code language="csharp" source="snippets/ObsoleteExample.cs" interactive="try-dotnet" :::

<span data-ttu-id="82a64-132">作为特性构造函数的第一个参数提供的字符串将作为警告或错误的一部分显示。</span><span class="sxs-lookup"><span data-stu-id="82a64-132">The string provided as the first argument to the attribute constructor will be displayed as part of the warning or error.</span></span> <span data-ttu-id="82a64-133">将生成类 `A` 的两个警告：一个用于声明类引用，另一个用于类构造函数。</span><span class="sxs-lookup"><span data-stu-id="82a64-133">Two warnings for class `A` are generated: one for the declaration of the class reference, and one for the class constructor.</span></span> <span data-ttu-id="82a64-134">`Obsolete` 特性可以在不带参数的情况下使用，但建议说明改为使用哪个项目。</span><span class="sxs-lookup"><span data-stu-id="82a64-134">The `Obsolete` attribute can be used without arguments, but including an explanation what to use instead is recommended.</span></span>

## <a name="attributeusage-attribute"></a><span data-ttu-id="82a64-135">`AttributeUsage` 特性</span><span class="sxs-lookup"><span data-stu-id="82a64-135">`AttributeUsage` attribute</span></span>

<span data-ttu-id="82a64-136">`AttributeUsage` 特性确定自定义特性类的使用方式。</span><span class="sxs-lookup"><span data-stu-id="82a64-136">The `AttributeUsage` attribute determines how a custom attribute class can be used.</span></span> <span data-ttu-id="82a64-137"><xref:System.AttributeUsageAttribute> 是应用到自定义特性定义的特性。</span><span class="sxs-lookup"><span data-stu-id="82a64-137"><xref:System.AttributeUsageAttribute> is an attribute you apply to custom attribute definitions.</span></span> <span data-ttu-id="82a64-138">`AttributeUsage` 特性帮助控制：</span><span class="sxs-lookup"><span data-stu-id="82a64-138">The `AttributeUsage` attribute enables you to control:</span></span>

- <span data-ttu-id="82a64-139">可能应用到的具体程序元素特性。</span><span class="sxs-lookup"><span data-stu-id="82a64-139">Which program elements attribute may be applied to.</span></span> <span data-ttu-id="82a64-140">除非使用限制，否则特性可能应用到以下任意程序元素：</span><span class="sxs-lookup"><span data-stu-id="82a64-140">Unless you restrict its usage, an attribute may be applied to any of the following program elements:</span></span>
  - <span data-ttu-id="82a64-141">程序集 (assembly)</span><span class="sxs-lookup"><span data-stu-id="82a64-141">assembly</span></span>
  - <span data-ttu-id="82a64-142">name</span><span class="sxs-lookup"><span data-stu-id="82a64-142">module</span></span>
  - <span data-ttu-id="82a64-143">field</span><span class="sxs-lookup"><span data-stu-id="82a64-143">field</span></span>
  - <span data-ttu-id="82a64-144">event</span><span class="sxs-lookup"><span data-stu-id="82a64-144">event</span></span>
  - <span data-ttu-id="82a64-145">method</span><span class="sxs-lookup"><span data-stu-id="82a64-145">method</span></span>
  - <span data-ttu-id="82a64-146">param</span><span class="sxs-lookup"><span data-stu-id="82a64-146">param</span></span>
  - <span data-ttu-id="82a64-147">property</span><span class="sxs-lookup"><span data-stu-id="82a64-147">property</span></span>
  - <span data-ttu-id="82a64-148">return</span><span class="sxs-lookup"><span data-stu-id="82a64-148">return</span></span>
  - <span data-ttu-id="82a64-149">type</span><span class="sxs-lookup"><span data-stu-id="82a64-149">type</span></span>
- <span data-ttu-id="82a64-150">某特性是否可多次应用于单个程序元素。</span><span class="sxs-lookup"><span data-stu-id="82a64-150">Whether an attribute can be applied to a single program element multiple times.</span></span>
- <span data-ttu-id="82a64-151">特性是否由派生类继承。</span><span class="sxs-lookup"><span data-stu-id="82a64-151">Whether attributes are inherited by derived classes.</span></span>

<span data-ttu-id="82a64-152">显式应用时，默认设置如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="82a64-152">The default settings look like the following example when applied explicitly:</span></span>

:::code language="csharp" source="snippets/NewAttribute.cs" id="SnippetUsageFirst" :::

<span data-ttu-id="82a64-153">在此示例中，`NewAttribute` 类可应用于任何受支持的程序元素。</span><span class="sxs-lookup"><span data-stu-id="82a64-153">In this example, the `NewAttribute` class can be applied to any supported program element.</span></span> <span data-ttu-id="82a64-154">但是它对每个实体仅能应用一次。</span><span class="sxs-lookup"><span data-stu-id="82a64-154">But it can be applied only once to each entity.</span></span> <span data-ttu-id="82a64-155">特性应用于基类时，它由派生类继承。</span><span class="sxs-lookup"><span data-stu-id="82a64-155">The attribute is inherited by derived classes when applied to a base class.</span></span>

<span data-ttu-id="82a64-156"><xref:System.AttributeUsageAttribute.AllowMultiple> 和 <xref:System.AttributeUsageAttribute.Inherited> 参数是可选的，因此以下代码具有相同效果：</span><span class="sxs-lookup"><span data-stu-id="82a64-156">The <xref:System.AttributeUsageAttribute.AllowMultiple> and <xref:System.AttributeUsageAttribute.Inherited> arguments are optional, so the following code has the same effect:</span></span>

:::code language="csharp" source="snippets/NewAttribute.cs" id="SnippetUsageSecond" :::

<span data-ttu-id="82a64-157">第一个 <xref:System.AttributeUsageAttribute> 参数必须是 <xref:System.AttributeTargets> 枚举的一个或多个元素。</span><span class="sxs-lookup"><span data-stu-id="82a64-157">The first <xref:System.AttributeUsageAttribute> argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="82a64-158">可将多个目标类型与 OR 运算符链接在一起，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="82a64-158">Multiple target types can be linked together with the OR operator, like the following example shows:</span></span>

:::code language="csharp" source="snippets/NewPropertyOrFieldAttribute.cs" id="SnippetDefinePropertyAttribute" :::

<span data-ttu-id="82a64-159">从 C# 7.3 开始，特性可应用于自动实现的属性的属性或支持字段。</span><span class="sxs-lookup"><span data-stu-id="82a64-159">Beginning in C# 7.3, attributes can be applied to either the property or the backing field for an auto-implemented property.</span></span> <span data-ttu-id="82a64-160">特性应用于属性，除非在特性上指定 `field` 说明符。</span><span class="sxs-lookup"><span data-stu-id="82a64-160">The attribute applies to the property, unless you specify the `field` specifier on the attribute.</span></span> <span data-ttu-id="82a64-161">都在以下示例中进行了演示：</span><span class="sxs-lookup"><span data-stu-id="82a64-161">Both are shown in the following example:</span></span>

:::code language="csharp" source="snippets/NewPropertyOrFieldAttribute.cs" id="SnippetUsePropertyAttribute" :::

<span data-ttu-id="82a64-162">如果 <xref:System.AttributeUsageAttribute.AllowMultiple> 参数为 `true`，那么结果特性可多次应用于单个实体，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="82a64-162">If the <xref:System.AttributeUsageAttribute.AllowMultiple> argument is `true`, then the resulting attribute can be applied more than once to a single entity, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/MultiUseAttribute.cs" id="SnippetMultiUse" :::

<span data-ttu-id="82a64-163">在本例中，`MultiUseAttribute` 可重复应用，因为 `AllowMultiple` 设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="82a64-163">In this case, `MultiUseAttribute` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="82a64-164">所显示的两种用于应用多个特性的格式均有效。</span><span class="sxs-lookup"><span data-stu-id="82a64-164">Both formats shown for applying multiple attributes are valid.</span></span>

<span data-ttu-id="82a64-165">如果 <xref:System.AttributeUsageAttribute.Inherited> 为 `false`，那么该特性不是由特性类派生的类继承。</span><span class="sxs-lookup"><span data-stu-id="82a64-165">If <xref:System.AttributeUsageAttribute.Inherited> is `false`, then the attribute isn't inherited by classes derived from an attributed class.</span></span> <span data-ttu-id="82a64-166">例如：</span><span class="sxs-lookup"><span data-stu-id="82a64-166">For example:</span></span>

:::code language="csharp" source="snippets/NonInheritedAttribute.cs" id="SnippetNonInherited" :::

<span data-ttu-id="82a64-167">在本例中，`NonInheritedAttribute` 不会通过继承应用于 `DClass`。</span><span class="sxs-lookup"><span data-stu-id="82a64-167">In this case `NonInheritedAttribute` isn't applied to `DClass` via inheritance.</span></span>

## <a name="see-also"></a><span data-ttu-id="82a64-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="82a64-168">See also</span></span>

- <xref:System.Attribute>
- <xref:System.Reflection>
- [<span data-ttu-id="82a64-169">特性</span><span class="sxs-lookup"><span data-stu-id="82a64-169">Attributes</span></span>](../../../standard/attributes/index.md)
- [<span data-ttu-id="82a64-170">反射</span><span class="sxs-lookup"><span data-stu-id="82a64-170">Reflection</span></span>](../../programming-guide/concepts/reflection.md)
