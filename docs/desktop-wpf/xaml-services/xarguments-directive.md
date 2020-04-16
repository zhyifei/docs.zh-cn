---
title: x:Arguments 指令
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 5ec6e192688e1065ea847db6c175ad9da0e743fe
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432832"
---
# <a name="xarguments-directive"></a><span data-ttu-id="5585c-102">x:Arguments 指令</span><span class="sxs-lookup"><span data-stu-id="5585c-102">x:Arguments Directive</span></span>

<span data-ttu-id="5585c-103">在 XAML 或工厂方法对象声明中为非无参数构造函数对象元素声明打包构造参数。</span><span class="sxs-lookup"><span data-stu-id="5585c-103">Packages construction arguments for a non-parameterless constructor object element declaration in XAML, or for a factory method object declaration.</span></span>

## <a name="xaml-element-usage-nonparameterless-constructor"></a><span data-ttu-id="5585c-104">XAML 元素使用（无参数构造函数）</span><span class="sxs-lookup"><span data-stu-id="5585c-104">XAML Element Usage (Nonparameterless constructor)</span></span>

```xaml
<object ...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="5585c-105">XAML 元素用法（工厂方法）</span><span class="sxs-lookup"><span data-stu-id="5585c-105">XAML Element Usage (factory method)</span></span>

```xaml
<object x:FactoryMethod="methodName"...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="5585c-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="5585c-106">XAML Values</span></span>

|||
|-|-|
|`oneOrMoreObjectElements`|<span data-ttu-id="5585c-107">指定要传递给支持的非无参数构造函数或工厂方法的参数的一个或多个对象元素。</span><span class="sxs-lookup"><span data-stu-id="5585c-107">One or more object elements that specify arguments to be passed to the backing non-parameterless constructor or factory method.</span></span><br /><br /> <span data-ttu-id="5585c-108">典型用法是使用对象元素中的初始化文本来指定实际参数值。</span><span class="sxs-lookup"><span data-stu-id="5585c-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="5585c-109">请参阅示例部分。</span><span class="sxs-lookup"><span data-stu-id="5585c-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="5585c-110">元素的顺序很重要。</span><span class="sxs-lookup"><span data-stu-id="5585c-110">The order of the elements is significant.</span></span> <span data-ttu-id="5585c-111">XAML 类型顺序必须与后备构造函数或工厂方法重载的类型和类型顺序匹配。</span><span class="sxs-lookup"><span data-stu-id="5585c-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|
|`methodName`|<span data-ttu-id="5585c-112">应处理任何`x:Arguments`参数的工厂方法的名称。</span><span class="sxs-lookup"><span data-stu-id="5585c-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="5585c-113">依赖项</span><span class="sxs-lookup"><span data-stu-id="5585c-113">Dependencies</span></span>

<span data-ttu-id="5585c-114">`x:FactoryMethod`可以修改`x:Arguments`适用的范围和行为。</span><span class="sxs-lookup"><span data-stu-id="5585c-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>

<span data-ttu-id="5585c-115">如果未`x:FactoryMethod`指定，`x:Arguments`则应用于支持构造函数的备用（非默认）签名。</span><span class="sxs-lookup"><span data-stu-id="5585c-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>

<span data-ttu-id="5585c-116">如果`x:FactoryMethod`指定，`x:Arguments`则应用于命名方法的重载。</span><span class="sxs-lookup"><span data-stu-id="5585c-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>

## <a name="remarks"></a><span data-ttu-id="5585c-117">备注</span><span class="sxs-lookup"><span data-stu-id="5585c-117">Remarks</span></span>

<span data-ttu-id="5585c-118">XAML 2006 可通过初始化文本支持非默认初始化。</span><span class="sxs-lookup"><span data-stu-id="5585c-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="5585c-119">然而，初始化文本构造技术的实际应用有限。</span><span class="sxs-lookup"><span data-stu-id="5585c-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="5585c-120">初始化文本被视为单个文本字符串;因此，它仅添加单个参数初始化的功能，除非为构造行为定义类型转换器，该构造行为可以从字符串解析自定义信息项和自定义分隔符。</span><span class="sxs-lookup"><span data-stu-id="5585c-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="5585c-121">此外，到对象逻辑的文本字符串可能是给定的 XAML 解析器的本机默认类型转换器，用于处理真字符串以外的基元。</span><span class="sxs-lookup"><span data-stu-id="5585c-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>

<span data-ttu-id="5585c-122">`x:Arguments` XAML 用法在典型意义上不是属性元素用法，因为指令标记不引用包含对象元素的类型。</span><span class="sxs-lookup"><span data-stu-id="5585c-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="5585c-123">它更类似于其他指令，例如`x:Code`元素将标记的范围解释为子内容的默认值以外的范围。</span><span class="sxs-lookup"><span data-stu-id="5585c-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="5585c-124">在这种情况下，每个对象元素的 XAML 类型传达有关参数类型的信息，XAML 解析器使用该类型来确定`x:Arguments`使用方法尝试引用的特定构造函数工厂方法签名。</span><span class="sxs-lookup"><span data-stu-id="5585c-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>

<span data-ttu-id="5585c-125">`x:Arguments`对于正在构造的对象元素，必须位于对象元素的任何其他属性元素、内容、内部文本或初始化字符串之前。</span><span class="sxs-lookup"><span data-stu-id="5585c-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="5585c-126">中`x:Arguments`的对象元素可以包括属性和初始化字符串，这是 XAML 类型及其支持构造函数或工厂方法所允许的。</span><span class="sxs-lookup"><span data-stu-id="5585c-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="5585c-127">对于对象或参数，可以通过引用已建立的前缀映射来指定自定义 XAML 类型或 XAML 类型，这些类型在默认 XAML 命名空间之外。</span><span class="sxs-lookup"><span data-stu-id="5585c-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>

<span data-ttu-id="5585c-128">XAML 处理器使用以下准则来确定如何在 中`x:Arguments`指定的参数用于构造对象。</span><span class="sxs-lookup"><span data-stu-id="5585c-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="5585c-129">如果`x:FactoryMethod`指定，则将信息与指定的`x:FactoryMethod`（请注意，值`x:FactoryMethod`是方法名称，并且命名方法可以具有重载。</span><span class="sxs-lookup"><span data-stu-id="5585c-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="5585c-130">如果未`x:FactoryMethod`指定，则将信息与对象的所有公共构造函数重载集进行比较。</span><span class="sxs-lookup"><span data-stu-id="5585c-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="5585c-131">然后，XAML 处理逻辑比较参数数，并选择具有匹配的参数的重载。</span><span class="sxs-lookup"><span data-stu-id="5585c-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="5585c-132">如果有多个匹配项，XAML 处理器应根据提供的对象元素的 XAML 类型比较参数类型。</span><span class="sxs-lookup"><span data-stu-id="5585c-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="5585c-133">如果仍然有多个匹配项，则未定义 XAML 处理器行为。</span><span class="sxs-lookup"><span data-stu-id="5585c-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="5585c-134">如果指定`x:FactoryMethod`了 ，但方法无法解决，XAML 处理器应引发异常。</span><span class="sxs-lookup"><span data-stu-id="5585c-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>

<span data-ttu-id="5585c-135">从技术上讲，XAML`<x:Arguments>string</x:Arguments>`属性使用是可能的。</span><span class="sxs-lookup"><span data-stu-id="5585c-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="5585c-136">但是，除了通过初始化文本和类型转换器可以执行哪些功能之外，这没有任何功能，使用此语法不是 XAML 2009 工厂方法功能的设计意图。</span><span class="sxs-lookup"><span data-stu-id="5585c-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>

## <a name="examples"></a><span data-ttu-id="5585c-137">示例</span><span class="sxs-lookup"><span data-stu-id="5585c-137">Examples</span></span>

<span data-ttu-id="5585c-138">下面的示例显示一个非无参数构造函数签名，然后是该签名的`x:Arguments`XAML 用法。</span><span class="sxs-lookup"><span data-stu-id="5585c-138">The following example shows a non-parameterless constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>

```csharp
public class Food {
  private string _name;
  private Int32 _calories;
  public Food(string name, Int32 calories) {
      _name=name;
      _calories=calories;
  }
}
```

```xaml
<my:Food>
  <x:Arguments>
      <x:String>Apple</x:String>
      <x:Int32>150</x:Int32>
  </x:Arguments>
</my:Food>
```

<span data-ttu-id="5585c-139">下面的示例显示目标工厂方法签名，然后显示该签名的`x:Arguments`XAML 用法。</span><span class="sxs-lookup"><span data-stu-id="5585c-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>

```csharp
public Food TryLookupFood(string name)
{
switch (name) {
  case "Apple": return new Food("Apple",150);
  case "Chocolate": return new Food("Chocolate",200);
  case "Cheese": return new Food("Cheese", 450);
  default: {return new Food(name,0);
}
}
```

```xaml
<my:Food x:FactoryMethod="TryLookupFood">
  <x:Arguments>
      <x:String>Apple</x:String>
  </x:Arguments>
</my:Food>
```

## <a name="see-also"></a><span data-ttu-id="5585c-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="5585c-140">See also</span></span>

- [<span data-ttu-id="5585c-141">定义与 .NET XAML 服务一起使用的自定义类型</span><span class="sxs-lookup"><span data-stu-id="5585c-141">Defining Custom Types for Use with .NET XAML Services</span></span>](define-custom-types.md)
- [<span data-ttu-id="5585c-142">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="5585c-142">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
