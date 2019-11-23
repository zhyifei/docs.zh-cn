---
title: 用户定义数据类型（Visual Basic）
ms.date: 07/20/2015
f1_keywords:
- UserDefined
- UDT
- vb.UDT
- User-Defined
- vb.UserDefined
- vb.User-Defined
helpviewer_keywords:
- user-defined data types [Visual Basic], Visual Basic
- user-defined types
- structures [Visual Basic], as user-defined data types
- user-defined types [Visual Basic], Visual Basic
- user-defined types [Visual Basic], structure declaration
- user-defined types [Visual Basic], structures in Visual Basic
- user-defined data types [Visual Basic], structure declaration
- data types [Visual Basic], assigning
- Structure statement [Visual Basic]
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], structures in Visual Basic
- user-defined data types
- types [Visual Basic], user-defined
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
ms.openlocfilehash: d95feec3a976a38c92a215f6da58ae6324085fe8
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696870"
---
# <a name="user-defined-data-type"></a><span data-ttu-id="dfd68-102">用户定义的数据类型</span><span class="sxs-lookup"><span data-stu-id="dfd68-102">User-Defined Data Type</span></span>

<span data-ttu-id="dfd68-103">以您定义的格式保存数据。</span><span class="sxs-lookup"><span data-stu-id="dfd68-103">Holds data in a format you define.</span></span> <span data-ttu-id="dfd68-104">`Structure` 语句定义格式。</span><span class="sxs-lookup"><span data-stu-id="dfd68-104">The `Structure` statement defines the format.</span></span>

<span data-ttu-id="dfd68-105">以前版本的 Visual Basic 支持用户定义的类型（UDT）。</span><span class="sxs-lookup"><span data-stu-id="dfd68-105">Previous versions of Visual Basic support the user-defined type (UDT).</span></span> <span data-ttu-id="dfd68-106">当前版本将 UDT 扩展到*结构*。</span><span class="sxs-lookup"><span data-stu-id="dfd68-106">The current version expands the UDT to a *structure*.</span></span> <span data-ttu-id="dfd68-107">结构是一种或多种数据类型*成员*的串联。</span><span class="sxs-lookup"><span data-stu-id="dfd68-107">A structure is a concatenation of one or more *members* of various data types.</span></span> <span data-ttu-id="dfd68-108">Visual Basic 将结构视为单个单元，但你也可以单独访问其成员。</span><span class="sxs-lookup"><span data-stu-id="dfd68-108">Visual Basic treats a structure as a single unit, although you can also access its members individually.</span></span>

## <a name="remarks"></a><span data-ttu-id="dfd68-109">备注</span><span class="sxs-lookup"><span data-stu-id="dfd68-109">Remarks</span></span>

<span data-ttu-id="dfd68-110">当需要将各种数据类型组合成单个单元时，或在没有任何基本数据类型满足您的需求时，可定义和使用结构数据类型。</span><span class="sxs-lookup"><span data-stu-id="dfd68-110">Define and use a structure data type when you need to combine various data types into a single unit, or when none of the elementary data types serve your needs.</span></span>

<span data-ttu-id="dfd68-111">结构数据类型的默认值由其每个成员的默认值组合而成。</span><span class="sxs-lookup"><span data-stu-id="dfd68-111">The default value of a structure data type consists of the combination of the default values of each of its members.</span></span>

## <a name="declaration-format"></a><span data-ttu-id="dfd68-112">声明格式</span><span class="sxs-lookup"><span data-stu-id="dfd68-112">Declaration Format</span></span>

<span data-ttu-id="dfd68-113">结构声明以[Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)开头，以 `End Structure` 语句结束。</span><span class="sxs-lookup"><span data-stu-id="dfd68-113">A structure declaration starts with the [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) and ends with the `End Structure` statement.</span></span> <span data-ttu-id="dfd68-114">`Structure` 语句提供结构的名称，该名称也是结构正在定义的数据类型的标识符。</span><span class="sxs-lookup"><span data-stu-id="dfd68-114">The `Structure` statement supplies the name of the structure, which is also the identifier of the data type the structure is defining.</span></span> <span data-ttu-id="dfd68-115">代码的其他部分可以使用此标识符来声明变量、参数和函数返回值，使其成为此结构的数据类型。</span><span class="sxs-lookup"><span data-stu-id="dfd68-115">Other parts of the code can use this identifier to declare variables, parameters, and function return values to be of this structure's data type.</span></span>

<span data-ttu-id="dfd68-116">`Structure` 和 `End Structure` 语句之间的声明定义结构的成员。</span><span class="sxs-lookup"><span data-stu-id="dfd68-116">The declarations between the `Structure` and `End Structure` statements define the members of the structure.</span></span>

## <a name="member-access-levels"></a><span data-ttu-id="dfd68-117">成员访问级别</span><span class="sxs-lookup"><span data-stu-id="dfd68-117">Member Access Levels</span></span>

<span data-ttu-id="dfd68-118">必须使用[Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)或指定访问级别的语句（如[Public](../../../visual-basic/language-reference/modifiers/public.md)、 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)或[Private](../../../visual-basic/language-reference/modifiers/private.md)）声明每个成员。</span><span class="sxs-lookup"><span data-stu-id="dfd68-118">You must declare every member using a [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) or a statement that specifies access level, such as [Public](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../visual-basic/language-reference/modifiers/private.md).</span></span> <span data-ttu-id="dfd68-119">如果使用 `Dim` 语句，则访问级别默认为 "公共"。</span><span class="sxs-lookup"><span data-stu-id="dfd68-119">If you use a `Dim` statement, the access level defaults to public.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="dfd68-120">编程提示</span><span class="sxs-lookup"><span data-stu-id="dfd68-120">Programming Tips</span></span>

- <span data-ttu-id="dfd68-121">**内存消耗。**</span><span class="sxs-lookup"><span data-stu-id="dfd68-121">**Memory Consumption.**</span></span> <span data-ttu-id="dfd68-122">与所有复合数据类型一样，不能通过将其成员的标称存储分配相加来安全地计算结构的总内存消耗量。</span><span class="sxs-lookup"><span data-stu-id="dfd68-122">As with all composite data types, you cannot safely calculate the total memory consumption of a structure by adding together the nominal storage allocations of its members.</span></span> <span data-ttu-id="dfd68-123">而且，不能安全地假设内存中的存储顺序与声明顺序相同。</span><span class="sxs-lookup"><span data-stu-id="dfd68-123">Furthermore, you cannot safely assume that the order of storage in memory is the same as your order of declaration.</span></span> <span data-ttu-id="dfd68-124">如果需要控制结构的存储布局，则可以将 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 特性应用于 `Structure` 语句。</span><span class="sxs-lookup"><span data-stu-id="dfd68-124">If you need to control the storage layout of a structure, you can apply the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute to the `Structure` statement.</span></span>

- <span data-ttu-id="dfd68-125">**互操作注意事项。**</span><span class="sxs-lookup"><span data-stu-id="dfd68-125">**Interop Considerations.**</span></span> <span data-ttu-id="dfd68-126">如果与不是为 .NET Framework 编写的组件（如自动化或 COM 对象）交互，请记住，其他环境中的用户定义类型与 Visual Basic 结构类型不兼容。</span><span class="sxs-lookup"><span data-stu-id="dfd68-126">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that user-defined types in other environments are not compatible with Visual Basic structure types.</span></span>

- <span data-ttu-id="dfd68-127">**扩大.**</span><span class="sxs-lookup"><span data-stu-id="dfd68-127">**Widening.**</span></span> <span data-ttu-id="dfd68-128">不会与任何结构数据类型自动转换。</span><span class="sxs-lookup"><span data-stu-id="dfd68-128">There is no automatic conversion to or from any structure data type.</span></span> <span data-ttu-id="dfd68-129">您可以使用[Operator 语句](../../../visual-basic/language-reference/statements/operator-statement.md)在结构上定义转换运算符，并且可以将每个转换运算符声明为 `Widening` 或 `Narrowing`。</span><span class="sxs-lookup"><span data-stu-id="dfd68-129">You can define conversion operators on your structure using the [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md), and you can declare each conversion operator to be `Widening` or `Narrowing`.</span></span>

- <span data-ttu-id="dfd68-130">**键入字符。**</span><span class="sxs-lookup"><span data-stu-id="dfd68-130">**Type Characters.**</span></span> <span data-ttu-id="dfd68-131">结构数据类型没有文本类型字符或标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="dfd68-131">Structure data types have no literal type character or identifier type character.</span></span>

- <span data-ttu-id="dfd68-132">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="dfd68-132">**Framework Type.**</span></span> <span data-ttu-id="dfd68-133">.NET Framework 中没有相应的类型。</span><span class="sxs-lookup"><span data-stu-id="dfd68-133">There is no corresponding type in the .NET Framework.</span></span> <span data-ttu-id="dfd68-134">所有结构都继承自 .NET Framework 类 <xref:System.ValueType?displayProperty=nameWithType>，但没有单个结构与 <xref:System.ValueType?displayProperty=nameWithType>相对应。</span><span class="sxs-lookup"><span data-stu-id="dfd68-134">All structures inherit from the .NET Framework class <xref:System.ValueType?displayProperty=nameWithType>, but no individual structure corresponds to <xref:System.ValueType?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="dfd68-135">示例</span><span class="sxs-lookup"><span data-stu-id="dfd68-135">Example</span></span>

<span data-ttu-id="dfd68-136">以下范例显示了结构声明的轮廓。</span><span class="sxs-lookup"><span data-stu-id="dfd68-136">The following paradigm shows the outline of the declaration of a structure.</span></span>

```vb
[Public | Protected | Friend | Protected Friend | Private] Structure structname
    {Dim | Public | Friend | Private} member1 As datatype1
    ' ...
    {Dim | Public | Friend | Private} memberN As datatypeN
End Structure
```

## <a name="see-also"></a><span data-ttu-id="dfd68-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dfd68-137">See also</span></span>

- <xref:System.ValueType>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [<span data-ttu-id="dfd68-138">数据类型</span><span class="sxs-lookup"><span data-stu-id="dfd68-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="dfd68-139">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="dfd68-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="dfd68-140">转换摘要</span><span class="sxs-lookup"><span data-stu-id="dfd68-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="dfd68-141">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="dfd68-141">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="dfd68-142">Widening</span><span class="sxs-lookup"><span data-stu-id="dfd68-142">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="dfd68-143">Narrowing</span><span class="sxs-lookup"><span data-stu-id="dfd68-143">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="dfd68-144">结构</span><span class="sxs-lookup"><span data-stu-id="dfd68-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="dfd68-145">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="dfd68-145">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
