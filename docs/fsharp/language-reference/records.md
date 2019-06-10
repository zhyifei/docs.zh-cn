---
title: 记录
description: 了解如何F#记录表示已命名的值，可选择包含成员的简单聚合。
ms.date: 06/09/2019
ms.openlocfilehash: cfb8de8272b479571119ae4cf91ea1d6fd5db73c
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816189"
---
# <a name="records"></a><span data-ttu-id="6b443-103">记录</span><span class="sxs-lookup"><span data-stu-id="6b443-103">Records</span></span>

<span data-ttu-id="6b443-104">记录表示已命名值的简单聚合，可选择包含成员。</span><span class="sxs-lookup"><span data-stu-id="6b443-104">Records represent simple aggregates of named values, optionally with members.</span></span> <span data-ttu-id="6b443-105">它们可以是结构或引用类型。</span><span class="sxs-lookup"><span data-stu-id="6b443-105">They can either be structs or reference types.</span></span>  <span data-ttu-id="6b443-106">它们是默认情况下引用类型。</span><span class="sxs-lookup"><span data-stu-id="6b443-106">They are reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="6b443-107">语法</span><span class="sxs-lookup"><span data-stu-id="6b443-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] typename =
    { [ mutable ] label1 : type1;
      [ mutable ] label2 : type2;
      ... }
    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="6b443-108">备注</span><span class="sxs-lookup"><span data-stu-id="6b443-108">Remarks</span></span>

<span data-ttu-id="6b443-109">在上述语法中， *typename*是记录类型的名称*label1*并*label2*都是名称的值，称为*标签*，并*type1*并*type2*是这些值的类型。</span><span class="sxs-lookup"><span data-stu-id="6b443-109">In the previous syntax, *typename* is the name of the record type, *label1* and *label2* are names of values, referred to as *labels*, and *type1* and *type2* are the types of these values.</span></span> <span data-ttu-id="6b443-110">*成员列表中*是成员的类型的可选列表。</span><span class="sxs-lookup"><span data-stu-id="6b443-110">*member-list* is the optional list of members for the type.</span></span>  <span data-ttu-id="6b443-111">可以使用`[<Struct>]`属性来创建结构记录而不是它是引用类型的记录。</span><span class="sxs-lookup"><span data-stu-id="6b443-111">You can use the `[<Struct>]` attribute to create a struct record rather than a record which is a reference type.</span></span>

<span data-ttu-id="6b443-112">以下是一些示例。</span><span class="sxs-lookup"><span data-stu-id="6b443-112">Following are some examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

<span data-ttu-id="6b443-113">单独的行上的每个标签时，分号是可选的。</span><span class="sxs-lookup"><span data-stu-id="6b443-113">When each label is on a separate line, the semicolon is optional.</span></span>

<span data-ttu-id="6b443-114">可以在名为的表达式中设置值*记录表达式*。</span><span class="sxs-lookup"><span data-stu-id="6b443-114">You can set values in expressions known as *record expressions*.</span></span> <span data-ttu-id="6b443-115">编译器将推断的类型使用 （如果足够不同于其他记录类型的标签） 的标签。</span><span class="sxs-lookup"><span data-stu-id="6b443-115">The compiler infers the type from the labels used (if the labels are sufficiently distinct from those of other record types).</span></span> <span data-ttu-id="6b443-116">大括号 （{}） 括住记录表达式。</span><span class="sxs-lookup"><span data-stu-id="6b443-116">Braces ({ }) enclose the record expression.</span></span> <span data-ttu-id="6b443-117">下面的代码演示初始化含有三个浮点元素带有标签的记录的记录表达式`x`，`y`和`z`。</span><span class="sxs-lookup"><span data-stu-id="6b443-117">The following code shows a record expression that initializes a record with three float elements with labels `x`, `y` and `z`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

<span data-ttu-id="6b443-118">如果可能还具有相同标签的另一种类型，则不要使用缩写形式。</span><span class="sxs-lookup"><span data-stu-id="6b443-118">Do not use the shortened form if there could be another type that also has the same labels.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

<span data-ttu-id="6b443-119">最近声明的类型的标签优先于那些以前声明的类型，因此，在上述示例中，`mypoint3D`被推断为`Point3D`。</span><span class="sxs-lookup"><span data-stu-id="6b443-119">The labels of the most recently declared type take precedence over those of the previously declared type, so in the preceding example, `mypoint3D` is inferred to be `Point3D`.</span></span> <span data-ttu-id="6b443-120">您可以显式指定记录类型，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="6b443-120">You can explicitly specify the record type, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

<span data-ttu-id="6b443-121">可以就像类类型的记录类型的定义方法。</span><span class="sxs-lookup"><span data-stu-id="6b443-121">Methods can be defined for record types just as for class types.</span></span>

## <a name="creating-records-by-using-record-expressions"></a><span data-ttu-id="6b443-122">使用记录表达式创建记录</span><span class="sxs-lookup"><span data-stu-id="6b443-122">Creating Records by Using Record Expressions</span></span>

<span data-ttu-id="6b443-123">可以通过使用记录中定义的标签初始化记录。</span><span class="sxs-lookup"><span data-stu-id="6b443-123">You can initialize records by using the labels that are defined in the record.</span></span> <span data-ttu-id="6b443-124">一个表达式，此方式被称为*记录表达式*。</span><span class="sxs-lookup"><span data-stu-id="6b443-124">An expression that does this is referred to as a *record expression*.</span></span> <span data-ttu-id="6b443-125">使用大括号括住记录表达式并使用分号作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="6b443-125">Use braces to enclose the record expression and use the semicolon as a delimiter.</span></span>

<span data-ttu-id="6b443-126">下面的示例演示如何创建一条记录。</span><span class="sxs-lookup"><span data-stu-id="6b443-126">The following example shows how to create a record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

<span data-ttu-id="6b443-127">最后一个字段中记录表达式和类型定义中后面的分号是可选的而不考虑字段是否都在同一行。</span><span class="sxs-lookup"><span data-stu-id="6b443-127">The semicolons after the last field in the record expression and in the type definition are optional, regardless of whether the fields are all in one line.</span></span>

<span data-ttu-id="6b443-128">创建一条记录时，必须提供每个字段的值。</span><span class="sxs-lookup"><span data-stu-id="6b443-128">When you create a record, you must supply values for each field.</span></span> <span data-ttu-id="6b443-129">不能引用任何字段的初始化表达式中的其他字段的值。</span><span class="sxs-lookup"><span data-stu-id="6b443-129">You cannot refer to the values of other fields in the initialization expression for any field.</span></span>

<span data-ttu-id="6b443-130">在下面的代码的类型`myRecord2`推断出的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="6b443-130">In the following code, the type of `myRecord2` is inferred from the names of the fields.</span></span> <span data-ttu-id="6b443-131">（可选） 可以显式指定类型名称。</span><span class="sxs-lookup"><span data-stu-id="6b443-131">Optionally, you can specify the type name explicitly.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="6b443-132">如果您需要复制现有记录，并可能更改的某些字段值，可记录构造的另一种形式。</span><span class="sxs-lookup"><span data-stu-id="6b443-132">Another form of record construction can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span> <span data-ttu-id="6b443-133">以下代码行阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="6b443-133">The following line of code illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

<span data-ttu-id="6b443-134">这种形式的记录表达式称为*复制和更新记录表达式*。</span><span class="sxs-lookup"><span data-stu-id="6b443-134">This form of the record expression is called the *copy and update record expression*.</span></span>

<span data-ttu-id="6b443-135">记录是不可变的默认设置。但是，您可以轻松创建已修改的记录，通过使用复制和更新表达式。</span><span class="sxs-lookup"><span data-stu-id="6b443-135">Records are immutable by default; however, you can easily create modified records by using a copy and update expression.</span></span> <span data-ttu-id="6b443-136">您还可显式指定可变字段。</span><span class="sxs-lookup"><span data-stu-id="6b443-136">You can also explicitly specify a mutable field.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

<span data-ttu-id="6b443-137">不要将用于记录字段的 DefaultValue 特性。</span><span class="sxs-lookup"><span data-stu-id="6b443-137">Don't use the DefaultValue attribute with record fields.</span></span> <span data-ttu-id="6b443-138">更好的方法是定义具有初始化的字段的记录的默认实例为默认值然后使用复制和更新记录表达式来设置不同于默认值的任何字段。</span><span class="sxs-lookup"><span data-stu-id="6b443-138">A better approach is to define default instances of records with fields that are initialized to default values and then use a copy and update record expression to set any fields that differ from the default values.</span></span>

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
    { Field1 : int
      Field2 : int }

let defaultRecord1 = { Field1 = 0; Field2 = 0 }
let defaultRecord2 = { Field1 = 1; Field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with Field2 = 42 }
```

## <a name="creating-mutually-recursive-records"></a><span data-ttu-id="6b443-139">创建相互递归记录</span><span class="sxs-lookup"><span data-stu-id="6b443-139">Creating Mutually Recursive Records</span></span>

<span data-ttu-id="6b443-140">一段时间时创建一条记录，你可能想让它取决于你想要定义之后的另一种类型。</span><span class="sxs-lookup"><span data-stu-id="6b443-140">Sometime when creating a record, you may want to have it depend on another type that you would like to define afterwards.</span></span> <span data-ttu-id="6b443-141">除非定义记录类型是互斥的递归，这是一个编译错误。</span><span class="sxs-lookup"><span data-stu-id="6b443-141">This is a compile error unless you define the record types to be mutually recursive.</span></span>

<span data-ttu-id="6b443-142">定义相互递归记录通过`and`关键字。</span><span class="sxs-lookup"><span data-stu-id="6b443-142">Defining mutually recursive records is done with the `and` keyword.</span></span> <span data-ttu-id="6b443-143">这样可将 2 个或更多记录类型链接在一起。</span><span class="sxs-lookup"><span data-stu-id="6b443-143">This lets you link 2 or more record types together.</span></span>

<span data-ttu-id="6b443-144">例如，下面的代码定义`Person`和`Address`为相互递归类型：</span><span class="sxs-lookup"><span data-stu-id="6b443-144">For example, the following code defines a `Person` and `Address` type as mutually recursive:</span></span>

```fsharp
// Create a Person type and use the Address type that is not defined
type Person =
  { Name: string
    Age: int
    Address: Address }
// Define the Address type which is used in the Person record
and Address =
  { Line1: string
    Line2: string
    PostCode: string }
```

<span data-ttu-id="6b443-145">如果要定义前面的示例，而无需`and`关键字，则它将无法编译。</span><span class="sxs-lookup"><span data-stu-id="6b443-145">If you were to define the previous example without the `and` keyword, then it would not compile.</span></span> <span data-ttu-id="6b443-146">`and`关键字是所必需的相互递归定义。</span><span class="sxs-lookup"><span data-stu-id="6b443-146">The `and` keyword is required for mutually recursive definitions.</span></span>

## <a name="pattern-matching-with-records"></a><span data-ttu-id="6b443-147">使用记录的模式匹配</span><span class="sxs-lookup"><span data-stu-id="6b443-147">Pattern Matching with Records</span></span>

<span data-ttu-id="6b443-148">记录可以与模式匹配一起使用。</span><span class="sxs-lookup"><span data-stu-id="6b443-148">Records can be used with pattern matching.</span></span> <span data-ttu-id="6b443-149">可以显式指定某些字段，并为匹配项时将分配其他字段所提供的变量。</span><span class="sxs-lookup"><span data-stu-id="6b443-149">You can specify some fields explicitly and provide variables for other fields that will be assigned when a match occurs.</span></span> <span data-ttu-id="6b443-150">下面的代码示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="6b443-150">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

<span data-ttu-id="6b443-151">此代码的输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="6b443-151">The output of this code is as follows.</span></span>

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a><span data-ttu-id="6b443-152">记录与类之间的差异</span><span class="sxs-lookup"><span data-stu-id="6b443-152">Differences Between Records and Classes</span></span>

<span data-ttu-id="6b443-153">记录字段与类不同，因为它们会自动公开为属性，并且它们是用于创建和复制的记录。</span><span class="sxs-lookup"><span data-stu-id="6b443-153">Record fields differ from classes in that they are automatically exposed as properties, and they are used in the creation and copying of records.</span></span> <span data-ttu-id="6b443-154">记录构造也不同于类构造。</span><span class="sxs-lookup"><span data-stu-id="6b443-154">Record construction also differs from class construction.</span></span> <span data-ttu-id="6b443-155">在一个记录类型，不能定义构造函数。</span><span class="sxs-lookup"><span data-stu-id="6b443-155">In a record type, you cannot define a constructor.</span></span> <span data-ttu-id="6b443-156">相反，本主题中所述的构造语法适用。</span><span class="sxs-lookup"><span data-stu-id="6b443-156">Instead, the construction syntax described in this topic applies.</span></span> <span data-ttu-id="6b443-157">类具有构造函数参数、 字段和属性之间没有直接关系。</span><span class="sxs-lookup"><span data-stu-id="6b443-157">Classes have no direct relationship between constructor parameters, fields, and properties.</span></span>

<span data-ttu-id="6b443-158">与联合和结构类型，类似记录具有结构相等性语义。</span><span class="sxs-lookup"><span data-stu-id="6b443-158">Like union and structure types, records have structural equality semantics.</span></span> <span data-ttu-id="6b443-159">类具有引用相等性语义。</span><span class="sxs-lookup"><span data-stu-id="6b443-159">Classes have reference equality semantics.</span></span> <span data-ttu-id="6b443-160">下面的代码示例展示了此操作。</span><span class="sxs-lookup"><span data-stu-id="6b443-160">The following code example demonstrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

<span data-ttu-id="6b443-161">此代码的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="6b443-161">The output of this code is as follows:</span></span>

```
The records are equal.
```

<span data-ttu-id="6b443-162">如果您编写与类相同的代码，因为两个值表示堆上的两个对象，并且仅地址进行比较，两个类对象将不相等 (除非类类型重写`System.Object.Equals`方法)。</span><span class="sxs-lookup"><span data-stu-id="6b443-162">If you write the same code with classes, the two class objects would be unequal because the two values would represent two objects on the heap and only the addresses would be compared (unless the class type overrides the `System.Object.Equals` method).</span></span>

<span data-ttu-id="6b443-163">如果需要引用相等性的记录，将属性添加`[<ReferenceEquality>]`记录上方。</span><span class="sxs-lookup"><span data-stu-id="6b443-163">If you need reference equality for records, add the attribute `[<ReferenceEquality>]` above the record.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b443-164">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b443-164">See also</span></span>

- [<span data-ttu-id="6b443-165">F# 类型</span><span class="sxs-lookup"><span data-stu-id="6b443-165">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="6b443-166">类</span><span class="sxs-lookup"><span data-stu-id="6b443-166">Classes</span></span>](classes.md)
- [<span data-ttu-id="6b443-167">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="6b443-167">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="6b443-168">Reference-Equality</span><span class="sxs-lookup"><span data-stu-id="6b443-168">Reference-Equality</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)
- [<span data-ttu-id="6b443-169">模式匹配</span><span class="sxs-lookup"><span data-stu-id="6b443-169">Pattern Matching</span></span>](pattern-matching.md)
