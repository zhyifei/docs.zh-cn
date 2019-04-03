---
title: 复合数据类型 (Visual Basic)
ms.date: 04/25/2017
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
ms.openlocfilehash: ea719b60a6bcd40494666d4923fad296a8ddae70
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58833810"
---
# <a name="composite-data-types-visual-basic"></a><span data-ttu-id="b2f49-102">复合数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2f49-102">Composite Data Types (Visual Basic)</span></span>
<span data-ttu-id="b2f49-103">除了基本数据类型 Visual Basic 提供，您可以汇集不同类型创建的项*复合数据类型*如结构、 数组和类。</span><span class="sxs-lookup"><span data-stu-id="b2f49-103">In addition to the elementary data types Visual Basic supplies, you can also assemble items of different types to create *composite data types* such as structures, arrays, and classes.</span></span> <span data-ttu-id="b2f49-104">从基本类型和其他复合类型，您可以构建复合数据类型。</span><span class="sxs-lookup"><span data-stu-id="b2f49-104">You can build composite data types from elementary types and from other composite types.</span></span> <span data-ttu-id="b2f49-105">例如，可以使用数组成员定义结构元素的数组或结构。</span><span class="sxs-lookup"><span data-stu-id="b2f49-105">For example, you can define an array of structure elements, or a structure with array members.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="b2f49-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="b2f49-106">Data Types</span></span>  
 <span data-ttu-id="b2f49-107">复合类型是不同于其任意组件的数据类型。</span><span class="sxs-lookup"><span data-stu-id="b2f49-107">A composite type is different from the data type of any of its components.</span></span> <span data-ttu-id="b2f49-108">例如，数组`Integer`元素的不是`Integer`数据类型。</span><span class="sxs-lookup"><span data-stu-id="b2f49-108">For example, an array of `Integer` elements is not of the `Integer` data type.</span></span>  
  
 <span data-ttu-id="b2f49-109">通常情况下根据需要使用元素类型、 括号和逗号表示数组数据类型。</span><span class="sxs-lookup"><span data-stu-id="b2f49-109">An array data type is normally represented using the element type, parentheses, and commas as necessary.</span></span> <span data-ttu-id="b2f49-110">例如的一维数组`String`元素表示为`String()`，和的二维数组`Boolean`元素表示为`Boolean(,)`。</span><span class="sxs-lookup"><span data-stu-id="b2f49-110">For example, a one-dimensional array of `String` elements is represented as `String()`, and a two-dimensional array of `Boolean` elements is represented as `Boolean(,)`.</span></span>  
  
## <a name="structure-types"></a><span data-ttu-id="b2f49-111">结构类型</span><span class="sxs-lookup"><span data-stu-id="b2f49-111">Structure Types</span></span>  
 <span data-ttu-id="b2f49-112">没有一种数据类型包含所有结构。</span><span class="sxs-lookup"><span data-stu-id="b2f49-112">There is no single data type comprising all structures.</span></span> <span data-ttu-id="b2f49-113">相反，每个定义的结构表示唯一的数据类型，即使两个结构的相同顺序定义相同的元素。</span><span class="sxs-lookup"><span data-stu-id="b2f49-113">Instead, each definition of a structure represents a unique data type, even if two structures define identical elements in the same order.</span></span> <span data-ttu-id="b2f49-114">但是，如果创建具有相同结构的两个或多个实例时，Visual Basic 将认为它们是相同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="b2f49-114">However, if you create two or more instances of the same structure, Visual Basic considers them to be of the same data type.</span></span>  
  
## <a name="tuples"></a><span data-ttu-id="b2f49-115">元组</span><span class="sxs-lookup"><span data-stu-id="b2f49-115">Tuples</span></span>

<span data-ttu-id="b2f49-116">元组是包含两个或多个字段的类型预定义的轻型结构。</span><span class="sxs-lookup"><span data-stu-id="b2f49-116">A tuple is a lightweight structure that contains two or more fields whose types are predefined.</span></span> <span data-ttu-id="b2f49-117">从 Visual Basic 2017 开始支持元组。</span><span class="sxs-lookup"><span data-stu-id="b2f49-117">Tuples are supported starting with Visual Basic 2017.</span></span> <span data-ttu-id="b2f49-118">元组通常用于从单个方法调用返回多个值，而无需按引用传递参数或打包更粗线的类或结构中返回的字段。</span><span class="sxs-lookup"><span data-stu-id="b2f49-118">Tuples are most commonly used to return multiple values from a single method call without having to pass arguments by reference or packaging the returned fields in a more heavy-weight class or structure.</span></span> <span data-ttu-id="b2f49-119">请参阅[元组](tuples.md)元组的详细信息的主题。</span><span class="sxs-lookup"><span data-stu-id="b2f49-119">See the [Tuples](tuples.md) topic for more information on tuples.</span></span>

## <a name="array-types"></a><span data-ttu-id="b2f49-120">数组类型</span><span class="sxs-lookup"><span data-stu-id="b2f49-120">Array Types</span></span>  
 <span data-ttu-id="b2f49-121">没有一种数据类型包含所有数组。</span><span class="sxs-lookup"><span data-stu-id="b2f49-121">There is no single data type comprising all arrays.</span></span> <span data-ttu-id="b2f49-122">通过以下方法确定数组的特定实例的数据类型：</span><span class="sxs-lookup"><span data-stu-id="b2f49-122">The data type of a particular instance of an array is determined by the following:</span></span>  
  
-   <span data-ttu-id="b2f49-123">这一事实的一个数组</span><span class="sxs-lookup"><span data-stu-id="b2f49-123">The fact of being an array</span></span>  
  
-   <span data-ttu-id="b2f49-124">数组的秩 （维数）</span><span class="sxs-lookup"><span data-stu-id="b2f49-124">The rank (number of dimensions) of the array</span></span>  
  
-   <span data-ttu-id="b2f49-125">数组的元素类型</span><span class="sxs-lookup"><span data-stu-id="b2f49-125">The element type of the array</span></span>  
  
 <span data-ttu-id="b2f49-126">具体而言，给定维度的长度不是实例的数据类型的一部分。</span><span class="sxs-lookup"><span data-stu-id="b2f49-126">In particular, the length of a given dimension is not part of the instance's data type.</span></span> <span data-ttu-id="b2f49-127">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="b2f49-127">The following example illustrates this.</span></span>  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 <span data-ttu-id="b2f49-128">在前面的示例中，数组变量`arrayA`并`arrayB`被视为是相同的数据类型 — `Byte()` — 即使它们初始化为不同的长度。</span><span class="sxs-lookup"><span data-stu-id="b2f49-128">In the preceding example, array variables `arrayA` and `arrayB` are considered to be of the same data type — `Byte()` — even though they are initialized to different lengths.</span></span> <span data-ttu-id="b2f49-129">变量`arrayB`和`arrayC`不属于同一类型，因为它们的元素类型不同。</span><span class="sxs-lookup"><span data-stu-id="b2f49-129">Variables `arrayB` and `arrayC` are not of the same type because their element types are different.</span></span> <span data-ttu-id="b2f49-130">变量`arrayC`和`arrayD`不属于同一类型，因为它们的秩不同。</span><span class="sxs-lookup"><span data-stu-id="b2f49-130">Variables `arrayC` and `arrayD` are not of the same type because their ranks are different.</span></span> <span data-ttu-id="b2f49-131">变量`arrayD`并`arrayE`具有相同的类型 — `Short(,)` — 因为它们的秩和元素类型是相同的即使`arrayD`尚未初始化。</span><span class="sxs-lookup"><span data-stu-id="b2f49-131">Variables `arrayD` and `arrayE` have the same type — `Short(,)` — because their ranks and element types are the same, even though `arrayD` is not yet initialized.</span></span>  
  
 <span data-ttu-id="b2f49-132">在数组上的详细信息，请参阅[数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b2f49-132">For more information on arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="class-types"></a><span data-ttu-id="b2f49-133">类类型</span><span class="sxs-lookup"><span data-stu-id="b2f49-133">Class Types</span></span>  
 <span data-ttu-id="b2f49-134">没有一种数据类型组成的所有类。</span><span class="sxs-lookup"><span data-stu-id="b2f49-134">There is no single data type comprising all classes.</span></span> <span data-ttu-id="b2f49-135">尽管一个类可以继承自另一个类，每个是单独的数据类型。</span><span class="sxs-lookup"><span data-stu-id="b2f49-135">Although one class can inherit from another class, each is a separate data type.</span></span> <span data-ttu-id="b2f49-136">同一个类的多个实例是相同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="b2f49-136">Multiple instances of the same class are of the same data type.</span></span> <span data-ttu-id="b2f49-137">如果将一个类实例变量分配到另一个，不仅它们具有相同的数据类型，它们指向内存中的同一个类实例。</span><span class="sxs-lookup"><span data-stu-id="b2f49-137">If you assign one class instance variable to another, not only do they have the same data type, they point to the same class instance in memory.</span></span>  
  
 <span data-ttu-id="b2f49-138">类的详细信息，请参阅[对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b2f49-138">For more information on classes, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2f49-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2f49-139">See also</span></span>

- [<span data-ttu-id="b2f49-140">数据类型</span><span class="sxs-lookup"><span data-stu-id="b2f49-140">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="b2f49-141">基本数据类型</span><span class="sxs-lookup"><span data-stu-id="b2f49-141">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="b2f49-142">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="b2f49-142">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="b2f49-143">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="b2f49-143">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="b2f49-144">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="b2f49-144">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="b2f49-145">结构</span><span class="sxs-lookup"><span data-stu-id="b2f49-145">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="b2f49-146">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="b2f49-146">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="b2f49-147">如何：在一个变量中保留多个值</span><span class="sxs-lookup"><span data-stu-id="b2f49-147">How to: Hold More Than One Value in a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
