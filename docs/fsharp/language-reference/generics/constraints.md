---
title: 约束 (F#)
description: '了解有关 F # 约束将应用于泛型类型参数在泛型类型或函数中指定的类型自变量的要求。'
ms.date: 05/16/2016
ms.openlocfilehash: f0722cafe27a4e2c38dfbf091973edb136cf5228
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="constraints"></a><span data-ttu-id="e1b14-103">约束</span><span class="sxs-lookup"><span data-stu-id="e1b14-103">Constraints</span></span>

<span data-ttu-id="e1b14-104">本主题描述约束可应用于泛型类型参数在泛型类型或函数中指定的类型自变量的要求。</span><span class="sxs-lookup"><span data-stu-id="e1b14-104">This topic describes constraints that you can apply to generic type parameters to specify the requirements for a type argument in a generic type or function.</span></span>


## <a name="syntax"></a><span data-ttu-id="e1b14-105">语法</span><span class="sxs-lookup"><span data-stu-id="e1b14-105">Syntax</span></span>

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a><span data-ttu-id="e1b14-106">备注</span><span class="sxs-lookup"><span data-stu-id="e1b14-106">Remarks</span></span>
<span data-ttu-id="e1b14-107">有几个不同的约束可用于限制可在泛型类型的类型。</span><span class="sxs-lookup"><span data-stu-id="e1b14-107">There are several different constraints you can apply to limit the types that can be used in a generic type.</span></span> <span data-ttu-id="e1b14-108">下表列出并描述这些约束。</span><span class="sxs-lookup"><span data-stu-id="e1b14-108">The following table lists and describes these constraints.</span></span>

|<span data-ttu-id="e1b14-109">约束</span><span class="sxs-lookup"><span data-stu-id="e1b14-109">Constraint</span></span>|<span data-ttu-id="e1b14-110">语法</span><span class="sxs-lookup"><span data-stu-id="e1b14-110">Syntax</span></span>|<span data-ttu-id="e1b14-111">描述</span><span class="sxs-lookup"><span data-stu-id="e1b14-111">Description</span></span>|
|----------|------|-----------|
|<span data-ttu-id="e1b14-112">类型约束</span><span class="sxs-lookup"><span data-stu-id="e1b14-112">Type Constraint</span></span>|<span data-ttu-id="e1b14-113">*类型参数*:&gt; *类型*</span><span class="sxs-lookup"><span data-stu-id="e1b14-113">*type-parameter* :&gt; *type*</span></span>|<span data-ttu-id="e1b14-114">所提供的类型必须等于或派生从指定的类型，或者，如果类型是接口，所提供的类型必须实现接口。</span><span class="sxs-lookup"><span data-stu-id="e1b14-114">The provided type must be equal to or derived from the type specified, or, if the type is an interface, the provided type must implement the interface.</span></span>|
|<span data-ttu-id="e1b14-115">Null 约束</span><span class="sxs-lookup"><span data-stu-id="e1b14-115">Null Constraint</span></span>|<span data-ttu-id="e1b14-116">*类型参数*: null</span><span class="sxs-lookup"><span data-stu-id="e1b14-116">*type-parameter* : null</span></span>|<span data-ttu-id="e1b14-117">所提供的类型必须支持 null 字面值。</span><span class="sxs-lookup"><span data-stu-id="e1b14-117">The provided type must support the null literal.</span></span> <span data-ttu-id="e1b14-118">这包括所有.NET 对象类型，但不是 F # 列表、 元组、 函数、 类、 记录或联合类型。</span><span class="sxs-lookup"><span data-stu-id="e1b14-118">This includes all .NET object types but not F# list, tuple, function, class, record, or union types.</span></span>|
|<span data-ttu-id="e1b14-119">显式成员约束</span><span class="sxs-lookup"><span data-stu-id="e1b14-119">Explicit Member Constraint</span></span>|<span data-ttu-id="e1b14-120">[(]*类型参数*[或...或*类型参数*)]: (* 成员签名 *)</span><span class="sxs-lookup"><span data-stu-id="e1b14-120">[(]*type-parameter* [or ... or *type-parameter*)] : (*member-signature *)</span></span>|<span data-ttu-id="e1b14-121">在至少其中一个提供的类型自变量必须有一个具有指定的签名; 的成员不能供公共使用。</span><span class="sxs-lookup"><span data-stu-id="e1b14-121">At least one of the type arguments provided must have a member that has the specified signature; not intended for common use.</span></span> <span data-ttu-id="e1b14-122">成员必须要么显式定义为一个显式成员约束的有效目标的类型或隐式类型扩展的一部分。</span><span class="sxs-lookup"><span data-stu-id="e1b14-122">Members must be either explicitly defined on the type or part of an implicit type extension to be valid targets for an Explicit Member Constraint.</span></span>|
|<span data-ttu-id="e1b14-123">构造函数约束</span><span class="sxs-lookup"><span data-stu-id="e1b14-123">Constructor Constraint</span></span>|<span data-ttu-id="e1b14-124">*类型参数*: (新： 单位-&gt; )</span><span class="sxs-lookup"><span data-stu-id="e1b14-124">*type-parameter* : ( new : unit -&gt; 'a )</span></span>|<span data-ttu-id="e1b14-125">所提供的类型必须具有默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="e1b14-125">The provided type must have a default constructor.</span></span>|
|<span data-ttu-id="e1b14-126">值类型约束</span><span class="sxs-lookup"><span data-stu-id="e1b14-126">Value Type Constraint</span></span>|<span data-ttu-id="e1b14-127">： 结构</span><span class="sxs-lookup"><span data-stu-id="e1b14-127">: struct</span></span>|<span data-ttu-id="e1b14-128">所提供的类型必须是一个.NET 值类型。</span><span class="sxs-lookup"><span data-stu-id="e1b14-128">The provided type must be a .NET value type.</span></span>|
|<span data-ttu-id="e1b14-129">引用类型约束</span><span class="sxs-lookup"><span data-stu-id="e1b14-129">Reference Type Constraint</span></span>|<span data-ttu-id="e1b14-130">： 不结构</span><span class="sxs-lookup"><span data-stu-id="e1b14-130">: not struct</span></span>|<span data-ttu-id="e1b14-131">所提供的类型必须是.NET 引用类型。</span><span class="sxs-lookup"><span data-stu-id="e1b14-131">The provided type must be a .NET reference type.</span></span>|
|<span data-ttu-id="e1b14-132">枚举类型约束</span><span class="sxs-lookup"><span data-stu-id="e1b14-132">Enumeration Type Constraint</span></span>|<span data-ttu-id="e1b14-133">： 枚举&lt;*基础类型*&gt;</span><span class="sxs-lookup"><span data-stu-id="e1b14-133">: enum&lt;*underlying-type*&gt;</span></span>|<span data-ttu-id="e1b14-134">所提供的类型必须是具有指定的基础类型; 的枚举的类型不能供公共使用。</span><span class="sxs-lookup"><span data-stu-id="e1b14-134">The provided type must be an enumerated type that has the specified underlying type; not intended for common use.</span></span>|
|<span data-ttu-id="e1b14-135">委托约束</span><span class="sxs-lookup"><span data-stu-id="e1b14-135">Delegate Constraint</span></span>|<span data-ttu-id="e1b14-136">： 委托&lt;*元组参数类型*，*返回类型*&gt;</span><span class="sxs-lookup"><span data-stu-id="e1b14-136">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span></span>|<span data-ttu-id="e1b14-137">所提供的类型必须是委托类型具有指定的参数和返回值;不能供公共使用。</span><span class="sxs-lookup"><span data-stu-id="e1b14-137">The provided type must be a delegate type that has the specified arguments and return value; not intended for common use.</span></span>|
|<span data-ttu-id="e1b14-138">比较约束</span><span class="sxs-lookup"><span data-stu-id="e1b14-138">Comparison Constraint</span></span>|<span data-ttu-id="e1b14-139">： 比较</span><span class="sxs-lookup"><span data-stu-id="e1b14-139">: comparison</span></span>|<span data-ttu-id="e1b14-140">所提供的类型必须支持比较。</span><span class="sxs-lookup"><span data-stu-id="e1b14-140">The provided type must support comparison.</span></span>|
|<span data-ttu-id="e1b14-141">等同性约束</span><span class="sxs-lookup"><span data-stu-id="e1b14-141">Equality Constraint</span></span>|<span data-ttu-id="e1b14-142">： 相等</span><span class="sxs-lookup"><span data-stu-id="e1b14-142">: equality</span></span>|<span data-ttu-id="e1b14-143">所提供的类型必须支持相等性。</span><span class="sxs-lookup"><span data-stu-id="e1b14-143">The provided type must support equality.</span></span>|
|<span data-ttu-id="e1b14-144">非托管的约束</span><span class="sxs-lookup"><span data-stu-id="e1b14-144">Unmanaged Constraint</span></span>|<span data-ttu-id="e1b14-145">： 非托管</span><span class="sxs-lookup"><span data-stu-id="e1b14-145">: unmanaged</span></span>|<span data-ttu-id="e1b14-146">所提供的类型必须是非托管的类型。</span><span class="sxs-lookup"><span data-stu-id="e1b14-146">The provided type must be an unmanaged type.</span></span> <span data-ttu-id="e1b14-147">非托管的类型包括： 任一某些基元类型 (`sbyte`， `byte`， `char`， `nativeint`， `unativeint`， `float32`， `float`， `int16`， `uint16`， `int32`， `uint32`， `int64`， `uint64`，或`decimal`)，枚举类型`nativeptr&lt;_&gt;`，或其字段都为非托管的类型的非泛型结构。</span><span class="sxs-lookup"><span data-stu-id="e1b14-147">Unmanaged types are either certain primitive types (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, or `decimal`), enumeration types, `nativeptr&lt;_&gt;`, or a non-generic structure whose fields are all unmanaged types.</span></span>|
<span data-ttu-id="e1b14-148">你需要添加约束，当你的代码必须使用通常在约束类型但不是在类型上可用的功能时。</span><span class="sxs-lookup"><span data-stu-id="e1b14-148">You have to add a constraint when your code has to use a feature that is available on the constraint type but not on types in general.</span></span> <span data-ttu-id="e1b14-149">例如，如果你使用的类型约束指定类类型，你可以使用任意一种该类中的泛型函数或类型的方法。</span><span class="sxs-lookup"><span data-stu-id="e1b14-149">For example, if you use the type constraint to specify a class type, you can use any one of the methods of that class in the generic function or type.</span></span>

<span data-ttu-id="e1b14-150">指定约束因有时需要显式，编写类型参数时不指定约束，编译器具有无法验证你使用的功能将可在运行时类型可能提供任何类型参数。</span><span class="sxs-lookup"><span data-stu-id="e1b14-150">Specifying constraints is sometimes required when writing type parameters explicitly, because without a constraint, the compiler has no way of verifying that the features that you are using will be available on any type that might be supplied at run time for the type parameter.</span></span>

<span data-ttu-id="e1b14-151">F # 代码中使用的最常见约束不指定基类或接口的类型约束。</span><span class="sxs-lookup"><span data-stu-id="e1b14-151">The most common constraints you use in F# code are type constraints that specify base classes or interfaces.</span></span> <span data-ttu-id="e1b14-152">其他约束也用于 F # 库实现某些功能，例如显式成员约束，用于实现针对算术运算符重载的运算符也提供了主要是因为 F # 支持完整公共语言运行时支持的组的约束。</span><span class="sxs-lookup"><span data-stu-id="e1b14-152">The other constraints are either used by the F# library to implement certain functionality, such as the explicit member constraint, which is used to implement operator overloading for arithmetic operators, or are provided mainly because F# supports the complete set of constraints that is supported by the common language runtime.</span></span>

<span data-ttu-id="e1b14-153">在类型推理过程中，一些约束会自动由编译器推断。</span><span class="sxs-lookup"><span data-stu-id="e1b14-153">During the type inference process, some constraints are inferred automatically by the compiler.</span></span> <span data-ttu-id="e1b14-154">例如，如果你使用`+`函数中的运算符，编译器推断出在表达式中使用的变量类型显式成员约束。</span><span class="sxs-lookup"><span data-stu-id="e1b14-154">For example, if you use the `+` operator in a function, the compiler infers an explicit member constraint on variable types that are used in the expression.</span></span>

<span data-ttu-id="e1b14-155">下面的代码演示了一些约束声明。</span><span class="sxs-lookup"><span data-stu-id="e1b14-155">The following code illustrates some constraint declarations.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e1b14-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1b14-156">See Also</span></span>
[<span data-ttu-id="e1b14-157">泛型</span><span class="sxs-lookup"><span data-stu-id="e1b14-157">Generics</span></span>](index.md)

[<span data-ttu-id="e1b14-158">约束</span><span class="sxs-lookup"><span data-stu-id="e1b14-158">Constraints</span></span>](constraints.md)
