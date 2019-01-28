---
title: AttributeUsage (C#)
ms.date: 04/25/2018
ms.openlocfilehash: a3a82e33d7259ec56ec3e907bc3d4d9f8a01167d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589303"
---
# <a name="attributeusage-c"></a><span data-ttu-id="8ad34-102">AttributeUsage (C#)</span><span class="sxs-lookup"><span data-stu-id="8ad34-102">AttributeUsage (C#)</span></span>

<span data-ttu-id="8ad34-103">确定如何使用自定义特性类。</span><span class="sxs-lookup"><span data-stu-id="8ad34-103">Determines how a custom attribute class can be used.</span></span> <span data-ttu-id="8ad34-104"><xref:System.AttributeUsageAttribute> 是应用到自定义特性定义的特性。</span><span class="sxs-lookup"><span data-stu-id="8ad34-104"><xref:System.AttributeUsageAttribute> is an attribute you apply to custom attribute definitions.</span></span> <span data-ttu-id="8ad34-105">`AttributeUsage` 特性帮助控制：</span><span class="sxs-lookup"><span data-stu-id="8ad34-105">The `AttributeUsage` attribute enables you to control:</span></span>

- <span data-ttu-id="8ad34-106">可能应用到的具体程序元素特性。</span><span class="sxs-lookup"><span data-stu-id="8ad34-106">Which program elements attribute may be applied to.</span></span> <span data-ttu-id="8ad34-107">除非使用限制，否则特性可能应用到以下任意程序元素：</span><span class="sxs-lookup"><span data-stu-id="8ad34-107">Unless you restrict its usage, an attribute may be applied to any of the following program elements:</span></span>
  - <span data-ttu-id="8ad34-108">程序集</span><span class="sxs-lookup"><span data-stu-id="8ad34-108">assembly</span></span>
  - <span data-ttu-id="8ad34-109">name</span><span class="sxs-lookup"><span data-stu-id="8ad34-109">module</span></span>
  - <span data-ttu-id="8ad34-110">Field — 字段</span><span class="sxs-lookup"><span data-stu-id="8ad34-110">field</span></span>
  - <span data-ttu-id="8ad34-111">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="8ad34-111">event</span></span>
  - <span data-ttu-id="8ad34-112">方法</span><span class="sxs-lookup"><span data-stu-id="8ad34-112">method</span></span>
  - <span data-ttu-id="8ad34-113">param</span><span class="sxs-lookup"><span data-stu-id="8ad34-113">param</span></span>
  - <span data-ttu-id="8ad34-114">属性</span><span class="sxs-lookup"><span data-stu-id="8ad34-114">property</span></span>
  - <span data-ttu-id="8ad34-115">return</span><span class="sxs-lookup"><span data-stu-id="8ad34-115">return</span></span>
  - <span data-ttu-id="8ad34-116">类型</span><span class="sxs-lookup"><span data-stu-id="8ad34-116">type</span></span>
- <span data-ttu-id="8ad34-117">某特性是否可多次应用于单个程序元素。</span><span class="sxs-lookup"><span data-stu-id="8ad34-117">Whether an attribute can be applied to a single program element multiple times.</span></span>
- <span data-ttu-id="8ad34-118">特性是否由派生类继承。</span><span class="sxs-lookup"><span data-stu-id="8ad34-118">Whether attributes are inherited by derived classes.</span></span>

<span data-ttu-id="8ad34-119">显式应用时，默认设置如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="8ad34-119">The default settings look like the following example when applied explicitly:</span></span>

[!code-csharp[Define a new attribute](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#1)]

<span data-ttu-id="8ad34-120">在此示例中，`NewAttribute` 类可应用于任何受支持的程序元素。</span><span class="sxs-lookup"><span data-stu-id="8ad34-120">In this example, the `NewAttribute` class can be applied to any supported program element.</span></span> <span data-ttu-id="8ad34-121">但是它对每个实体仅能应用一次。</span><span class="sxs-lookup"><span data-stu-id="8ad34-121">But it can be applied only once to each entity.</span></span> <span data-ttu-id="8ad34-122">特性应用于基类时，它由派生类继承。</span><span class="sxs-lookup"><span data-stu-id="8ad34-122">The attribute is inherited by derived classes when applied to a base class.</span></span>

<span data-ttu-id="8ad34-123"><xref:System.AttributeUsageAttribute.AllowMultiple> 和 <xref:System.AttributeUsageAttribute.Inherited> 参数是可选的，因此以下代码具有相同效果：</span><span class="sxs-lookup"><span data-stu-id="8ad34-123">The <xref:System.AttributeUsageAttribute.AllowMultiple> and <xref:System.AttributeUsageAttribute.Inherited> arguments are optional, so the following code has the same effect:</span></span>

[!code-csharp[Omit optional attributes](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#2)]

<span data-ttu-id="8ad34-124">第一个 <xref:System.AttributeUsageAttribute> 参数必须是 <xref:System.AttributeTargets> 枚举的一个或多个元素。</span><span class="sxs-lookup"><span data-stu-id="8ad34-124">The first <xref:System.AttributeUsageAttribute> argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="8ad34-125">可将多个目标类型与 OR 运算符链接在一起，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="8ad34-125">Multiple target types can be linked together with the OR operator, like the following example shows:</span></span>

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#1)]

<span data-ttu-id="8ad34-126">从 C# 7.3 开始，特性可应用于自动实现的属性的属性或支持字段。</span><span class="sxs-lookup"><span data-stu-id="8ad34-126">Beginning in C# 7.3, attributes can be applied to either the property or the backing field for an auto-implemented property.</span></span> <span data-ttu-id="8ad34-127">特性应用于属性，除非在特性上指定 `field` 说明符。</span><span class="sxs-lookup"><span data-stu-id="8ad34-127">The attribute applies to the property, unless you specify the `field` specifier on the attribute.</span></span> <span data-ttu-id="8ad34-128">都在以下示例中进行了演示：</span><span class="sxs-lookup"><span data-stu-id="8ad34-128">Both are shown in the following example:</span></span>

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#2)]

<span data-ttu-id="8ad34-129">如果 <xref:System.AttributeUsageAttribute.AllowMultiple> 参数为 `true`，那么结果特性可多次应用于单个实体，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="8ad34-129">If the <xref:System.AttributeUsageAttribute.AllowMultiple> argument is `true`, then the resulting attribute can be applied more than once to a single entity, as shown in the following example:</span></span>

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/MultiUseAttribute.cs#1)]

<span data-ttu-id="8ad34-130">在本例中，`MultiUseAttribute` 可重复应用，因为 `AllowMultiple` 设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="8ad34-130">In this case, `MultiUseAttribute` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="8ad34-131">所显示的两种用于应用多个特性的格式均有效。</span><span class="sxs-lookup"><span data-stu-id="8ad34-131">Both formats shown for applying multiple attributes are valid.</span></span>

<span data-ttu-id="8ad34-132">如果 <xref:System.AttributeUsageAttribute.Inherited> 为 `false`，那么该特性不是由特性类派生的类继承。</span><span class="sxs-lookup"><span data-stu-id="8ad34-132">If <xref:System.AttributeUsageAttribute.Inherited> is `false`, then the attribute isn't inherited by classes derived from an attributed class.</span></span> <span data-ttu-id="8ad34-133">例如:</span><span class="sxs-lookup"><span data-stu-id="8ad34-133">For example:</span></span>

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/NonInheritedAttribute.cs#1)]

<span data-ttu-id="8ad34-134">在本例中，`NonInheritedAttribute` 不会通过继承应用于 `DClass`。</span><span class="sxs-lookup"><span data-stu-id="8ad34-134">In this case `NonInheritedAttribute` isn't applied to `DClass` via inheritance.</span></span>

## <a name="remarks"></a><span data-ttu-id="8ad34-135">备注</span><span class="sxs-lookup"><span data-stu-id="8ad34-135">Remarks</span></span>

<span data-ttu-id="8ad34-136">`AttributeUsage` 特性是单次使用的特性 -- 它无法应用于同一个类超过一次。</span><span class="sxs-lookup"><span data-stu-id="8ad34-136">The `AttributeUsage` attribute is a single-use attribute--it can't be applied more than once to the same class.</span></span> <span data-ttu-id="8ad34-137">`AttributeUsage` 是 <xref:System.AttributeUsageAttribute> 的别名。</span><span class="sxs-lookup"><span data-stu-id="8ad34-137">`AttributeUsage` is an alias for <xref:System.AttributeUsageAttribute>.</span></span>

<span data-ttu-id="8ad34-138">有关详细信息，请参阅[使用反射访问特性 (C#)](accessing-attributes-by-using-reflection.md)。</span><span class="sxs-lookup"><span data-stu-id="8ad34-138">For more information, see [Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md).</span></span>

## <a name="example"></a><span data-ttu-id="8ad34-139">示例</span><span class="sxs-lookup"><span data-stu-id="8ad34-139">Example</span></span>

<span data-ttu-id="8ad34-140">以下示例演示 <xref:System.AttributeUsageAttribute.Inherited> 和 <xref:System.AttributeUsageAttribute.AllowMultiple> 参数对 <xref:System.AttributeUsageAttribute> 特性的影响，以及如何枚举应用于类的自定义特性。</span><span class="sxs-lookup"><span data-stu-id="8ad34-140">The following example demonstrates the effect of the <xref:System.AttributeUsageAttribute.Inherited> and <xref:System.AttributeUsageAttribute.AllowMultiple> arguments to the <xref:System.AttributeUsageAttribute> attribute, and how the custom attributes applied to a class can be enumerated.</span></span>

[!code-csharp[Applying and querying attributes](../../../../../samples/snippets/csharp/attributes/Program.cs#1)]

## <a name="sample-output"></a><span data-ttu-id="8ad34-141">示例输出</span><span class="sxs-lookup"><span data-stu-id="8ad34-141">Sample Output</span></span>

```text
Attributes on Base Class:
FirstAttribute
SecondAttribute
Attributes on Derived Class:
ThirdAttribute
ThirdAttribute
SecondAttribute
```

## <a name="see-also"></a><span data-ttu-id="8ad34-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ad34-142">See also</span></span>

- <xref:System.Attribute>
- <xref:System.Reflection>
- [<span data-ttu-id="8ad34-143">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8ad34-143">C# Programming Guide</span></span>](../..//index.md)
- [<span data-ttu-id="8ad34-144">特性</span><span class="sxs-lookup"><span data-stu-id="8ad34-144">Attributes</span></span>](../../../..//standard/attributes/index.md)
- [<span data-ttu-id="8ad34-145">反射 (C#)</span><span class="sxs-lookup"><span data-stu-id="8ad34-145">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="8ad34-146">特性</span><span class="sxs-lookup"><span data-stu-id="8ad34-146">Attributes</span></span>](index.md)
- [<span data-ttu-id="8ad34-147">创建自定义特性 (C#)</span><span class="sxs-lookup"><span data-stu-id="8ad34-147">Creating Custom Attributes (C#)</span></span>](creating-custom-attributes.md)
- [<span data-ttu-id="8ad34-148">使用反射访问特性 (C#)</span><span class="sxs-lookup"><span data-stu-id="8ad34-148">Accessing Attributes by Using Reflection (C#)</span></span>](accessing-attributes-by-using-reflection.md)
