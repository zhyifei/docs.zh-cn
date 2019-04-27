---
title: Generic Procedures in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- generic methods [Visual Basic], type inference
- generics [Visual Basic], type inference
- procedures [Visual Basic], generic
- generic procedures
- type inference, generics
- generic methods [Visual Basic]
- type inference
- generics [Visual Basic], procedures
- generic procedures [Visual Basic], type inference
ms.assetid: 95577b28-137f-4d5c-a149-919c828600e5
ms.openlocfilehash: 4aed16ce9eb59da54156a0cd5f1594819788521b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906589"
---
# <a name="generic-procedures-in-visual-basic"></a><span data-ttu-id="f5736-102">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f5736-102">Generic Procedures in Visual Basic</span></span>
<span data-ttu-id="f5736-103">一个*泛型过程*，也称为*泛型方法*，是使用至少一个类型参数定义的过程。</span><span class="sxs-lookup"><span data-stu-id="f5736-103">A *generic procedure*, also called a *generic method*, is a procedure defined with at least one type parameter.</span></span> <span data-ttu-id="f5736-104">这使得调用代码来定制其要求的数据类型的每次调用该过程。</span><span class="sxs-lookup"><span data-stu-id="f5736-104">This allows the calling code to tailor the data types to its requirements each time it calls the procedure.</span></span>  
  
 <span data-ttu-id="f5736-105">过程是不是简单地由于正在定义在泛型类或泛型结构。</span><span class="sxs-lookup"><span data-stu-id="f5736-105">A procedure is not generic simply by virtue of being defined inside a generic class or a generic structure.</span></span> <span data-ttu-id="f5736-106">若要为泛型，该过程必须采用至少一个类型参数，除了可能需要的所有普通参数。</span><span class="sxs-lookup"><span data-stu-id="f5736-106">To be generic, the procedure must take at least one type parameter, in addition to any normal parameters it might take.</span></span> <span data-ttu-id="f5736-107">泛型类或结构可以包含非泛型过程和非泛型类、 结构或模块可以包含泛型过程。</span><span class="sxs-lookup"><span data-stu-id="f5736-107">A generic class or structure can contain nongeneric procedures, and a nongeneric class, structure, or module can contain generic procedures.</span></span>  
  
 <span data-ttu-id="f5736-108">泛型过程可以在其正常参数列表中，其返回类型，如果它有一个，并在其过程代码中使用其类型参数。</span><span class="sxs-lookup"><span data-stu-id="f5736-108">A generic procedure can use its type parameters in its normal parameter list, in its return type if it has one, and in its procedure code.</span></span>  
  
## <a name="type-inference"></a><span data-ttu-id="f5736-109">类型推断</span><span class="sxs-lookup"><span data-stu-id="f5736-109">Type Inference</span></span>  
 <span data-ttu-id="f5736-110">未提供任何类型参数在所有情况下，可以调用泛型过程。</span><span class="sxs-lookup"><span data-stu-id="f5736-110">You can call a generic procedure without supplying any type arguments at all.</span></span> <span data-ttu-id="f5736-111">如果您以这种方式，编译器将尝试确定要传递给过程的类型参数的相应的数据类型。</span><span class="sxs-lookup"><span data-stu-id="f5736-111">If you call it this way, the compiler attempts to determine the appropriate data types to pass to the procedure's type arguments.</span></span> <span data-ttu-id="f5736-112">这称为*类型推理*。</span><span class="sxs-lookup"><span data-stu-id="f5736-112">This is called *type inference*.</span></span> <span data-ttu-id="f5736-113">下面的代码演示如何调用中，编译器推断它应将类型传递`String`对该类型参数`t`。</span><span class="sxs-lookup"><span data-stu-id="f5736-113">The following code shows a call in which the compiler infers that it should pass type `String` to the type parameter `t`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#15)]  
  
 <span data-ttu-id="f5736-114">如果编译器无法推断调用上下文的类型参数，则将报告错误。</span><span class="sxs-lookup"><span data-stu-id="f5736-114">If the compiler cannot infer the type arguments from the context of your call, it reports an error.</span></span> <span data-ttu-id="f5736-115">此类错误的一个可能原因是数组秩不匹配。</span><span class="sxs-lookup"><span data-stu-id="f5736-115">One possible cause of such an error is an array rank mismatch.</span></span> <span data-ttu-id="f5736-116">例如，假设您定义普通参数作为数组的类型参数。</span><span class="sxs-lookup"><span data-stu-id="f5736-116">For example, suppose you define a normal parameter as an array of a type parameter.</span></span> <span data-ttu-id="f5736-117">如果调用的泛型过程提供不同的秩 （维数），数组不匹配会导致类型推理失败。</span><span class="sxs-lookup"><span data-stu-id="f5736-117">If you call the generic procedure supplying an array of a different rank (number of dimensions), the mismatch causes type inference to fail.</span></span> <span data-ttu-id="f5736-118">下面的代码演示如何调用中的二维数组传递给过程所需的一维数组。</span><span class="sxs-lookup"><span data-stu-id="f5736-118">The following code shows a call in which a two-dimensional array is passed to a procedure that expects a one-dimensional array.</span></span>  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 <span data-ttu-id="f5736-119">可以仅通过省略的所有类型参数调用类型推理。</span><span class="sxs-lookup"><span data-stu-id="f5736-119">You can invoke type inference only by omitting all the type arguments.</span></span> <span data-ttu-id="f5736-120">如果您提供一个类型实参，则必须提供所有这些。</span><span class="sxs-lookup"><span data-stu-id="f5736-120">If you supply one type argument, you must supply them all.</span></span>  
  
 <span data-ttu-id="f5736-121">仅对泛型过程支持的类型推理。</span><span class="sxs-lookup"><span data-stu-id="f5736-121">Type inference is supported only for generic procedures.</span></span> <span data-ttu-id="f5736-122">不能调用上泛型类、 结构、 接口或委托的类型推理。</span><span class="sxs-lookup"><span data-stu-id="f5736-122">You cannot invoke type inference on generic classes, structures, interfaces, or delegates.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5736-123">示例</span><span class="sxs-lookup"><span data-stu-id="f5736-123">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="f5736-124">描述</span><span class="sxs-lookup"><span data-stu-id="f5736-124">Description</span></span>  
 <span data-ttu-id="f5736-125">下面的示例定义了一个泛型`Function`过程，用于在数组中查找特定元素。</span><span class="sxs-lookup"><span data-stu-id="f5736-125">The following example defines a generic `Function` procedure to find a particular element in an array.</span></span> <span data-ttu-id="f5736-126">它定义一个类型参数，并使用它来构建在参数列表中的两个参数。</span><span class="sxs-lookup"><span data-stu-id="f5736-126">It defines one type parameter and uses it to construct the two parameters in the parameter list.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f5736-127">代码</span><span class="sxs-lookup"><span data-stu-id="f5736-127">Code</span></span>  
 [!code-vb[VbVbalrDataTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#14)]  
  
### <a name="comments"></a><span data-ttu-id="f5736-128">注释</span><span class="sxs-lookup"><span data-stu-id="f5736-128">Comments</span></span>  
 <span data-ttu-id="f5736-129">前面的示例要求进行比较的能力`searchValue`针对每个元素的`searchArray`。</span><span class="sxs-lookup"><span data-stu-id="f5736-129">The preceding example requires the ability to compare `searchValue` against each element of `searchArray`.</span></span> <span data-ttu-id="f5736-130">若要确保此功能，它可以约束类型参数`T`实现<xref:System.IComparable%601>接口。</span><span class="sxs-lookup"><span data-stu-id="f5736-130">To guarantee this ability, it constrains the type parameter `T` to implement the <xref:System.IComparable%601> interface.</span></span> <span data-ttu-id="f5736-131">该代码使用<xref:System.IComparable%601.CompareTo%2A>方法而不是`=`运算符，因为没有为提供的类型参数不能保证`T`支持`=`运算符。</span><span class="sxs-lookup"><span data-stu-id="f5736-131">The code uses the <xref:System.IComparable%601.CompareTo%2A> method instead of the `=` operator, because there is no guarantee that a type argument supplied for `T` supports the `=` operator.</span></span>  
  
 <span data-ttu-id="f5736-132">你可以测试`findElement`用下面的代码的过程。</span><span class="sxs-lookup"><span data-stu-id="f5736-132">You can test the `findElement` procedure with the following code.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#13)]  
  
 <span data-ttu-id="f5736-133">上述调用`MsgBox`分别显示"0"、"1"和"-1"。</span><span class="sxs-lookup"><span data-stu-id="f5736-133">The preceding calls to `MsgBox` display "0", "1", and "-1" respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5736-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5736-134">See also</span></span>

- [<span data-ttu-id="f5736-135">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="f5736-135">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="f5736-136">如何：定义可对不同数据类型提供相同功能的类</span><span class="sxs-lookup"><span data-stu-id="f5736-136">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)
- [<span data-ttu-id="f5736-137">如何：使用泛型类</span><span class="sxs-lookup"><span data-stu-id="f5736-137">How to: Use a Generic Class</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="f5736-138">过程</span><span class="sxs-lookup"><span data-stu-id="f5736-138">Procedures</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="f5736-139">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="f5736-139">Procedure Parameters and Arguments</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="f5736-140">类型列表</span><span class="sxs-lookup"><span data-stu-id="f5736-140">Type List</span></span>](../../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="f5736-141">参数列表</span><span class="sxs-lookup"><span data-stu-id="f5736-141">Parameter List</span></span>](../../../../visual-basic/language-reference/statements/parameter-list.md)
