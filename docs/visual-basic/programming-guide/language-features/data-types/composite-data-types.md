---
title: "复合数据类型 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types
- composite data types
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures, composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5f0c6215ce45d724a7b5c8c4f8e34ea27bce8fe4
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="composite-data-types-visual-basic"></a><span data-ttu-id="a3464-102">复合数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3464-102">Composite Data Types (Visual Basic)</span></span>
<span data-ttu-id="a3464-103">除了基本数据类型[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]供应品，你可以还将组合来创建不同类型的项*复合数据类型*如结构、 数组和类。</span><span class="sxs-lookup"><span data-stu-id="a3464-103">In addition to the elementary data types [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] supplies, you can also assemble items of different types to create *composite data types* such as structures, arrays, and classes.</span></span> <span data-ttu-id="a3464-104">从基本类型和其他复合类型，您可以构建复合数据类型。</span><span class="sxs-lookup"><span data-stu-id="a3464-104">You can build composite data types from elementary types and from other composite types.</span></span> <span data-ttu-id="a3464-105">例如，可以具有数组成员中定义的结构元素的数组或结构。</span><span class="sxs-lookup"><span data-stu-id="a3464-105">For example, you can define an array of structure elements, or a structure with array members.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="a3464-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="a3464-106">Data Types</span></span>  
 <span data-ttu-id="a3464-107">复合类型是不同于其任意组件的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a3464-107">A composite type is different from the data type of any of its components.</span></span> <span data-ttu-id="a3464-108">例如，数组的`Integer`元素不属于`Integer`数据类型。</span><span class="sxs-lookup"><span data-stu-id="a3464-108">For example, an array of `Integer` elements is not of the `Integer` data type.</span></span>  
  
 <span data-ttu-id="a3464-109">数组数据类型通常是根据需要使用元素类型、 括号和逗号表示的。</span><span class="sxs-lookup"><span data-stu-id="a3464-109">An array data type is normally represented using the element type, parentheses, and commas as necessary.</span></span> <span data-ttu-id="a3464-110">例如的一维数组`String`元素表示为`String()`，和一个二维数组`Boolean`元素表示为`Boolean(,)`。</span><span class="sxs-lookup"><span data-stu-id="a3464-110">For example, a one-dimensional array of `String` elements is represented as `String()`, and a two-dimensional array of `Boolean` elements is represented as `Boolean(,)`.</span></span>  
  
## <a name="structure-types"></a><span data-ttu-id="a3464-111">结构化类型</span><span class="sxs-lookup"><span data-stu-id="a3464-111">Structure Types</span></span>  
 <span data-ttu-id="a3464-112">没有一种数据类型包含所有结构。</span><span class="sxs-lookup"><span data-stu-id="a3464-112">There is no single data type comprising all structures.</span></span> <span data-ttu-id="a3464-113">相反，每个定义的结构表示唯一的数据类型，即使两个结构定义相同的元素以相同的顺序。</span><span class="sxs-lookup"><span data-stu-id="a3464-113">Instead, each definition of a structure represents a unique data type, even if two structures define identical elements in the same order.</span></span> <span data-ttu-id="a3464-114">但是，如果创建两个或多个实例相同的结构，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]认为它们是相同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a3464-114">However, if you create two or more instances of the same structure, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] considers them to be of the same data type.</span></span>  
  
## <a name="array-types"></a><span data-ttu-id="a3464-115">数组类型</span><span class="sxs-lookup"><span data-stu-id="a3464-115">Array Types</span></span>  
 <span data-ttu-id="a3464-116">不存在包含所有数组的单个数据类型。</span><span class="sxs-lookup"><span data-stu-id="a3464-116">There is no single data type comprising all arrays.</span></span> <span data-ttu-id="a3464-117">数组的特定实例的数据类型是由以下方面确定︰</span><span class="sxs-lookup"><span data-stu-id="a3464-117">The data type of a particular instance of an array is determined by the following:</span></span>  
  
-   <span data-ttu-id="a3464-118">确实为数组</span><span class="sxs-lookup"><span data-stu-id="a3464-118">The fact of being an array</span></span>  
  
-   <span data-ttu-id="a3464-119">数组的秩 （维数）</span><span class="sxs-lookup"><span data-stu-id="a3464-119">The rank (number of dimensions) of the array</span></span>  
  
-   <span data-ttu-id="a3464-120">数组的元素类型</span><span class="sxs-lookup"><span data-stu-id="a3464-120">The element type of the array</span></span>  
  
 <span data-ttu-id="a3464-121">具体而言，给定维度的长度不是该实例的数据类型的一部分。</span><span class="sxs-lookup"><span data-stu-id="a3464-121">In particular, the length of a given dimension is not part of the instance's data type.</span></span> <span data-ttu-id="a3464-122">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="a3464-122">The following example illustrates this.</span></span>  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 <span data-ttu-id="a3464-123">在前面的示例中，数组变量`arrayA`和`arrayB`被认为是相同的数据类型 — `Byte()` — 即使它们被初始化为不同的长度也是如此。</span><span class="sxs-lookup"><span data-stu-id="a3464-123">In the preceding example, array variables `arrayA` and `arrayB` are considered to be of the same data type — `Byte()` — even though they are initialized to different lengths.</span></span> <span data-ttu-id="a3464-124">变量`arrayB`和`arrayC`不相同类型的因为它们的元素类型不同。</span><span class="sxs-lookup"><span data-stu-id="a3464-124">Variables `arrayB` and `arrayC` are not of the same type because their element types are different.</span></span> <span data-ttu-id="a3464-125">变量`arrayC`和`arrayD`不相同类型的因为它们的秩不同。</span><span class="sxs-lookup"><span data-stu-id="a3464-125">Variables `arrayC` and `arrayD` are not of the same type because their ranks are different.</span></span> <span data-ttu-id="a3464-126">变量`arrayD`和`arrayE`具有相同的类型 — `Short(,)` — 因为它们的秩和元素类型是相同的即使`arrayD`尚未初始化。</span><span class="sxs-lookup"><span data-stu-id="a3464-126">Variables `arrayD` and `arrayE` have the same type — `Short(,)` — because their ranks and element types are the same, even though `arrayD` is not yet initialized.</span></span>  
  
 <span data-ttu-id="a3464-127">在阵列上的详细信息，请参阅[数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a3464-127">For more information on arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="class-types"></a><span data-ttu-id="a3464-128">类类型</span><span class="sxs-lookup"><span data-stu-id="a3464-128">Class Types</span></span>  
 <span data-ttu-id="a3464-129">没有一种数据类型组成的所有类。</span><span class="sxs-lookup"><span data-stu-id="a3464-129">There is no single data type comprising all classes.</span></span> <span data-ttu-id="a3464-130">尽管一个类可以从另一个类继承的每个是单独的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a3464-130">Although one class can inherit from another class, each is a separate data type.</span></span> <span data-ttu-id="a3464-131">同一个类的多个实例是相同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a3464-131">Multiple instances of the same class are of the same data type.</span></span> <span data-ttu-id="a3464-132">如果将一个类实例变量分配到另一个，不仅它们具有相同的数据类型，它们指向内存中的同一个类实例。</span><span class="sxs-lookup"><span data-stu-id="a3464-132">If you assign one class instance variable to another, not only do they have the same data type, they point to the same class instance in memory.</span></span>  
  
 <span data-ttu-id="a3464-133">类的详细信息，请参阅[对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a3464-133">For more information on classes, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3464-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3464-134">See Also</span></span>  
 <span data-ttu-id="a3464-135">[数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="a3464-135">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="a3464-136"> [基本数据类型](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="a3464-136"> [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="a3464-137"> [Visual Basic 中的泛型类型](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="a3464-137"> [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
<span data-ttu-id="a3464-138"> [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="a3464-138"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="a3464-139"> [在 Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="a3464-139"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="a3464-140"> [结构](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span><span class="sxs-lookup"><span data-stu-id="a3464-140"> [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span></span>  
<span data-ttu-id="a3464-141"> [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="a3464-141"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="a3464-142"> [如何：在一个变量中保存多个值](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)</span><span class="sxs-lookup"><span data-stu-id="a3464-142"> [How to: Hold More Than One Value in a Variable](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)</span></span>
