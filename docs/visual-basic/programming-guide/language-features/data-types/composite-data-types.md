---
title: "复合数据类型 (Visual Basic)"
ms.custom: 
ms.date: 04/25/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e9adb407757dbee2f7ac5a94118623a62212faec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="composite-data-types-visual-basic"></a><span data-ttu-id="e4fcb-102">复合数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4fcb-102">Composite Data Types (Visual Basic)</span></span>
<span data-ttu-id="e4fcb-103">除了基本数据类型[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]提供，你可以还将组合不同的类型创建的项目*复合数据类型*如结构、 数组和类。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-103">In addition to the elementary data types [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] supplies, you can also assemble items of different types to create *composite data types* such as structures, arrays, and classes.</span></span> <span data-ttu-id="e4fcb-104">基本类型和其他复合类型，你可以构建复合数据类型。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-104">You can build composite data types from elementary types and from other composite types.</span></span> <span data-ttu-id="e4fcb-105">例如，可以与数组成员中定义的结构元素的数组或结构。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-105">For example, you can define an array of structure elements, or a structure with array members.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="e4fcb-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4fcb-106">Data Types</span></span>  
 <span data-ttu-id="e4fcb-107">复合类型是不同的任一种情况及其组件的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-107">A composite type is different from the data type of any of its components.</span></span> <span data-ttu-id="e4fcb-108">例如，数组的`Integer`元素不属于`Integer`数据类型。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-108">For example, an array of `Integer` elements is not of the `Integer` data type.</span></span>  
  
 <span data-ttu-id="e4fcb-109">数组数据类型通常表示根据需要使用元素类型、 圆括号和逗号。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-109">An array data type is normally represented using the element type, parentheses, and commas as necessary.</span></span> <span data-ttu-id="e4fcb-110">例如，一维数组的`String`元素表示为`String()`，和一个二维数组的`Boolean`元素表示为`Boolean(,)`。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-110">For example, a one-dimensional array of `String` elements is represented as `String()`, and a two-dimensional array of `Boolean` elements is represented as `Boolean(,)`.</span></span>  
  
## <a name="structure-types"></a><span data-ttu-id="e4fcb-111">结构类型</span><span class="sxs-lookup"><span data-stu-id="e4fcb-111">Structure Types</span></span>  
 <span data-ttu-id="e4fcb-112">不存在包含所有结构的单个数据类型。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-112">There is no single data type comprising all structures.</span></span> <span data-ttu-id="e4fcb-113">相反，每个定义的结构表示唯一的数据类型，即使两个结构定义相同的元素顺序相同。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-113">Instead, each definition of a structure represents a unique data type, even if two structures define identical elements in the same order.</span></span> <span data-ttu-id="e4fcb-114">但是，如果创建两个或多个相同的结构，实例[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]将认为它们是相同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-114">However, if you create two or more instances of the same structure, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] considers them to be of the same data type.</span></span>  
  
## <a name="tuples"></a><span data-ttu-id="e4fcb-115">元组</span><span class="sxs-lookup"><span data-stu-id="e4fcb-115">Tuples</span></span>

<span data-ttu-id="e4fcb-116">元组是包含其类型预定义的两个或多个字段的轻量结构。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-116">A tuple is a lightweight structure that contains two or more fields whose types are predefined.</span></span> <span data-ttu-id="e4fcb-117">从 Visual Basic 自 2017 年开始支持元组。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-117">Tuples are supported starting with Visual Basic 2017.</span></span> <span data-ttu-id="e4fcb-118">元组通常用于从单个方法调用返回多个值，而无需通过引用传递自变量或打包多重型的类或结构中返回的字段。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-118">Tuples are most commonly used to return multiple values from a single method call without having to pass arguments by reference or packaging the returned fields in a more heavy-weight class or structure.</span></span> <span data-ttu-id="e4fcb-119">请参阅[元组](tuples.md)元组的详细信息的主题。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-119">See the [Tuples](tuples.md) topic for more information on tuples.</span></span>

## <a name="array-types"></a><span data-ttu-id="e4fcb-120">数组类型</span><span class="sxs-lookup"><span data-stu-id="e4fcb-120">Array Types</span></span>  
 <span data-ttu-id="e4fcb-121">不存在包含所有数组的单个数据类型。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-121">There is no single data type comprising all arrays.</span></span> <span data-ttu-id="e4fcb-122">由以下确定数组的特定实例的数据类型：</span><span class="sxs-lookup"><span data-stu-id="e4fcb-122">The data type of a particular instance of an array is determined by the following:</span></span>  
  
-   <span data-ttu-id="e4fcb-123">确实为数组</span><span class="sxs-lookup"><span data-stu-id="e4fcb-123">The fact of being an array</span></span>  
  
-   <span data-ttu-id="e4fcb-124">数组的秩 （维数）</span><span class="sxs-lookup"><span data-stu-id="e4fcb-124">The rank (number of dimensions) of the array</span></span>  
  
-   <span data-ttu-id="e4fcb-125">数组的元素类型</span><span class="sxs-lookup"><span data-stu-id="e4fcb-125">The element type of the array</span></span>  
  
 <span data-ttu-id="e4fcb-126">具体而言，给定维度的长度不是实例的数据类型的一部分。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-126">In particular, the length of a given dimension is not part of the instance's data type.</span></span> <span data-ttu-id="e4fcb-127">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-127">The following example illustrates this.</span></span>  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 <span data-ttu-id="e4fcb-128">在前面的示例中，数组变量`arrayA`和`arrayB`被视为相同的数据类型- `Byte()` — 即使它们将初始化为不同长度也是如此。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-128">In the preceding example, array variables `arrayA` and `arrayB` are considered to be of the same data type — `Byte()` — even though they are initialized to different lengths.</span></span> <span data-ttu-id="e4fcb-129">变量`arrayB`和`arrayC`不属于同一类型，因为它们的元素类型不同。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-129">Variables `arrayB` and `arrayC` are not of the same type because their element types are different.</span></span> <span data-ttu-id="e4fcb-130">变量`arrayC`和`arrayD`不属于同一类型，因为它们的秩不同。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-130">Variables `arrayC` and `arrayD` are not of the same type because their ranks are different.</span></span> <span data-ttu-id="e4fcb-131">变量`arrayD`和`arrayE`具有相同的类型- `Short(,)` -因为它们的秩和元素类型是相同的即使`arrayD`尚未初始化。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-131">Variables `arrayD` and `arrayE` have the same type — `Short(,)` — because their ranks and element types are the same, even though `arrayD` is not yet initialized.</span></span>  
  
 <span data-ttu-id="e4fcb-132">在阵列上的详细信息，请参阅[数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-132">For more information on arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="class-types"></a><span data-ttu-id="e4fcb-133">类类型</span><span class="sxs-lookup"><span data-stu-id="e4fcb-133">Class Types</span></span>  
 <span data-ttu-id="e4fcb-134">不存在包含所有类的单个数据类型。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-134">There is no single data type comprising all classes.</span></span> <span data-ttu-id="e4fcb-135">尽管一个类可以从另一个类继承的每个是单独的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-135">Although one class can inherit from another class, each is a separate data type.</span></span> <span data-ttu-id="e4fcb-136">同一个类的多个实例均为相同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-136">Multiple instances of the same class are of the same data type.</span></span> <span data-ttu-id="e4fcb-137">如果将一个类实例变量分配到另一个，不仅它们具有相同的数据类型，它们指向内存中的同一个类实例。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-137">If you assign one class instance variable to another, not only do they have the same data type, they point to the same class instance in memory.</span></span>  
  
 <span data-ttu-id="e4fcb-138">类的详细信息，请参阅[对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)。</span><span class="sxs-lookup"><span data-stu-id="e4fcb-138">For more information on classes, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4fcb-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4fcb-139">See Also</span></span>  
 [<span data-ttu-id="e4fcb-140">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4fcb-140">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="e4fcb-141">基本数据类型</span><span class="sxs-lookup"><span data-stu-id="e4fcb-141">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="e4fcb-142">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="e4fcb-142">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="e4fcb-143">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="e4fcb-143">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="e4fcb-144">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="e4fcb-144">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="e4fcb-145">结构</span><span class="sxs-lookup"><span data-stu-id="e4fcb-145">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="e4fcb-146">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="e4fcb-146">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="e4fcb-147">如何：在一个变量中保存多个值</span><span class="sxs-lookup"><span data-stu-id="e4fcb-147">How to: Hold More Than One Value in a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
