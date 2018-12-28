---
title: 特性
description: 了解如何F#属性启用要应用于编程构造的元数据。
ms.date: 05/16/2016
ms.openlocfilehash: 34223523efbb3bd89bb73f35fac3dfd8113d8611
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611837"
---
# <a name="attributes"></a><span data-ttu-id="f31b9-103">特性</span><span class="sxs-lookup"><span data-stu-id="f31b9-103">Attributes</span></span>

<span data-ttu-id="f31b9-104">属性启用要应用于编程构造的元数据。</span><span class="sxs-lookup"><span data-stu-id="f31b9-104">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="f31b9-105">语法</span><span class="sxs-lookup"><span data-stu-id="f31b9-105">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="f31b9-106">备注</span><span class="sxs-lookup"><span data-stu-id="f31b9-106">Remarks</span></span>

<span data-ttu-id="f31b9-107">在上述语法中，*目标*是可选的并且如果存在，则指定特性所应用到程序实体的类型。</span><span class="sxs-lookup"><span data-stu-id="f31b9-107">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="f31b9-108">有效值*目标*出现在本文档后面的表中所示。</span><span class="sxs-lookup"><span data-stu-id="f31b9-108">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="f31b9-109">*属性名称*引用 （可能是用命名空间限定） 名称的有效的特性类型，带有或不带后缀`Attribute`的常用属性的类型名称。</span><span class="sxs-lookup"><span data-stu-id="f31b9-109">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="f31b9-110">例如，类型`ObsoleteAttribute`可以缩短至只有`Obsolete`在此上下文中。</span><span class="sxs-lookup"><span data-stu-id="f31b9-110">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="f31b9-111">*自变量*是属性类型构造函数的参数。</span><span class="sxs-lookup"><span data-stu-id="f31b9-111">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="f31b9-112">如果属性具有默认构造函数，可以省略参数列表和括号。</span><span class="sxs-lookup"><span data-stu-id="f31b9-112">If an attribute has a default constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="f31b9-113">属性支持位置参数和命名自变量。</span><span class="sxs-lookup"><span data-stu-id="f31b9-113">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="f31b9-114">*位置参数*是它们的显示的顺序中使用的参数。</span><span class="sxs-lookup"><span data-stu-id="f31b9-114">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="f31b9-115">如果属性具有公共属性，可以使用命名的参数。</span><span class="sxs-lookup"><span data-stu-id="f31b9-115">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="f31b9-116">您可以设置这些自变量列表中使用以下语法。</span><span class="sxs-lookup"><span data-stu-id="f31b9-116">You can set these by using the following syntax in the argument list.</span></span>

```
*property-name* = *property-value*
```

<span data-ttu-id="f31b9-117">此类属性初始化可以任何顺序，但它们必须遵循任何位置自变量。</span><span class="sxs-lookup"><span data-stu-id="f31b9-117">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="f31b9-118">下面是使用位置自变量和属性初始化属性的一个示例。</span><span class="sxs-lookup"><span data-stu-id="f31b9-118">Following is an example of an attribute that uses positional arguments and property initializations.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="f31b9-119">在此示例中，属性是`DllImportAttribute`，此处使用缩写形式。</span><span class="sxs-lookup"><span data-stu-id="f31b9-119">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="f31b9-120">第一个参数是位置参数和第二个是一个属性。</span><span class="sxs-lookup"><span data-stu-id="f31b9-120">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="f31b9-121">属性是.NET 编程构造，使对象称为*特性*要与类型或其他程序元素相关联。</span><span class="sxs-lookup"><span data-stu-id="f31b9-121">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="f31b9-122">特性应用于程序元素称为*属性目标*。</span><span class="sxs-lookup"><span data-stu-id="f31b9-122">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="f31b9-123">该属性通常包含有关其目标的元数据。</span><span class="sxs-lookup"><span data-stu-id="f31b9-123">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="f31b9-124">在此上下文中，元数据可能是其字段和成员以外的类型有关的任何数据。</span><span class="sxs-lookup"><span data-stu-id="f31b9-124">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="f31b9-125">中的属性F#可应用于以下的编程构造： 函数、 方法、 程序集、 模块、 类型 （类、 记录、 结构、 接口、 委托、 枚举、 联合和等等）、 构造函数、 属性、 字段，参数，类型参数，并返回值。</span><span class="sxs-lookup"><span data-stu-id="f31b9-125">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="f31b9-126">属性不允许对`let`类、 表达式或工作流表达式内部的绑定。</span><span class="sxs-lookup"><span data-stu-id="f31b9-126">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="f31b9-127">通常情况下，特性声明的属性目标的声明之前直接显示。</span><span class="sxs-lookup"><span data-stu-id="f31b9-127">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="f31b9-128">可以使用多个属性声明，在一起，按如下所示。</span><span class="sxs-lookup"><span data-stu-id="f31b9-128">Multiple attribute declarations can be used together, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="f31b9-129">可以通过使用.NET 反射在运行时查询属性。</span><span class="sxs-lookup"><span data-stu-id="f31b9-129">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="f31b9-130">如前面的代码示例中所示，声明单独，多个属性，或如果您使用分号来分隔各个属性和构造函数，如下所示可以声明它们中一组方括号。</span><span class="sxs-lookup"><span data-stu-id="f31b9-130">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as shown here.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="f31b9-131">通常会遇到的属性包括`Obsolete`COM 支持、 与代码中，所有权相关的属性和属性，指示是否可以序列化类型的属性，出于安全考虑，特性属性。</span><span class="sxs-lookup"><span data-stu-id="f31b9-131">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="f31b9-132">下面的示例演示如何将`Obsolete`属性。</span><span class="sxs-lookup"><span data-stu-id="f31b9-132">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="f31b9-133">对于特性目标`assembly`并`module`，将特性应用于顶级`do`中您的程序集的绑定。</span><span class="sxs-lookup"><span data-stu-id="f31b9-133">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="f31b9-134">可以包括词`assembly`或`module`在属性声明中，按如下所示。</span><span class="sxs-lookup"><span data-stu-id="f31b9-134">You can include the word `assembly` or `module` in the attribute declaration, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="f31b9-135">如果忽略应用于的特性的属性目标`do`绑定，F#编译器将尝试确定该属性有意义的属性目标。</span><span class="sxs-lookup"><span data-stu-id="f31b9-135">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="f31b9-136">许多属性类具有类型的属性`System.AttributeUsageAttribute`，包括支持该属性的可能目标有关的信息。</span><span class="sxs-lookup"><span data-stu-id="f31b9-136">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="f31b9-137">如果`System.AttributeUsageAttribute`指示该属性支持使用函数作为目标，则会特性要应用于程序的主入口点。</span><span class="sxs-lookup"><span data-stu-id="f31b9-137">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="f31b9-138">如果`System.AttributeUsageAttribute`指示该属性支持使用作为目标的程序集，编译器会将特性应用于程序集。</span><span class="sxs-lookup"><span data-stu-id="f31b9-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="f31b9-139">大多数属性不适用于函数和程序集，但在完成的情况下，会将特性应用于程序的主函数。</span><span class="sxs-lookup"><span data-stu-id="f31b9-139">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="f31b9-140">如果显式指定特性目标，则该属性应用到指定的目标。</span><span class="sxs-lookup"><span data-stu-id="f31b9-140">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="f31b9-141">尽管您通常不必指定特性显式目标的有效值*目标*在属性中所示下表中，以及使用情况的示例。</span><span class="sxs-lookup"><span data-stu-id="f31b9-141">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute are shown in the following table, along with examples of usage.</span></span>

<table>
  <tr>
    <th><span data-ttu-id="f31b9-142">属性目标</span><span class="sxs-lookup"><span data-stu-id="f31b9-142">Attribute target</span></span></td>
    <th><span data-ttu-id="f31b9-143">示例</span><span class="sxs-lookup"><span data-stu-id="f31b9-143">Example</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="f31b9-144">程序集</span><span class="sxs-lookup"><span data-stu-id="f31b9-144">assembly</span></span></td>
    <td><span data-ttu-id="f31b9-145">`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</span><span class="sxs-lookup"><span data-stu-id="f31b9-145">`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="f31b9-146">return</span><span class="sxs-lookup"><span data-stu-id="f31b9-146">return</span></span></td>
    <td><span data-ttu-id="f31b9-147">让 function1 x: [<return: Obsolete>] int = x + 1</span><span class="sxs-lookup"><span data-stu-id="f31b9-147">`let function1 x : [<return: Obsolete>] int = x + 1`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="f31b9-148">Field — 字段</span><span class="sxs-lookup"><span data-stu-id="f31b9-148">field</span></span></td>
    <td><span data-ttu-id="f31b9-149">[<field: DefaultValue>] val 可变 x: int</span><span class="sxs-lookup"><span data-stu-id="f31b9-149">`[<field: DefaultValue>] val mutable x: int`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="f31b9-150">属性</span><span class="sxs-lookup"><span data-stu-id="f31b9-150">property</span></span></td>
    <td><span data-ttu-id="f31b9-151">[<property: Obsolete>] 这。MyProperty = x</span><span class="sxs-lookup"><span data-stu-id="f31b9-151">`[<property: Obsolete>] this.MyProperty = x`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="f31b9-152">param</span><span class="sxs-lookup"><span data-stu-id="f31b9-152">param</span></span></td>
    <td><span data-ttu-id="f31b9-153">成员这。MyMethod ([<param: Out>] x: ref<int>) = x: = 10</span><span class="sxs-lookup"><span data-stu-id="f31b9-153">`member this.MyMethod([<param: Out>] x : ref<int>) = x := 10`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="f31b9-154">类型</span><span class="sxs-lookup"><span data-stu-id="f31b9-154">type</span></span></td>
    <td>

        ```
        [<type: StructLayout(Sequential)>] 
        type MyStruct = 
        struct 
        x : byte
        y : int
        end
        ```
    </td> 
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="f31b9-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="f31b9-155">See also</span></span>

- [<span data-ttu-id="f31b9-156">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="f31b9-156">F# Language Reference</span></span>](index.md)