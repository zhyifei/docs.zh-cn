---
title: "析构元组和其他类型 | Microsoft Docs"
description: "了解如何析构元组和其他类型"
keywords: .NET, .NET Core, C#0
author: rpetrusha
ms-author: ronpet
ms.date: 07/18/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 0b0c4b0f-4a47-4f66-9b8e-f5c63b195960
ms.translationtype: HT
ms.sourcegitcommit: 9fc16c63a6e0e0dd31ee4a68fca8b945b8281e04
ms.openlocfilehash: f0946db700301a63109f23be5536f3a0505f4d60
ms.contentlocale: zh-cn
ms.lasthandoff: 08/01/2017

---

# <a name="deconstructing-tuples-and-other-types"></a><span data-ttu-id="4ba34-104">析构元组和其他类型</span><span class="sxs-lookup"><span data-stu-id="4ba34-104">Deconstructing tuples and other types</span></span> #

<span data-ttu-id="4ba34-105">元组提供一种从方法调用中检索多个值的轻量级方法。</span><span class="sxs-lookup"><span data-stu-id="4ba34-105">A tuple provides a light-weight way to retrieve multiple values from a method call.</span></span> <span data-ttu-id="4ba34-106">但是，一旦检索到元组，就必须处理它的各个元素。</span><span class="sxs-lookup"><span data-stu-id="4ba34-106">But once you retrieve the tuple, you have to handle its individual elements.</span></span> <span data-ttu-id="4ba34-107">按元素逐个执行此操作会比较麻烦，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="4ba34-107">Doing this on an element-by-element basis is cumbersome, as the following example shows.</span></span> <span data-ttu-id="4ba34-108">`QueryCityData` 方法返回一个 3 元组，并通过单独的操作将其每个元素分配给一个变量。</span><span class="sxs-lookup"><span data-stu-id="4ba34-108">The `QueryCityData` method returns a 3-tuple, and each of its elements is assigned to a variable in a separate operation.</span></span>

<span data-ttu-id="4ba34-109">[!code-csharp[WithoutDeconstruction](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4ba34-109">[!code-csharp[WithoutDeconstruction](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple1.cs)]</span></span>

<span data-ttu-id="4ba34-110">从对象检索多个字段值和属性值可能同样麻烦：必须按成员逐个将字段值或属性值赋给一个变量。</span><span class="sxs-lookup"><span data-stu-id="4ba34-110">Retrieving multiple field and property values from an object can be equally cumbersome: you have to assign a field or property value to a variable on a member-by-member basis.</span></span> 

<span data-ttu-id="4ba34-111">从 C# 7 开始，用户可从元组中检索多个元素，或在单个析构操作中从对象检索多个字段值、属性值和计算值。</span><span class="sxs-lookup"><span data-stu-id="4ba34-111">Starting with C# 7, you can retrieve multiple elements from a tuple or retrieve multiple field, property, and computed values from an object in a single *deconstruct* operation.</span></span> <span data-ttu-id="4ba34-112">析构元组时，将其元素分配给各个变量。</span><span class="sxs-lookup"><span data-stu-id="4ba34-112">When you deconstruct a tuple, you assign its elements to individual variables.</span></span> <span data-ttu-id="4ba34-113">析构对象时，将选定值分配给各个变量。</span><span class="sxs-lookup"><span data-stu-id="4ba34-113">When you deconstruct an object, you assign selected values to individual variables.</span></span> 

## <a name="deconstructing-a-tuple"></a><span data-ttu-id="4ba34-114">析构元组</span><span class="sxs-lookup"><span data-stu-id="4ba34-114">Deconstructing a tuple</span></span>

<span data-ttu-id="4ba34-115">C# 提供内置的元组析构支持，可在单个操作中解包一个元组中的所有项。</span><span class="sxs-lookup"><span data-stu-id="4ba34-115">C# features built-in support for deconstructing tuples, which lets you unpackage all the items in a tuple in a single operation.</span></span> <span data-ttu-id="4ba34-116">用于析构元组的常规语法与用于定义元组的语法相似：将要向其分配元素的变量放在赋值语句左侧的括号中。</span><span class="sxs-lookup"><span data-stu-id="4ba34-116">The general syntax for deconstructing a tuple is similar to the syntax for defining one: you enclose the variables to which each element is to be assigned in parentheses in the left side of an assignment statement.</span></span> <span data-ttu-id="4ba34-117">例如，以下语句将 4 元组的元素分配给 4 个单独的变量：</span><span class="sxs-lookup"><span data-stu-id="4ba34-117">For example, the following statement assigns the elements of a 4-tuple to four separate variables:</span></span>

```csharp
var (name, address, city, zip) = contact.GetAddressInfo();
```

<span data-ttu-id="4ba34-118">有两种方法可用于析构元组：</span><span class="sxs-lookup"><span data-stu-id="4ba34-118">There are two ways to deconstruct a tuple:</span></span>

- <span data-ttu-id="4ba34-119">可以在括号内显式声明每个字段的类型。</span><span class="sxs-lookup"><span data-stu-id="4ba34-119">You can explicitly declare the type of each field inside parentheses.</span></span> <span data-ttu-id="4ba34-120">以下示例使用此方法来析构由 `QueryCityData` 方法返回的 3 元组。</span><span class="sxs-lookup"><span data-stu-id="4ba34-120">The following example uses this approach to deconstruct the 3-tuple returned by the `QueryCityData` method.</span></span>

    <span data-ttu-id="4ba34-121">[!code-csharp[析构-显式](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple2.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="4ba34-121">[!code-csharp[Deconstruction-Explicit](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple2.cs#1)]</span></span>

- <span data-ttu-id="4ba34-122">可使用 `var` 关键字，以便 C# 推断每个变量的类型。</span><span class="sxs-lookup"><span data-stu-id="4ba34-122">You can use the `var` keyword so that C# infers the type of each variable.</span></span> <span data-ttu-id="4ba34-123">将 `var` 关键字放在括号外。</span><span class="sxs-lookup"><span data-stu-id="4ba34-123">You place the `var` keyword outside of the parentheses.</span></span> <span data-ttu-id="4ba34-124">以下示例在析构由 `QueryCityData` 方法返回的 3 元组时使用类型推理。</span><span class="sxs-lookup"><span data-stu-id="4ba34-124">The following example uses type inference when deconstructing the 3-tuple returned by the `QueryCityData` method.</span></span>
 
      [!code-csharp[Deconstruction-Infer](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple3.cs#1)]

    <span data-ttu-id="4ba34-125">还可在括号内将 `var` 关键字单独与任一或全部变量声明结合使用。</span><span class="sxs-lookup"><span data-stu-id="4ba34-125">You can also use the `var` keyword individually with any or all of the variable declarations inside the parentheses.</span></span> 

      [!code-csharp[Deconstruction-Infer-Some](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple4.cs#1)]

    <span data-ttu-id="4ba34-126">这很麻烦，不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="4ba34-126">This is cumbersome and is not recommended.</span></span>

<span data-ttu-id="4ba34-127">请注意，即使元组中的每个字段都具有相同的类型，也不能在括号外指定特定类型。</span><span class="sxs-lookup"><span data-stu-id="4ba34-127">Note that you cannot specify a specific type outside the parentheses even if every field in the tuple has the same type.</span></span> <span data-ttu-id="4ba34-128">这会引发编译器错误 CS8136：“`var (...)` 形式不允许 `var` 的特定类型”。</span><span class="sxs-lookup"><span data-stu-id="4ba34-128">This generates compiler error CS8136, "`var (...)` form disallows a specific type for `var`.</span></span>

<span data-ttu-id="4ba34-129">请注意，还必须将元组的每个元素分配给一个变量。</span><span class="sxs-lookup"><span data-stu-id="4ba34-129">Note that you must also assign each element of the tuple to a variable.</span></span> <span data-ttu-id="4ba34-130">如果省略任何元素，编译器将生成错误 CS8132，“无法将 ‘x’ 元素的元组析构为 ‘y’ 变量”。</span><span class="sxs-lookup"><span data-stu-id="4ba34-130">If you omit any elements, the compiler generates error CS8132, "Cannot deconstruct a tuple of 'x' elements into 'y' variables."</span></span>

## <a name="deconstructing-tuple-elements-with-discards"></a><span data-ttu-id="4ba34-131">使用放弃析构元组元素</span><span class="sxs-lookup"><span data-stu-id="4ba34-131">Deconstructing tuple elements with discards</span></span>

<span data-ttu-id="4ba34-132">析构元组时，通常只需要关注某些元素的值。</span><span class="sxs-lookup"><span data-stu-id="4ba34-132">Often when deconstructing a tuple, you're interested in the values of only some elements.</span></span> <span data-ttu-id="4ba34-133">从 C# 7 开始，便可利用 C# 对放弃的支持，放弃是一种仅能写入的变量，且其值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="4ba34-133">Starting with C# 7, you can take advantage of C#'s support for *discards*, which are write-only variables whose values you've chosen to ignore.</span></span> <span data-ttu-id="4ba34-134">在赋值中，通过下划线字符 ("_") 指定放弃。</span><span class="sxs-lookup"><span data-stu-id="4ba34-134">A discard is designated by an underscore character ("_") in an assignment.</span></span> <span data-ttu-id="4ba34-135">可放弃任意数量的值，且均由单个放弃 `_` 表示。</span><span class="sxs-lookup"><span data-stu-id="4ba34-135">You can discard as many values as you like; all are represented by the single discard, `_`.</span></span>

<span data-ttu-id="4ba34-136">以下示例演示了对元组使用放弃时的用法。</span><span class="sxs-lookup"><span data-stu-id="4ba34-136">The following example illustrates the use of tuples with discards.</span></span> <span data-ttu-id="4ba34-137">`QueryCityDataForYears` 方法返回一个 6 元组，包含城市名称、城市面积、一个年份、该年份的城市人口、另一个年份及该年份的城市人口。</span><span class="sxs-lookup"><span data-stu-id="4ba34-137">The `QueryCityDataForYears` method returns a 6-tuple with the name of a city, its area, a year, the city's population for that year, a second year, and the city's population for that second year.</span></span> <span data-ttu-id="4ba34-138">该示例显示了两个年份之间人口的变化。</span><span class="sxs-lookup"><span data-stu-id="4ba34-138">The example shows the change in population between those two years.</span></span> <span data-ttu-id="4ba34-139">对于元组提供的数据，我们不关注城市面积，并在一开始就知道城市名称和两个日期。</span><span class="sxs-lookup"><span data-stu-id="4ba34-139">Of the data available from the tuple, we're unconcerned with the city area, and we know the city name and the two dates at design-time.</span></span> <span data-ttu-id="4ba34-140">因此，我们只关注存储在元组中的两个人口数量值，可将其余值作为放弃处理。</span><span class="sxs-lookup"><span data-stu-id="4ba34-140">As a result, we're only interested in the two population values stored in the tuple, and can handle its remaining values as discards.</span></span>  

<span data-ttu-id="4ba34-141">[!code-csharp[元组-放弃](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4ba34-141">[!code-csharp[Tuple-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]</span></span>

### <a name="deconstructing-user-defined-types"></a><span data-ttu-id="4ba34-142">析构用户定义类型</span><span class="sxs-lookup"><span data-stu-id="4ba34-142">Deconstructing user-defined types</span></span>

<span data-ttu-id="4ba34-143">非元组类型不提供对放弃的内置支持。</span><span class="sxs-lookup"><span data-stu-id="4ba34-143">Non-tuple types do not offer built-in support for discards.</span></span> <span data-ttu-id="4ba34-144">但是，用户作为类、结构或接口的创建者，可通过实现一个或多个 `Deconstruct` 方法来析构该类型的实例。</span><span class="sxs-lookup"><span data-stu-id="4ba34-144">However, as the author of a class, a struct, or an interface, you can allow instances of the type to be deconstructed by implementing one or more `Deconstruct` methods.</span></span> <span data-ttu-id="4ba34-145">该方法返回 void，且要析构的每个值由方法签名中的 [out](language-reference/keywords/out-parameter-modifier.md) 参数指示。</span><span class="sxs-lookup"><span data-stu-id="4ba34-145">The method returns void, and each value to be deconstructed is indicated by an [out](language-reference/keywords/out-parameter-modifier.md) parameter in the method signature.</span></span> <span data-ttu-id="4ba34-146">例如，下面的 `Person` 类的 `Deconstruct` 方法返回名字、中间名和姓氏：</span><span class="sxs-lookup"><span data-stu-id="4ba34-146">For example, the following `Deconstruct` method of a `Person` class returns the first, middle, and last name:</span></span>

<span data-ttu-id="4ba34-147">[!code-csharp[类-析构](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-class1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="4ba34-147">[!code-csharp[Class-deconstruct](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-class1.cs#1)]</span></span>

<span data-ttu-id="4ba34-148">然后，可使用类似于以下的分配来析构名为 `p` 的 `Person` 类的实例：</span><span class="sxs-lookup"><span data-stu-id="4ba34-148">You can then deconstruct an instance of the `Person` class named `p` with an assignment like the following:</span></span>

<span data-ttu-id="4ba34-149">[!code-csharp[类-析构](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-class1.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="4ba34-149">[!code-csharp[Class-deconstruct](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-class1.cs#2)]</span></span>

<span data-ttu-id="4ba34-150">以下示例重载 `Deconstruct` 方法以返回 `Person` 对象的各种属性组合。</span><span class="sxs-lookup"><span data-stu-id="4ba34-150">The following example overloads the `Deconstruct` method to return various combinations of properties of a `Person` object.</span></span> <span data-ttu-id="4ba34-151">单个重载返回：</span><span class="sxs-lookup"><span data-stu-id="4ba34-151">Individual overloads return:</span></span>

- <span data-ttu-id="4ba34-152">名字和姓氏。</span><span class="sxs-lookup"><span data-stu-id="4ba34-152">A first and last name.</span></span>
- <span data-ttu-id="4ba34-153">名字、姓氏和中间名。</span><span class="sxs-lookup"><span data-stu-id="4ba34-153">A first, last, and middle name.</span></span>
- <span data-ttu-id="4ba34-154">名字、姓氏、城市名和省/市/自治区名。</span><span class="sxs-lookup"><span data-stu-id="4ba34-154">A first name, a last name, a city name, and a state name.</span></span>

<span data-ttu-id="4ba34-155">[!code-csharp[类-析构](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-class2.cs)]</span><span class="sxs-lookup"><span data-stu-id="4ba34-155">[!code-csharp[Class-deconstruct](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-class2.cs)]</span></span>

<span data-ttu-id="4ba34-156">因为可重载 `Deconstruct` 方法来反映通常从对象中提取的数据组，所以应使用独特明确的签名来定义 `Deconstruct` 方法。</span><span class="sxs-lookup"><span data-stu-id="4ba34-156">Because you can overload the `Deconstruct` method to reflect groups of data that are commonly extracted from an object, you should be careful to define `Deconstruct` methods with signatures that are distinctive and unambiguous.</span></span> <span data-ttu-id="4ba34-157">如果有多个 `Deconstruct` 方法具有相同数量的 `out` 参数，或具有相同数量和类型的 `out` 参数且顺序不同，则可能会造成混淆。</span><span class="sxs-lookup"><span data-stu-id="4ba34-157">Multiple `Deconstruct` methods that have the same number of `out` parameters or the same number and type of `out` parameters in a different order can cause confusion.</span></span> 

<span data-ttu-id="4ba34-158">以下示例中的重载 `Deconstruct` 方法演示一种混淆的可能性。</span><span class="sxs-lookup"><span data-stu-id="4ba34-158">The overloaded `Deconstruct` method in the following example illustrates one possible source of confusion.</span></span> <span data-ttu-id="4ba34-159">第一个重载按该顺序返回 `Person` 对象的名字、中间名、姓氏和年龄。</span><span class="sxs-lookup"><span data-stu-id="4ba34-159">The first overload returns the first name, middle name, last name, and age of a `Person` object, in that order.</span></span> <span data-ttu-id="4ba34-160">第二个重载仅将姓名信息与年收入一起返回，但名字、中间名和姓氏的顺序不同。</span><span class="sxs-lookup"><span data-stu-id="4ba34-160">The second overload returns name information only along with annual income, but the first, middle, and last name are in a different order.</span></span> <span data-ttu-id="4ba34-161">这使得在析构 `Person` 实例时容易混淆参数的顺序。</span><span class="sxs-lookup"><span data-stu-id="4ba34-161">This makes it easy to confuse the order of arguments when deconstructing a `Person` instance.</span></span>

<span data-ttu-id="4ba34-162">[!code-csharp[析构-多义性](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-ambiguous.cs)]</span><span class="sxs-lookup"><span data-stu-id="4ba34-162">[!code-csharp[Deconstruct-ambiguity](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-ambiguous.cs)]</span></span>

## <a name="deconstructing-a-user-defined-type-with-discards"></a><span data-ttu-id="4ba34-163">使用放弃析构用户定义类型</span><span class="sxs-lookup"><span data-stu-id="4ba34-163">Deconstructing a user-defined type with discards</span></span>

<span data-ttu-id="4ba34-164">就像使用[元组](#deconstructing-tuple-elements-with-discards)一样，可使用放弃来忽略 `Deconstruct` 方法返回的选定项。</span><span class="sxs-lookup"><span data-stu-id="4ba34-164">Just as you do with [tuples](#deconstructing-tuple-elements-with-discards), you can use discards to ignore selected items returned by a `Deconstruct` method.</span></span> <span data-ttu-id="4ba34-165">每个放弃由一个名为“_”的变量定义，单个析构操作可包含多个放弃。</span><span class="sxs-lookup"><span data-stu-id="4ba34-165">Each discard is defined by a variable named "_", and a single deconstruction operation can include multiple discards.</span></span>

<span data-ttu-id="4ba34-166">以下示例将 `Person` 对象析构为四个字符串（名字、姓氏、城市和省/市/自治区），但舍弃姓氏和省/市/自治区。</span><span class="sxs-lookup"><span data-stu-id="4ba34-166">The following example deconstructs a `Person` object into four strings (the first and last names, the city, and the state) but discards the last name and the state.</span></span>

<span data-ttu-id="4ba34-167">[!code-csharp[类-放弃](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/class-discard1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="4ba34-167">[!code-csharp[Class-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/class-discard1.cs#1)]</span></span>

## <a name="deconstructing-a-user-defined-type-with-an-extension-method"></a><span data-ttu-id="4ba34-168">使用扩展方法析构用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="4ba34-168">Deconstructing a user-defined type with an extension method</span></span>

<span data-ttu-id="4ba34-169">如果没有创建类、结构或接口，仍可通过实现一个或多个 `Deconstruct` [扩展方法](programming-guide/classes-and-structs/extension-methods.md)来析构该类型的对象，以返回所需值。</span><span class="sxs-lookup"><span data-stu-id="4ba34-169">If you didn't author a class, struct, or interface, you can still deconstruct objects of that type by implementing one or more `Deconstruct` [extension methods](programming-guide/classes-and-structs/extension-methods.md) to return the values in which you're interested.</span></span> 

<span data-ttu-id="4ba34-170">以下示例为 <xref:System.Reflection.PropertyInfo?displayProperty=fullName> 类定义了两个 `Deconstruct` 扩展方法。</span><span class="sxs-lookup"><span data-stu-id="4ba34-170">The following example defines two `Deconstruct` extension methods for the <xref:System.Reflection.PropertyInfo?displayProperty=fullName> class.</span></span> <span data-ttu-id="4ba34-171">第一个方法返回一组值，指示属性的特征，包括其类型、是静态还是实例、是否为只读，以及是否已编制索引。</span><span class="sxs-lookup"><span data-stu-id="4ba34-171">The first returns a set of values that indicate the characteristics of the property, including its type, whether it's static or instance, whether it's read-only, and whether it's indexed.</span></span> <span data-ttu-id="4ba34-172">第二个方法指示属性的可访问性。</span><span class="sxs-lookup"><span data-stu-id="4ba34-172">The second indicates the property's accessibility.</span></span> <span data-ttu-id="4ba34-173">因为 get 和 set 访问器的可访问性可能不同，所以布尔值指示属性是否具有单独的 get 和 set 访问器，如果是，则指示它们是否具有相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="4ba34-173">Because the accessibility of get and set accessors can differ, Boolean values indicate whether the property has separate get and set accessors and, if it does, whether they have the same accessibility.</span></span> <span data-ttu-id="4ba34-174">如果只有一个访问器，或者 get 和 set 访问器具有相同的可访问性，则 `access` 变量指示整个属性的可访问性。</span><span class="sxs-lookup"><span data-stu-id="4ba34-174">If there is only one accessor or both the get and the set accessor have the same accessibility, the `access` variable indicates the accessibility of the property as a whole.</span></span> <span data-ttu-id="4ba34-175">否则，get 和 set 访问器的可访问性由 `getAccess` 和 `setAccess` 变量所指示的可访问性来指示。</span><span class="sxs-lookup"><span data-stu-id="4ba34-175">Otherwise, the accessibility of the get and set accessors are indicated by the accessaccessibility is indicated by the `getAccess` and `setAccess` variables.</span></span>

<span data-ttu-id="4ba34-176">[!code-csharp[扩展-析构](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-extension1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4ba34-176">[!code-csharp[Extension-deconstruct](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-extension1.cs)]</span></span>
 
## <a name="see-also"></a><span data-ttu-id="4ba34-177">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ba34-177">See also</span></span>
<span data-ttu-id="4ba34-178">[放弃](discards.md) </span><span class="sxs-lookup"><span data-stu-id="4ba34-178">[Discards](discards.md) </span></span>  
[<span data-ttu-id="4ba34-179">元组</span><span class="sxs-lookup"><span data-stu-id="4ba34-179">Tuples</span></span>](tuples.md)  

