---
title: 特性
description: 了解属性F#如何使元数据应用于编程构造。
ms.date: 05/16/2016
ms.openlocfilehash: 3f3c3469192c09aa51f31ef3f00aca0196e3c382
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630087"
---
# <a name="attributes"></a><span data-ttu-id="75a0d-103">特性</span><span class="sxs-lookup"><span data-stu-id="75a0d-103">Attributes</span></span>

<span data-ttu-id="75a0d-104">特性使元数据可以应用于编程构造。</span><span class="sxs-lookup"><span data-stu-id="75a0d-104">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="75a0d-105">语法</span><span class="sxs-lookup"><span data-stu-id="75a0d-105">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="75a0d-106">备注</span><span class="sxs-lookup"><span data-stu-id="75a0d-106">Remarks</span></span>

<span data-ttu-id="75a0d-107">在前面的语法中,*目标*是可选的, 如果存在, 则指定应用该属性的程序实体的类型。</span><span class="sxs-lookup"><span data-stu-id="75a0d-107">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="75a0d-108">*目标*的有效值显示在本文档后面的表中。</span><span class="sxs-lookup"><span data-stu-id="75a0d-108">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="75a0d-109">*特性名称*是指具有有效属性类型的名称 (可能用命名空间限定), 其中使用或不使用通常在`Attribute`属性类型名称中使用的后缀。</span><span class="sxs-lookup"><span data-stu-id="75a0d-109">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="75a0d-110">例如, `Obsolete`在此上下文`ObsoleteAttribute`中, 类型只能缩短到。</span><span class="sxs-lookup"><span data-stu-id="75a0d-110">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="75a0d-111">*参数*是属性类型的构造函数的参数。</span><span class="sxs-lookup"><span data-stu-id="75a0d-111">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="75a0d-112">如果特性具有默认构造函数, 则可以省略参数列表和括号。</span><span class="sxs-lookup"><span data-stu-id="75a0d-112">If an attribute has a default constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="75a0d-113">特性支持位置参数和命名参数。</span><span class="sxs-lookup"><span data-stu-id="75a0d-113">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="75a0d-114">*位置参数*是按其出现顺序使用的参数。</span><span class="sxs-lookup"><span data-stu-id="75a0d-114">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="75a0d-115">如果特性具有公共属性, 则可以使用命名参数。</span><span class="sxs-lookup"><span data-stu-id="75a0d-115">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="75a0d-116">可以通过在参数列表中使用以下语法来设置这些参数。</span><span class="sxs-lookup"><span data-stu-id="75a0d-116">You can set these by using the following syntax in the argument list.</span></span>

```
*property-name* = *property-value*
```

<span data-ttu-id="75a0d-117">此类属性初始化可以按任意顺序进行, 但必须遵循任何位置自变量。</span><span class="sxs-lookup"><span data-stu-id="75a0d-117">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="75a0d-118">下面是使用位置参数和属性初始化的特性的一个示例。</span><span class="sxs-lookup"><span data-stu-id="75a0d-118">Following is an example of an attribute that uses positional arguments and property initializations.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="75a0d-119">在此示例中, 属性为`DllImportAttribute`, 此处以缩写形式使用。</span><span class="sxs-lookup"><span data-stu-id="75a0d-119">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="75a0d-120">第一个参数是位置参数, 第二个参数是一个属性。</span><span class="sxs-lookup"><span data-stu-id="75a0d-120">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="75a0d-121">特性是一个 .NET 编程构造, 使称为*属性*的对象可与类型或其他程序元素相关联。</span><span class="sxs-lookup"><span data-stu-id="75a0d-121">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="75a0d-122">应用特性的程序元素称为*属性目标*。</span><span class="sxs-lookup"><span data-stu-id="75a0d-122">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="75a0d-123">该属性通常包含有关其目标的元数据。</span><span class="sxs-lookup"><span data-stu-id="75a0d-123">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="75a0d-124">在这种情况下, 元数据可以是除字段和成员之外的任何类型的数据。</span><span class="sxs-lookup"><span data-stu-id="75a0d-124">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="75a0d-125">中F#的属性可应用于以下编程构造: 函数、方法、程序集、模块、类型 (类、记录、结构、接口、委托、枚举、联合等等)、构造函数、属性、字段、参数、类型参数和返回值。</span><span class="sxs-lookup"><span data-stu-id="75a0d-125">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="75a0d-126">不允许在类、 `let`表达式或工作流表达式中的绑定上使用特性。</span><span class="sxs-lookup"><span data-stu-id="75a0d-126">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="75a0d-127">通常, 特性声明直接出现在属性目标的声明之前。</span><span class="sxs-lookup"><span data-stu-id="75a0d-127">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="75a0d-128">可以将多个属性声明一起使用, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="75a0d-128">Multiple attribute declarations can be used together, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="75a0d-129">可以通过使用 .NET 反射在运行时查询属性。</span><span class="sxs-lookup"><span data-stu-id="75a0d-129">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="75a0d-130">如前面的代码示例中所示, 可以单独声明多个特性, 也可以在一组方括号中将它们声明为, 前提是使用分号分隔各个特性和构造函数, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="75a0d-130">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as shown here.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="75a0d-131">通常, 所遇到的`Obsolete`属性包括属性、安全注意事项属性、COM 支持的属性、与代码所有权相关的属性, 以及指示类型是否可以序列化的属性。</span><span class="sxs-lookup"><span data-stu-id="75a0d-131">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="75a0d-132">下面的示例演示`Obsolete`属性的用法。</span><span class="sxs-lookup"><span data-stu-id="75a0d-132">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="75a0d-133">对于特性目标`assembly`和`module`, 将特性应用于程序集中的顶级`do`绑定。</span><span class="sxs-lookup"><span data-stu-id="75a0d-133">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="75a0d-134">可以在属性声明中`assembly`包含`module`单词或, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="75a0d-134">You can include the word `assembly` or `module` in the attribute declaration, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="75a0d-135">如果省略应用`do`于绑定的属性的属性目标, 则编译器将F#尝试确定对于该属性有意义的属性目标。</span><span class="sxs-lookup"><span data-stu-id="75a0d-135">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="75a0d-136">许多特性类都有一个类型`System.AttributeUsageAttribute`为的属性, 其中包括有关该特性支持的可能目标的信息。</span><span class="sxs-lookup"><span data-stu-id="75a0d-136">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="75a0d-137">`System.AttributeUsageAttribute`如果指示该特性支持作为目标的函数, 则会将该特性应用于程序的主入口点。</span><span class="sxs-lookup"><span data-stu-id="75a0d-137">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="75a0d-138">`System.AttributeUsageAttribute`如果指示特性支持作为目标的程序集, 则编译器会将特性应用于程序集。</span><span class="sxs-lookup"><span data-stu-id="75a0d-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="75a0d-139">大多数特性并不适用于函数和程序集, 但在这些特性的情况下, 会将特性应用于程序的 main 函数。</span><span class="sxs-lookup"><span data-stu-id="75a0d-139">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="75a0d-140">如果显式指定了特性目标, 则该特性将应用于指定的目标。</span><span class="sxs-lookup"><span data-stu-id="75a0d-140">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="75a0d-141">尽管通常不需要显式指定属性目标, 但下表中显示了属性中 "*目标*" 的有效值, 以及用法示例。</span><span class="sxs-lookup"><span data-stu-id="75a0d-141">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute are shown in the following table, along with examples of usage.</span></span>

<table>
  <tr>
    <th><span data-ttu-id="75a0d-142">特性目标</span><span class="sxs-lookup"><span data-stu-id="75a0d-142">Attribute target</span></span></td>
    <th><span data-ttu-id="75a0d-143">示例</span><span class="sxs-lookup"><span data-stu-id="75a0d-143">Example</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="75a0d-144">程序集</span><span class="sxs-lookup"><span data-stu-id="75a0d-144">assembly</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;assembly: AssemblyVersionAttribute("1.0.0.0")&gt;]<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="75a0d-145">return</span><span class="sxs-lookup"><span data-stu-id="75a0d-145">return</span></span></td>
    <td><pre lang="fsharp"><code>let function1 x : [&lt;return: Obsolete&gt;] int = x + 1<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="75a0d-146">Field — 字段</span><span class="sxs-lookup"><span data-stu-id="75a0d-146">field</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;field: DefaultValue&gt;] val mutable x: int<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="75a0d-147">属性</span><span class="sxs-lookup"><span data-stu-id="75a0d-147">property</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;property: Obsolete&gt;] this.MyProperty = x<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="75a0d-148">param</span><span class="sxs-lookup"><span data-stu-id="75a0d-148">param</span></span></td>
    <td><pre lang="fsharp"><code>member this.MyMethod([&lt;param: Out&gt;] x : ref&lt;int&gt;) = x := 10<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="75a0d-149">类型</span><span class="sxs-lookup"><span data-stu-id="75a0d-149">type</span></span></td>
    <td>
        <pre lang="fsharp"><code>
        [&lt;type: StructLayout(Sequential)&gt;] 
        type MyStruct = 
        struct 
        x : byte
        y : int
        end
        <code></pre>
    </td>
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="75a0d-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="75a0d-150">See also</span></span>

- [<span data-ttu-id="75a0d-151">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="75a0d-151">F# Language Reference</span></span>](index.md)
