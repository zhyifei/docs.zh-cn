---
title: "约束 (F#)"
description: "了解有关 F # 约束将应用于泛型类型参数在泛型类型或函数中指定的类型自变量的要求。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2f232a3a-9486-48fb-9759-f23404ed4b52
ms.openlocfilehash: 91854fd2f692688e0f1c27aba1422eff64156048
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="constraints"></a><span data-ttu-id="71dff-104">约束</span><span class="sxs-lookup"><span data-stu-id="71dff-104">Constraints</span></span>

<span data-ttu-id="71dff-105">本主题描述约束可应用于泛型类型参数在泛型类型或函数中指定的类型自变量的要求。</span><span class="sxs-lookup"><span data-stu-id="71dff-105">This topic describes constraints that you can apply to generic type parameters to specify the requirements for a type argument in a generic type or function.</span></span>


## <a name="syntax"></a><span data-ttu-id="71dff-106">语法</span><span class="sxs-lookup"><span data-stu-id="71dff-106">Syntax</span></span>

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a><span data-ttu-id="71dff-107">备注</span><span class="sxs-lookup"><span data-stu-id="71dff-107">Remarks</span></span>
<span data-ttu-id="71dff-108">有几个不同的约束可用于限制可在泛型类型的类型。</span><span class="sxs-lookup"><span data-stu-id="71dff-108">There are several different constraints you can apply to limit the types that can be used in a generic type.</span></span> <span data-ttu-id="71dff-109">下表列出并描述这些约束。</span><span class="sxs-lookup"><span data-stu-id="71dff-109">The following table lists and describes these constraints.</span></span>

|<span data-ttu-id="71dff-110">约束</span><span class="sxs-lookup"><span data-stu-id="71dff-110">Constraint</span></span>|<span data-ttu-id="71dff-111">语法</span><span class="sxs-lookup"><span data-stu-id="71dff-111">Syntax</span></span>|<span data-ttu-id="71dff-112">描述</span><span class="sxs-lookup"><span data-stu-id="71dff-112">Description</span></span>|
|----------|------|-----------|
|<span data-ttu-id="71dff-113">类型约束</span><span class="sxs-lookup"><span data-stu-id="71dff-113">Type Constraint</span></span>|<span data-ttu-id="71dff-114">*类型参数*:&gt; *类型*</span><span class="sxs-lookup"><span data-stu-id="71dff-114">*type-parameter* :&gt; *type*</span></span>|<span data-ttu-id="71dff-115">所提供的类型必须等于或派生从指定的类型，或者，如果类型是接口，所提供的类型必须实现接口。</span><span class="sxs-lookup"><span data-stu-id="71dff-115">The provided type must be equal to or derived from the type specified, or, if the type is an interface, the provided type must implement the interface.</span></span>|
|<span data-ttu-id="71dff-116">Null 约束</span><span class="sxs-lookup"><span data-stu-id="71dff-116">Null Constraint</span></span>|<span data-ttu-id="71dff-117">*类型参数*: null</span><span class="sxs-lookup"><span data-stu-id="71dff-117">*type-parameter* : null</span></span>|<span data-ttu-id="71dff-118">所提供的类型必须支持 null 字面值。</span><span class="sxs-lookup"><span data-stu-id="71dff-118">The provided type must support the null literal.</span></span> <span data-ttu-id="71dff-119">这包括所有.NET 对象类型，但不是 F # 列表、 元组、 函数、 类、 记录或联合类型。</span><span class="sxs-lookup"><span data-stu-id="71dff-119">This includes all .NET object types but not F# list, tuple, function, class, record, or union types.</span></span>|
|<span data-ttu-id="71dff-120">显式成员约束</span><span class="sxs-lookup"><span data-stu-id="71dff-120">Explicit Member Constraint</span></span>|<span data-ttu-id="71dff-121">[（)]*类型参数*[或...或*类型参数*)]: (* 成员签名 *)</span><span class="sxs-lookup"><span data-stu-id="71dff-121">[(]*type-parameter* [or ... or *type-parameter*)] : (*member-signature *)</span></span>|<span data-ttu-id="71dff-122">在至少其中一个提供的类型自变量必须有一个具有指定的签名; 的成员不能供公共使用。</span><span class="sxs-lookup"><span data-stu-id="71dff-122">At least one of the type arguments provided must have a member that has the specified signature; not intended for common use.</span></span> <span data-ttu-id="71dff-123">成员必须要么显式定义为一个显式成员约束的有效目标的类型或隐式类型扩展的一部分。</span><span class="sxs-lookup"><span data-stu-id="71dff-123">Members must be either explicitly defined on the type or part of an implicit type extension to be valid targets for an Explicit Member Constraint.</span></span>|
|<span data-ttu-id="71dff-124">构造函数约束</span><span class="sxs-lookup"><span data-stu-id="71dff-124">Constructor Constraint</span></span>|<span data-ttu-id="71dff-125">*类型参数*: (新： 单位-&gt; )</span><span class="sxs-lookup"><span data-stu-id="71dff-125">*type-parameter* : ( new : unit -&gt; 'a )</span></span>|<span data-ttu-id="71dff-126">所提供的类型必须具有默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="71dff-126">The provided type must have a default constructor.</span></span>|
|<span data-ttu-id="71dff-127">值类型约束</span><span class="sxs-lookup"><span data-stu-id="71dff-127">Value Type Constraint</span></span>|<span data-ttu-id="71dff-128">： 结构</span><span class="sxs-lookup"><span data-stu-id="71dff-128">: struct</span></span>|<span data-ttu-id="71dff-129">所提供的类型必须是一个.NET 值类型。</span><span class="sxs-lookup"><span data-stu-id="71dff-129">The provided type must be a .NET value type.</span></span>|
|<span data-ttu-id="71dff-130">引用类型约束</span><span class="sxs-lookup"><span data-stu-id="71dff-130">Reference Type Constraint</span></span>|<span data-ttu-id="71dff-131">： 不结构</span><span class="sxs-lookup"><span data-stu-id="71dff-131">: not struct</span></span>|<span data-ttu-id="71dff-132">所提供的类型必须是.NET 引用类型。</span><span class="sxs-lookup"><span data-stu-id="71dff-132">The provided type must be a .NET reference type.</span></span>|
|<span data-ttu-id="71dff-133">枚举类型约束</span><span class="sxs-lookup"><span data-stu-id="71dff-133">Enumeration Type Constraint</span></span>|<span data-ttu-id="71dff-134">： 枚举&lt;*基础类型*&gt;</span><span class="sxs-lookup"><span data-stu-id="71dff-134">: enum&lt;*underlying-type*&gt;</span></span>|<span data-ttu-id="71dff-135">所提供的类型必须是具有指定的基础类型; 的枚举的类型不能供公共使用。</span><span class="sxs-lookup"><span data-stu-id="71dff-135">The provided type must be an enumerated type that has the specified underlying type; not intended for common use.</span></span>|
|<span data-ttu-id="71dff-136">委托约束</span><span class="sxs-lookup"><span data-stu-id="71dff-136">Delegate Constraint</span></span>|<span data-ttu-id="71dff-137">： 委托&lt;*元组参数类型*，*返回类型*&gt;</span><span class="sxs-lookup"><span data-stu-id="71dff-137">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span></span>|<span data-ttu-id="71dff-138">所提供的类型必须是委托类型具有指定的参数和返回值;不能供公共使用。</span><span class="sxs-lookup"><span data-stu-id="71dff-138">The provided type must be a delegate type that has the specified arguments and return value; not intended for common use.</span></span>|
|<span data-ttu-id="71dff-139">比较约束</span><span class="sxs-lookup"><span data-stu-id="71dff-139">Comparison Constraint</span></span>|<span data-ttu-id="71dff-140">： 比较</span><span class="sxs-lookup"><span data-stu-id="71dff-140">: comparison</span></span>|<span data-ttu-id="71dff-141">所提供的类型必须支持比较。</span><span class="sxs-lookup"><span data-stu-id="71dff-141">The provided type must support comparison.</span></span>|
|<span data-ttu-id="71dff-142">等同性约束</span><span class="sxs-lookup"><span data-stu-id="71dff-142">Equality Constraint</span></span>|<span data-ttu-id="71dff-143">： 相等</span><span class="sxs-lookup"><span data-stu-id="71dff-143">: equality</span></span>|<span data-ttu-id="71dff-144">所提供的类型必须支持相等性。</span><span class="sxs-lookup"><span data-stu-id="71dff-144">The provided type must support equality.</span></span>|
|<span data-ttu-id="71dff-145">非托管的约束</span><span class="sxs-lookup"><span data-stu-id="71dff-145">Unmanaged Constraint</span></span>|<span data-ttu-id="71dff-146">： 非托管</span><span class="sxs-lookup"><span data-stu-id="71dff-146">: unmanaged</span></span>|<span data-ttu-id="71dff-147">所提供的类型必须是非托管的类型。</span><span class="sxs-lookup"><span data-stu-id="71dff-147">The provided type must be an unmanaged type.</span></span> <span data-ttu-id="71dff-148">非托管的类型包括： 任一某些基元类型 (`sbyte`， `byte`， `char`， `nativeint`， `unativeint`， `float32`， `float`， `int16`， `uint16`， `int32`， `uint32`， `int64`， `uint64`，或`decimal`)，枚举类型`nativeptr&lt;_&gt;`，或其字段都为非托管的类型的非泛型结构。</span><span class="sxs-lookup"><span data-stu-id="71dff-148">Unmanaged types are either certain primitive types (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, or `decimal`), enumeration types, `nativeptr&lt;_&gt;`, or a non-generic structure whose fields are all unmanaged types.</span></span>|
<span data-ttu-id="71dff-149">你需要添加约束，当你的代码必须使用通常在约束类型但不是在类型上可用的功能时。</span><span class="sxs-lookup"><span data-stu-id="71dff-149">You have to add a constraint when your code has to use a feature that is available on the constraint type but not on types in general.</span></span> <span data-ttu-id="71dff-150">例如，如果你使用的类型约束指定类类型，你可以使用任意一种该类中的泛型函数或类型的方法。</span><span class="sxs-lookup"><span data-stu-id="71dff-150">For example, if you use the type constraint to specify a class type, you can use any one of the methods of that class in the generic function or type.</span></span>

<span data-ttu-id="71dff-151">指定约束因有时需要显式，编写类型参数时不指定约束，编译器具有无法验证你使用的功能将可在运行时类型可能提供任何类型参数。</span><span class="sxs-lookup"><span data-stu-id="71dff-151">Specifying constraints is sometimes required when writing type parameters explicitly, because without a constraint, the compiler has no way of verifying that the features that you are using will be available on any type that might be supplied at run time for the type parameter.</span></span>

<span data-ttu-id="71dff-152">F # 代码中使用的最常见约束不指定基类或接口的类型约束。</span><span class="sxs-lookup"><span data-stu-id="71dff-152">The most common constraints you use in F# code are type constraints that specify base classes or interfaces.</span></span> <span data-ttu-id="71dff-153">其他约束也用于 F # 库实现某些功能，例如显式成员约束，用于实现针对算术运算符重载的运算符也提供了主要是因为 F # 支持完整公共语言运行时支持的组的约束。</span><span class="sxs-lookup"><span data-stu-id="71dff-153">The other constraints are either used by the F# library to implement certain functionality, such as the explicit member constraint, which is used to implement operator overloading for arithmetic operators, or are provided mainly because F# supports the complete set of constraints that is supported by the common language runtime.</span></span>

<span data-ttu-id="71dff-154">在类型推理过程中，一些约束会自动由编译器推断。</span><span class="sxs-lookup"><span data-stu-id="71dff-154">During the type inference process, some constraints are inferred automatically by the compiler.</span></span> <span data-ttu-id="71dff-155">例如，如果你使用`+`函数中的运算符，编译器推断出在表达式中使用的变量类型显式成员约束。</span><span class="sxs-lookup"><span data-stu-id="71dff-155">For example, if you use the `+` operator in a function, the compiler infers an explicit member constraint on variable types that are used in the expression.</span></span>

<span data-ttu-id="71dff-156">下面的代码演示了一些约束声明。</span><span class="sxs-lookup"><span data-stu-id="71dff-156">The following code illustrates some constraint declarations.</span></span>

```fsharp
// Base Type Constraint
type Class1<'T when 'T :> System.Exception> =
class end

// Interface Type Constraint
type Class2<'T when 'T :> System.IComparable> = 
class end

// Null constraint
type Class3<'T when 'T : null> =
class end

// Member constraint with static member
type Class4<'T when 'T : (static member staticMethod1 : unit -> 'T) > =
class end

// Member constraint with instance member
type Class5<'T when 'T : (member Method1 : 'T -> int)> =
class end

// Member constraint with property
type Class6<'T when 'T : (member Property1 : int)> =
class end

// Constructor constraint
type Class7<'T when 'T : (new : unit -> 'T)>() =
member val Field = new 'T()

// Reference type constraint
type Class8<'T when 'T : not struct> =
class end

// Enumeration constraint with underlying value specified
type Class9<'T when 'T : enum<uint32>> =
class end

// 'T must implement IComparable, or be an array type with comparable
// elements, or be System.IntPtr or System.UIntPtr. Also, 'T must not have
// the NoComparison attribute.
type Class10<'T when 'T : comparison> =
class end

// 'T must support equality. This is true for any type that does not
// have the NoEquality attribute.
type Class11<'T when 'T : equality> =
class end

type Class12<'T when 'T : delegate<obj * System.EventArgs, unit>> =
class end

type Class13<'T when 'T : unmanaged> =
class end

// Member constraints with two type parameters
// Most often used with static type parameters in inline functions
let inline add(value1 : ^T when ^T : (static member (+) : ^T * ^T -> ^T), value2: ^T) =
value1 + value2

// ^T and ^U must support operator +
let inline heterogenousAdd(value1 : ^T when (^T or ^U) : (static member (+) : ^T * ^U -> ^T), value2 : ^U) =
value1 + value2

// If there are multiple constraints, use the and keyword to separate them.
type Class14<'T,'U when 'T : equality and 'U : equality> =
class end
```

## <a name="see-also"></a><span data-ttu-id="71dff-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71dff-157">See Also</span></span>
[<span data-ttu-id="71dff-158">泛型</span><span class="sxs-lookup"><span data-stu-id="71dff-158">Generics</span></span>](index.md)

[<span data-ttu-id="71dff-159">约束</span><span class="sxs-lookup"><span data-stu-id="71dff-159">Constraints</span></span>](constraints.md)
