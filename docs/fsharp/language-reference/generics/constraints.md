---
title: 约束 (F#)
description: '了解有关 F # 约束应用于泛型类型参数，以在泛型类型或函数中指定的类型参数的要求。'
ms.date: 05/16/2016
ms.openlocfilehash: 9534db4ffd195022366af8c993658bd94f375f53
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47081730"
---
# <a name="constraints"></a><span data-ttu-id="1be41-103">约束</span><span class="sxs-lookup"><span data-stu-id="1be41-103">Constraints</span></span>

<span data-ttu-id="1be41-104">本主题介绍可应用于泛型约束类型参数，以在泛型类型或函数中指定的类型参数的要求。</span><span class="sxs-lookup"><span data-stu-id="1be41-104">This topic describes constraints that you can apply to generic type parameters to specify the requirements for a type argument in a generic type or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="1be41-105">语法</span><span class="sxs-lookup"><span data-stu-id="1be41-105">Syntax</span></span>

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a><span data-ttu-id="1be41-106">备注</span><span class="sxs-lookup"><span data-stu-id="1be41-106">Remarks</span></span>

<span data-ttu-id="1be41-107">有几个不同的约束可用于限制可在泛型类型的类型。</span><span class="sxs-lookup"><span data-stu-id="1be41-107">There are several different constraints you can apply to limit the types that can be used in a generic type.</span></span> <span data-ttu-id="1be41-108">下表列出并描述这些约束。</span><span class="sxs-lookup"><span data-stu-id="1be41-108">The following table lists and describes these constraints.</span></span>

|<span data-ttu-id="1be41-109">约束</span><span class="sxs-lookup"><span data-stu-id="1be41-109">Constraint</span></span>|<span data-ttu-id="1be41-110">语法</span><span class="sxs-lookup"><span data-stu-id="1be41-110">Syntax</span></span>|<span data-ttu-id="1be41-111">描述</span><span class="sxs-lookup"><span data-stu-id="1be41-111">Description</span></span>|
|----------|------|-----------|
|<span data-ttu-id="1be41-112">类型约束</span><span class="sxs-lookup"><span data-stu-id="1be41-112">Type Constraint</span></span>|<span data-ttu-id="1be41-113">*类型参数*:&gt; *类型*</span><span class="sxs-lookup"><span data-stu-id="1be41-113">*type-parameter* :&gt; *type*</span></span>|<span data-ttu-id="1be41-114">提供的类型必须等于或派生从指定的类型，或者，如果该类型是接口，提供的类型必须实现接口。</span><span class="sxs-lookup"><span data-stu-id="1be41-114">The provided type must be equal to or derived from the type specified, or, if the type is an interface, the provided type must implement the interface.</span></span>|
|<span data-ttu-id="1be41-115">Null 约束</span><span class="sxs-lookup"><span data-stu-id="1be41-115">Null Constraint</span></span>|<span data-ttu-id="1be41-116">*类型参数*: null</span><span class="sxs-lookup"><span data-stu-id="1be41-116">*type-parameter* : null</span></span>|<span data-ttu-id="1be41-117">提供的类型必须支持 null 字面值。</span><span class="sxs-lookup"><span data-stu-id="1be41-117">The provided type must support the null literal.</span></span> <span data-ttu-id="1be41-118">这包括所有.NET 对象类型，但不是 F # 列表、 元组、 函数、 类、 记录或联合类型。</span><span class="sxs-lookup"><span data-stu-id="1be41-118">This includes all .NET object types but not F# list, tuple, function, class, record, or union types.</span></span>|
|<span data-ttu-id="1be41-119">显式成员约束</span><span class="sxs-lookup"><span data-stu-id="1be41-119">Explicit Member Constraint</span></span>|<span data-ttu-id="1be41-120">[（]*类型参数*[or...或*类型参数*)]: (*成员签名*)</span><span class="sxs-lookup"><span data-stu-id="1be41-120">[(]*type-parameter* [or ... or *type-parameter*)] : (*member-signature*)</span></span>|<span data-ttu-id="1be41-121">在至少其中一个提供的类型参数必须具有指定的签名; 的成员不适合公共使用。</span><span class="sxs-lookup"><span data-stu-id="1be41-121">At least one of the type arguments provided must have a member that has the specified signature; not intended for common use.</span></span> <span data-ttu-id="1be41-122">成员必须要么显式定义为显式成员约束的有效目标类型或隐式类型扩展的一部分。</span><span class="sxs-lookup"><span data-stu-id="1be41-122">Members must be either explicitly defined on the type or part of an implicit type extension to be valid targets for an Explicit Member Constraint.</span></span>|
|<span data-ttu-id="1be41-123">构造函数约束</span><span class="sxs-lookup"><span data-stu-id="1be41-123">Constructor Constraint</span></span>|<span data-ttu-id="1be41-124">*类型参数*: (新： 单元-&gt; )</span><span class="sxs-lookup"><span data-stu-id="1be41-124">*type-parameter* : ( new : unit -&gt; 'a )</span></span>|<span data-ttu-id="1be41-125">提供的类型必须具有默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="1be41-125">The provided type must have a default constructor.</span></span>|
|<span data-ttu-id="1be41-126">值类型约束</span><span class="sxs-lookup"><span data-stu-id="1be41-126">Value Type Constraint</span></span>|<span data-ttu-id="1be41-127">： 结构</span><span class="sxs-lookup"><span data-stu-id="1be41-127">: struct</span></span>|<span data-ttu-id="1be41-128">提供的类型必须是一个.NET 值类型。</span><span class="sxs-lookup"><span data-stu-id="1be41-128">The provided type must be a .NET value type.</span></span>|
|<span data-ttu-id="1be41-129">引用类型约束</span><span class="sxs-lookup"><span data-stu-id="1be41-129">Reference Type Constraint</span></span>|<span data-ttu-id="1be41-130">： 不结构</span><span class="sxs-lookup"><span data-stu-id="1be41-130">: not struct</span></span>|<span data-ttu-id="1be41-131">提供的类型必须是.NET 引用类型。</span><span class="sxs-lookup"><span data-stu-id="1be41-131">The provided type must be a .NET reference type.</span></span>|
|<span data-ttu-id="1be41-132">枚举类型约束</span><span class="sxs-lookup"><span data-stu-id="1be41-132">Enumeration Type Constraint</span></span>|<span data-ttu-id="1be41-133">： 枚举&lt;*基础类型*&gt;</span><span class="sxs-lookup"><span data-stu-id="1be41-133">: enum&lt;*underlying-type*&gt;</span></span>|<span data-ttu-id="1be41-134">提供的类型必须为枚举的类型具有指定的基础类型;不适合公共使用。</span><span class="sxs-lookup"><span data-stu-id="1be41-134">The provided type must be an enumerated type that has the specified underlying type; not intended for common use.</span></span>|
|<span data-ttu-id="1be41-135">委托约束</span><span class="sxs-lookup"><span data-stu-id="1be41-135">Delegate Constraint</span></span>|<span data-ttu-id="1be41-136">： 委托&lt;*元组参数类型*，*返回类型*&gt;</span><span class="sxs-lookup"><span data-stu-id="1be41-136">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span></span>|<span data-ttu-id="1be41-137">提供的类型必须为委托类型具有指定的参数和返回值;不适合公共使用。</span><span class="sxs-lookup"><span data-stu-id="1be41-137">The provided type must be a delegate type that has the specified arguments and return value; not intended for common use.</span></span>|
|<span data-ttu-id="1be41-138">比较约束</span><span class="sxs-lookup"><span data-stu-id="1be41-138">Comparison Constraint</span></span>|<span data-ttu-id="1be41-139">： 比较</span><span class="sxs-lookup"><span data-stu-id="1be41-139">: comparison</span></span>|<span data-ttu-id="1be41-140">提供的类型必须支持比较。</span><span class="sxs-lookup"><span data-stu-id="1be41-140">The provided type must support comparison.</span></span>|
|<span data-ttu-id="1be41-141">相等约束</span><span class="sxs-lookup"><span data-stu-id="1be41-141">Equality Constraint</span></span>|<span data-ttu-id="1be41-142">： 是否相等</span><span class="sxs-lookup"><span data-stu-id="1be41-142">: equality</span></span>|<span data-ttu-id="1be41-143">提供的类型必须支持相等性。</span><span class="sxs-lookup"><span data-stu-id="1be41-143">The provided type must support equality.</span></span>|
|<span data-ttu-id="1be41-144">非托管的约束</span><span class="sxs-lookup"><span data-stu-id="1be41-144">Unmanaged Constraint</span></span>|<span data-ttu-id="1be41-145">： 非托管</span><span class="sxs-lookup"><span data-stu-id="1be41-145">: unmanaged</span></span>|<span data-ttu-id="1be41-146">提供的类型必须是一个非托管的类型。</span><span class="sxs-lookup"><span data-stu-id="1be41-146">The provided type must be an unmanaged type.</span></span> <span data-ttu-id="1be41-147">非托管的类型都是任一特定基元类型 (`sbyte`， `byte`， `char`， `nativeint`， `unativeint`， `float32`， `float`， `int16`， `uint16`， `int32`， `uint32`， `int64`， `uint64`，或`decimal`)，枚举类型`nativeptr<_>`，或其字段都为非托管的类型的非泛型结构。</span><span class="sxs-lookup"><span data-stu-id="1be41-147">Unmanaged types are either certain primitive types (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, or `decimal`), enumeration types, `nativeptr<_>`, or a non-generic structure whose fields are all unmanaged types.</span></span>|
<span data-ttu-id="1be41-148">您必须添加约束，当你的代码必须使用一种功能，一般情况下是可在约束类型而不是在类型上时。</span><span class="sxs-lookup"><span data-stu-id="1be41-148">You have to add a constraint when your code has to use a feature that is available on the constraint type but not on types in general.</span></span> <span data-ttu-id="1be41-149">例如，如果你使用类型约束指定类类型，可以使用任何一种泛型函数或类型中的类的方法。</span><span class="sxs-lookup"><span data-stu-id="1be41-149">For example, if you use the type constraint to specify a class type, you can use any one of the methods of that class in the generic function or type.</span></span>

<span data-ttu-id="1be41-150">指定约束有时需要写入时，是类型参数显式，因为不受约束，编译器具有无法验证您使用的功能将可用于在运行时类型可能会提供任何类型参数。</span><span class="sxs-lookup"><span data-stu-id="1be41-150">Specifying constraints is sometimes required when writing type parameters explicitly, because without a constraint, the compiler has no way of verifying that the features that you are using will be available on any type that might be supplied at run time for the type parameter.</span></span>

<span data-ttu-id="1be41-151">在 F # 代码中使用的最常见约束是指定基类或接口的类型约束。</span><span class="sxs-lookup"><span data-stu-id="1be41-151">The most common constraints you use in F# code are type constraints that specify base classes or interfaces.</span></span> <span data-ttu-id="1be41-152">其他约束既用于由 F # 库实现某些功能，如用于实现的运算符重载算术运算符，由你或由主要是因为 F # 支持完整的显式成员约束公共语言运行时支持的组的约束。</span><span class="sxs-lookup"><span data-stu-id="1be41-152">The other constraints are either used by the F# library to implement certain functionality, such as the explicit member constraint, which is used to implement operator overloading for arithmetic operators, or are provided mainly because F# supports the complete set of constraints that is supported by the common language runtime.</span></span>

<span data-ttu-id="1be41-153">在类型推理过程中，某些约束会自动由编译器推断。</span><span class="sxs-lookup"><span data-stu-id="1be41-153">During the type inference process, some constraints are inferred automatically by the compiler.</span></span> <span data-ttu-id="1be41-154">例如，如果您使用`+`在函数中的运算符，编译器将推断变量类型的表达式中使用的显式成员约束。</span><span class="sxs-lookup"><span data-stu-id="1be41-154">For example, if you use the `+` operator in a function, the compiler infers an explicit member constraint on variable types that are used in the expression.</span></span>

<span data-ttu-id="1be41-155">以下代码演示了一些约束声明。</span><span class="sxs-lookup"><span data-stu-id="1be41-155">The following code illustrates some constraint declarations.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1be41-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="1be41-156">See also</span></span>

- [<span data-ttu-id="1be41-157">泛型</span><span class="sxs-lookup"><span data-stu-id="1be41-157">Generics</span></span>](index.md)
- [<span data-ttu-id="1be41-158">约束</span><span class="sxs-lookup"><span data-stu-id="1be41-158">Constraints</span></span>](constraints.md)
