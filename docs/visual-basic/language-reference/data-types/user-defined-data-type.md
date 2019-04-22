---
title: 用户定义数据类型 (Visual Basic)
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
ms.openlocfilehash: 5fe12d18c7f403c1a50ed548a260ba39e83280eb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814185"
---
# <a name="user-defined-data-type"></a><span data-ttu-id="e4aa4-102">用户定义的数据类型</span><span class="sxs-lookup"><span data-stu-id="e4aa4-102">User-Defined Data Type</span></span>
<span data-ttu-id="e4aa4-103">在您定义的格式保存数据。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-103">Holds data in a format you define.</span></span> <span data-ttu-id="e4aa4-104">`Structure`语句定义的格式。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-104">The `Structure` statement defines the format.</span></span>  
  
 <span data-ttu-id="e4aa4-105">早期版本的 Visual Basic 支持用户定义类型 (UDT)。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-105">Previous versions of Visual Basic support the user-defined type (UDT).</span></span> <span data-ttu-id="e4aa4-106">当前版本扩展了到 UDT*结构*。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-106">The current version expands the UDT to a *structure*.</span></span> <span data-ttu-id="e4aa4-107">结构是一个或多个串联*成员*的各种数据类型。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-107">A structure is a concatenation of one or more *members* of various data types.</span></span> <span data-ttu-id="e4aa4-108">Visual Basic 将结构作为单个单元，尽管您还可以单独访问其成员。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-108">Visual Basic treats a structure as a single unit, although you can also access its members individually.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4aa4-109">备注</span><span class="sxs-lookup"><span data-stu-id="e4aa4-109">Remarks</span></span>  
 <span data-ttu-id="e4aa4-110">定义和使用结构数据类型，或无基本数据类型满足你的需求时您需要将各种数据类型组合到单个单元。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-110">Define and use a structure data type when you need to combine various data types into a single unit, or when none of the elementary data types serve your needs.</span></span>  
  
 <span data-ttu-id="e4aa4-111">结构的数据类型的默认值由其每个成员的默认值的组合组成。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-111">The default value of a structure data type consists of the combination of the default values of each of its members.</span></span>  
  
## <a name="declaration-format"></a><span data-ttu-id="e4aa4-112">声明格式</span><span class="sxs-lookup"><span data-stu-id="e4aa4-112">Declaration Format</span></span>  
 <span data-ttu-id="e4aa4-113">在结构声明开头[Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)结尾`End Structure`语句。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-113">A structure declaration starts with the [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) and ends with the `End Structure` statement.</span></span> <span data-ttu-id="e4aa4-114">`Structure`语句提供的结构，这也是该结构定义的数据类型的标识符的名称。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-114">The `Structure` statement supplies the name of the structure, which is also the identifier of the data type the structure is defining.</span></span> <span data-ttu-id="e4aa4-115">代码的其他部分可以使用此标识符来声明变量、 参数和函数返回值为此结构的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-115">Other parts of the code can use this identifier to declare variables, parameters, and function return values to be of this structure's data type.</span></span>  
  
 <span data-ttu-id="e4aa4-116">之间的声明`Structure`和`End Structure`语句定义的结构的成员。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-116">The declarations between the `Structure` and `End Structure` statements define the members of the structure.</span></span>  
  
## <a name="member-access-levels"></a><span data-ttu-id="e4aa4-117">成员访问级别</span><span class="sxs-lookup"><span data-stu-id="e4aa4-117">Member Access Levels</span></span>  
 <span data-ttu-id="e4aa4-118">必须声明使用每个成员[Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)或指定访问级别，例如语句[公共](../../../visual-basic/language-reference/modifiers/public.md)，[友元](../../../visual-basic/language-reference/modifiers/friend.md)，或[专用](../../../visual-basic/language-reference/modifiers/private.md).</span><span class="sxs-lookup"><span data-stu-id="e4aa4-118">You must declare every member using a [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) or a statement that specifies access level, such as [Public](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../visual-basic/language-reference/modifiers/private.md).</span></span> <span data-ttu-id="e4aa4-119">如果使用`Dim`语句中，为公共访问级别默认设置。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-119">If you use a `Dim` statement, the access level defaults to public.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="e4aa4-120">编程提示</span><span class="sxs-lookup"><span data-stu-id="e4aa4-120">Programming Tips</span></span>  
  
-   <span data-ttu-id="e4aa4-121">**内存占用情况。**</span><span class="sxs-lookup"><span data-stu-id="e4aa4-121">**Memory Consumption.**</span></span> <span data-ttu-id="e4aa4-122">与所有复合数据类型，不能安全地通过同时添加其成员的名义存储分配计算结构的内存总消耗。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-122">As with all composite data types, you cannot safely calculate the total memory consumption of a structure by adding together the nominal storage allocations of its members.</span></span> <span data-ttu-id="e4aa4-123">此外，不能安全地假定已在内存中存储的顺序声明的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-123">Furthermore, you cannot safely assume that the order of storage in memory is the same as your order of declaration.</span></span> <span data-ttu-id="e4aa4-124">如果需要控制结构的存储布局，你可以申请<xref:System.Runtime.InteropServices.StructLayoutAttribute>属性为`Structure`语句。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-124">If you need to control the storage layout of a structure, you can apply the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute to the `Structure` statement.</span></span>  
  
-   <span data-ttu-id="e4aa4-125">**互操作注意事项。**</span><span class="sxs-lookup"><span data-stu-id="e4aa4-125">**Interop Considerations.**</span></span> <span data-ttu-id="e4aa4-126">如果你与不是为.NET Framework 编写的组件交互，如自动化或 COM 对象，请记住，在其他环境中的用户定义类型都不兼容使用 Visual Basic 的结构类型。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-126">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that user-defined types in other environments are not compatible with Visual Basic structure types.</span></span>  
  
-   <span data-ttu-id="e4aa4-127">**扩大转换。**</span><span class="sxs-lookup"><span data-stu-id="e4aa4-127">**Widening.**</span></span> <span data-ttu-id="e4aa4-128">没有自动转换到或从任何结构的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-128">There is no automatic conversion to or from any structure data type.</span></span> <span data-ttu-id="e4aa4-129">可以使用在结构上定义转换运算符[Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)，并可以声明为每个转换运算符`Widening`或`Narrowing`。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-129">You can define conversion operators on your structure using the [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md), and you can declare each conversion operator to be `Widening` or `Narrowing`.</span></span>  
  
-   <span data-ttu-id="e4aa4-130">**类型字符。**</span><span class="sxs-lookup"><span data-stu-id="e4aa4-130">**Type Characters.**</span></span> <span data-ttu-id="e4aa4-131">结构的数据类型不具有文本类型字符或标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-131">Structure data types have no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="e4aa4-132">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="e4aa4-132">**Framework Type.**</span></span> <span data-ttu-id="e4aa4-133">.NET Framework 中没有相应类型。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-133">There is no corresponding type in the .NET Framework.</span></span> <span data-ttu-id="e4aa4-134">从.NET Framework 类继承的所有结构<xref:System.ValueType?displayProperty=nameWithType>，但没有单个结构对应于<xref:System.ValueType?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-134">All structures inherit from the .NET Framework class <xref:System.ValueType?displayProperty=nameWithType>, but no individual structure corresponds to <xref:System.ValueType?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4aa4-135">示例</span><span class="sxs-lookup"><span data-stu-id="e4aa4-135">Example</span></span>  
 <span data-ttu-id="e4aa4-136">下面的示例演示一种结构的声明的大纲。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-136">The following paradigm shows the outline of the declaration of a structure.</span></span>  
  
```  
[Public | Protected | Friend | Protected Friend | Private] Structure structname  
    {Dim | Public | Friend | Private} member1 As datatype1  
    ' ...  
    {Dim | Public | Friend | Private} memberN As datatypeN  
End Structure  
```  
  
## <a name="see-also"></a><span data-ttu-id="e4aa4-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4aa4-137">See also</span></span>

- <xref:System.ValueType>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [<span data-ttu-id="e4aa4-138">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4aa4-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="e4aa4-139">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="e4aa4-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="e4aa4-140">转换摘要</span><span class="sxs-lookup"><span data-stu-id="e4aa4-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="e4aa4-141">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="e4aa4-141">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="e4aa4-142">Widening</span><span class="sxs-lookup"><span data-stu-id="e4aa4-142">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="e4aa4-143">Narrowing</span><span class="sxs-lookup"><span data-stu-id="e4aa4-143">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="e4aa4-144">结构</span><span class="sxs-lookup"><span data-stu-id="e4aa4-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="e4aa4-145">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="e4aa4-145">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
