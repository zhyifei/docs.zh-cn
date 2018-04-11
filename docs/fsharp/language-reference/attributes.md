---
title: 特性 (F#)
description: '了解如何 F # 属性启用要应用到编程构造的元数据。'
keywords: visual f#, f#, 函数编程
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 95c001e6-3708-4d04-a850-d855f78eb51e
ms.openlocfilehash: 88098e51d19a86f501c35abe3408524378f147b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="attributes"></a><span data-ttu-id="a1a55-104">特性</span><span class="sxs-lookup"><span data-stu-id="a1a55-104">Attributes</span></span>

<span data-ttu-id="a1a55-105">属性启用元数据要应用到编程构造。</span><span class="sxs-lookup"><span data-stu-id="a1a55-105">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="a1a55-106">语法</span><span class="sxs-lookup"><span data-stu-id="a1a55-106">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="a1a55-107">备注</span><span class="sxs-lookup"><span data-stu-id="a1a55-107">Remarks</span></span>

<span data-ttu-id="a1a55-108">在上述语法中，*目标*是可选的如果存在，则指定此特性应用于程序实体的类型。</span><span class="sxs-lookup"><span data-stu-id="a1a55-108">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="a1a55-109">有效值为*目标*出现在本文档后面的表所示。</span><span class="sxs-lookup"><span data-stu-id="a1a55-109">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="a1a55-110">*属性名称*引用 （可能用命名空间限定） 名称的有效的属性类型，或如果没有后缀`Attribute`通常用在特性类型名称。</span><span class="sxs-lookup"><span data-stu-id="a1a55-110">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="a1a55-111">例如，类型`ObsoleteAttribute`可以缩短至只有`Obsolete`在此上下文中。</span><span class="sxs-lookup"><span data-stu-id="a1a55-111">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="a1a55-112">*参数*属性类型的自变量的构造函数。</span><span class="sxs-lookup"><span data-stu-id="a1a55-112">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="a1a55-113">如果某一特性有一个默认构造函数，可以省略自变量列表和括号。</span><span class="sxs-lookup"><span data-stu-id="a1a55-113">If an attribute has a default constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="a1a55-114">特性支持位置自变量和命名自变量。</span><span class="sxs-lookup"><span data-stu-id="a1a55-114">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="a1a55-115">*位置自变量*是以它们出现的顺序使用的自变量。</span><span class="sxs-lookup"><span data-stu-id="a1a55-115">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="a1a55-116">如果该属性具有公共属性，可以使用命名自变量。</span><span class="sxs-lookup"><span data-stu-id="a1a55-116">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="a1a55-117">可以通过使用以下语法自变量列表中的这些设置。</span><span class="sxs-lookup"><span data-stu-id="a1a55-117">You can set these by using the following syntax in the argument list.</span></span>

```
*property-name* = *property-value*
```

<span data-ttu-id="a1a55-118">此类属性初始化操作可以采用任何顺序，但它们必须遵循的任何位置的自变量。</span><span class="sxs-lookup"><span data-stu-id="a1a55-118">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="a1a55-119">下面是特性的使用位置自变量和属性的初始化过程中的示例。</span><span class="sxs-lookup"><span data-stu-id="a1a55-119">Following is an example of an attribute that uses positional arguments and property initializations.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="a1a55-120">在此示例中，该特性是`DllImportAttribute`，此处使用缩写形式。</span><span class="sxs-lookup"><span data-stu-id="a1a55-120">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="a1a55-121">第一个参数是位置参数，并且第二个是属性。</span><span class="sxs-lookup"><span data-stu-id="a1a55-121">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="a1a55-122">属性是一个.NET 编程构造，用于使对象称为*属性*要与类型或其他程序元素相关联。</span><span class="sxs-lookup"><span data-stu-id="a1a55-122">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="a1a55-123">向其应用的特性的程序元素称为*属性目标*。</span><span class="sxs-lookup"><span data-stu-id="a1a55-123">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="a1a55-124">属性通常包含有关其目标的元数据。</span><span class="sxs-lookup"><span data-stu-id="a1a55-124">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="a1a55-125">在此上下文中，元数据可能是其字段和成员以外的类型有关的任何数据。</span><span class="sxs-lookup"><span data-stu-id="a1a55-125">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="a1a55-126">F # 中的特性可以应用于以下的编程构造： 函数、 方法、 程序集、 模块、 类型 （类、 记录、 结构、 接口、 委托、 枚举、 联合和等等）、 构造函数、 属性、 字段、 参数，类型参数，并返回值。</span><span class="sxs-lookup"><span data-stu-id="a1a55-126">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="a1a55-127">属性不能存在于`let`绑定到类、 表达式或工作流表达式。</span><span class="sxs-lookup"><span data-stu-id="a1a55-127">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="a1a55-128">通常情况下，特性声明出现直接之前的属性目标的声明。</span><span class="sxs-lookup"><span data-stu-id="a1a55-128">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="a1a55-129">在一起，如下所示，可以使用多个属性声明。</span><span class="sxs-lookup"><span data-stu-id="a1a55-129">Multiple attribute declarations can be used together, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="a1a55-130">通过使用.NET 反射，可以在运行时查询属性。</span><span class="sxs-lookup"><span data-stu-id="a1a55-130">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="a1a55-131">如前面的代码示例所示，声明单独，多个属性或如果你使用分号来分隔各个属性和构造函数，如此处所示可以声明它们在一组方括号中。</span><span class="sxs-lookup"><span data-stu-id="a1a55-131">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as shown here.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="a1a55-132">通常会遇到的属性包括`Obsolete`COM 支持、 所有权的代码中，相关的属性和属性，该值指示是否可以序列化类型的属性，为了安全起见，特性属性。</span><span class="sxs-lookup"><span data-stu-id="a1a55-132">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="a1a55-133">下面的示例演示了利用`Obsolete`属性。</span><span class="sxs-lookup"><span data-stu-id="a1a55-133">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="a1a55-134">对于特性目标`assembly`和`module`，将特性应用于顶级`do`中程序集的绑定。</span><span class="sxs-lookup"><span data-stu-id="a1a55-134">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="a1a55-135">你可以纳入单词`assembly`或`module`，请在属性声明，如下所示。</span><span class="sxs-lookup"><span data-stu-id="a1a55-135">You can include the word `assembly` or `module` in the attribute declaration, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="a1a55-136">如果你省略应用于属性的属性目标`do`绑定，F # 编译器将尝试确定适合该属性的属性目标。</span><span class="sxs-lookup"><span data-stu-id="a1a55-136">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="a1a55-137">许多属性类具有类型的属性`System.AttributeUsageAttribute`，包括有关可能的目标支持该属性的信息。</span><span class="sxs-lookup"><span data-stu-id="a1a55-137">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="a1a55-138">如果`System.AttributeUsageAttribute`指示特性支持使用作为目标的函数，则会特性将应用于程序的主入口点。</span><span class="sxs-lookup"><span data-stu-id="a1a55-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="a1a55-139">如果`System.AttributeUsageAttribute`指示特性支持使用作为目标的程序集，编译器采用要应用于程序集的特性。</span><span class="sxs-lookup"><span data-stu-id="a1a55-139">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="a1a55-140">大多数属性不适用于函数和程序集，但在它们执行操作的情况下，会将特性应用于程序的主函数。</span><span class="sxs-lookup"><span data-stu-id="a1a55-140">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="a1a55-141">如果显式指定的属性目标，则属性应用于指定的目标。</span><span class="sxs-lookup"><span data-stu-id="a1a55-141">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="a1a55-142">尽管您不通常需要指定特性显式，目标的有效值*目标*特性中所示下表中，以及用法的示例。</span><span class="sxs-lookup"><span data-stu-id="a1a55-142">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute are shown in the following table, along with examples of usage.</span></span>

<table>
  <tr>
    <th><span data-ttu-id="a1a55-143">特性目标</span><span class="sxs-lookup"><span data-stu-id="a1a55-143">Attribute target</span></span></td>
    <th><span data-ttu-id="a1a55-144">示例</span><span class="sxs-lookup"><span data-stu-id="a1a55-144">Example</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="a1a55-145">程序集</span><span class="sxs-lookup"><span data-stu-id="a1a55-145">assembly</span></span></td>
    <td><span data-ttu-id="a1a55-146">`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</span><span class="sxs-lookup"><span data-stu-id="a1a55-146">`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="a1a55-147">return</span><span class="sxs-lookup"><span data-stu-id="a1a55-147">return</span></span></td>
    <td><span data-ttu-id="a1a55-148">让 function1 x: [<return: Obsolete>] int = x + 1</span><span class="sxs-lookup"><span data-stu-id="a1a55-148">`let function1 x : [<return: Obsolete>] int = x + 1`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="a1a55-149">Field — 字段</span><span class="sxs-lookup"><span data-stu-id="a1a55-149">field</span></span></td>
    <td><span data-ttu-id="a1a55-150">[<field: DefaultValue>] val 可变 x: int</span><span class="sxs-lookup"><span data-stu-id="a1a55-150">`[<field: DefaultValue>] val mutable x: int`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="a1a55-151">属性</span><span class="sxs-lookup"><span data-stu-id="a1a55-151">property</span></span></td>
    <td><span data-ttu-id="a1a55-152">[<property: Obsolete>] 这。MyProperty = x</span><span class="sxs-lookup"><span data-stu-id="a1a55-152">`[<property: Obsolete>] this.MyProperty = x`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="a1a55-153">Param</span><span class="sxs-lookup"><span data-stu-id="a1a55-153">param</span></span></td>
    <td><span data-ttu-id="a1a55-154">成员这。MyMethod ([<param: Out>] x: ref<int>) = x: = 10</span><span class="sxs-lookup"><span data-stu-id="a1a55-154">`member this.MyMethod([<param: Out>] x : ref<int>) = x := 10`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="a1a55-155">类型</span><span class="sxs-lookup"><span data-stu-id="a1a55-155">type</span></span></td>
    <td><span data-ttu-id="a1a55-156">
        ```
        [<type: StructLayout(Sequential)>] 键入 MyStruct = 结构 x： 字节 y: int 结束```
    </span><span class="sxs-lookup"><span data-stu-id="a1a55-156">
        ```
        [<type: StructLayout(Sequential)>] type MyStruct = struct x : byte y : int end ```
    </span></span></td> 
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="a1a55-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1a55-157">See Also</span></span>

[<span data-ttu-id="a1a55-158">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="a1a55-158">F# Language Reference</span></span>](index.md)
