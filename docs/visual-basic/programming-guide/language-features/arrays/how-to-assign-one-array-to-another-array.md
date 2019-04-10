---
title: 如何：将一个数组赋给另一个数组 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: 78497de3a9aea55320639c55a151a1260a960159
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59303084"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a><span data-ttu-id="3c6c5-102">如何：将一个数组赋给另一个数组 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c6c5-102">How to: Assign One Array to Another Array (Visual Basic)</span></span>
<span data-ttu-id="3c6c5-103">由于数组是对象，您可以在赋值语句和其他对象类型一样使用它们。</span><span class="sxs-lookup"><span data-stu-id="3c6c5-103">Because arrays are objects, you can use them in assignment statements like other object types.</span></span> <span data-ttu-id="3c6c5-104">一个数组变量保留一个指向数据构成的数组元素和等级和长度的信息，并分配只复制此指针。</span><span class="sxs-lookup"><span data-stu-id="3c6c5-104">An array variable holds a pointer to the data constituting the array elements and the rank and length information, and an assignment copies only this pointer.</span></span>  
  
### <a name="to-assign-one-array-to-another-array"></a><span data-ttu-id="3c6c5-105">若要将一个数组赋给另一个数组</span><span class="sxs-lookup"><span data-stu-id="3c6c5-105">To assign one array to another array</span></span>  
  
1. <span data-ttu-id="3c6c5-106">请确保两个数组具有相同的秩 （维数） 和兼容的元素数据类型。</span><span class="sxs-lookup"><span data-stu-id="3c6c5-106">Ensure that the two arrays have the same rank (number of dimensions) and compatible element data types.</span></span>  
  
2. <span data-ttu-id="3c6c5-107">使用标准的赋值语句将源数组赋给目标数组。</span><span class="sxs-lookup"><span data-stu-id="3c6c5-107">Use a standard assignment statement to assign the source array to the destination array.</span></span> <span data-ttu-id="3c6c5-108">不遵循括号数组名。</span><span class="sxs-lookup"><span data-stu-id="3c6c5-108">Do not follow either array name with parentheses.</span></span>  
  
    ```  
    Dim formArray() As System.Windows.Forms.Form  
    Dim controlArray() As System.Windows.Forms.Control  
    controlArray = formArray  
    ```  
  
 <span data-ttu-id="3c6c5-109">当将一个数组赋给另一个时，以下规则适用：</span><span class="sxs-lookup"><span data-stu-id="3c6c5-109">When you assign one array to another, the following rules apply:</span></span>  
  
-   **<span data-ttu-id="3c6c5-110">相等的秩。</span><span class="sxs-lookup"><span data-stu-id="3c6c5-110">Equal Ranks.</span></span>** <span data-ttu-id="3c6c5-111">目标数组的秩 （维数） 必须是相同的源数组。</span><span class="sxs-lookup"><span data-stu-id="3c6c5-111">The rank (number of dimensions) of the destination array must be the same as that of the source array.</span></span>  
  
     <span data-ttu-id="3c6c5-112">提供两个数组的秩相等，维度不相等。</span><span class="sxs-lookup"><span data-stu-id="3c6c5-112">Provided the ranks of the two arrays are equal, the dimensions do not need to be equal.</span></span> <span data-ttu-id="3c6c5-113">在分配期间可以更改给定维度中的元素数。</span><span class="sxs-lookup"><span data-stu-id="3c6c5-113">The number of elements in a given dimension can change during assignment.</span></span>  
  
-   **<span data-ttu-id="3c6c5-114">元素类型。</span><span class="sxs-lookup"><span data-stu-id="3c6c5-114">Element Types.</span></span>** <span data-ttu-id="3c6c5-115">任一这两个数组必须具有*引用类型*必须具有的元素或这两个数组*值类型*元素。</span><span class="sxs-lookup"><span data-stu-id="3c6c5-115">Either both arrays must have *reference type* elements or both arrays must have *value type* elements.</span></span> <span data-ttu-id="3c6c5-116">有关更多信息，请参见 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)。</span><span class="sxs-lookup"><span data-stu-id="3c6c5-116">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
    -   <span data-ttu-id="3c6c5-117">如果这两个数组具有值类型的元素，元素数据类型必须完全相同。</span><span class="sxs-lookup"><span data-stu-id="3c6c5-117">If both arrays have value type elements, the element data types must be exactly the same.</span></span> <span data-ttu-id="3c6c5-118">唯一的例外是，您可以将分配的数组`Enum`的基类型的数组元素`Enum`。</span><span class="sxs-lookup"><span data-stu-id="3c6c5-118">The only exception to this is that you can assign an array of `Enum` elements to an array of the base type of that `Enum`.</span></span>  
  
    -   <span data-ttu-id="3c6c5-119">如果两个数组具有引用类型元素，则必须从目标元素类型派生的源元素类型。</span><span class="sxs-lookup"><span data-stu-id="3c6c5-119">If both arrays have reference type elements, the source element type must derive from the destination element type.</span></span> <span data-ttu-id="3c6c5-120">在这种情况下，两个数组具有相同的继承关系作为其元素。</span><span class="sxs-lookup"><span data-stu-id="3c6c5-120">When this is the case, the two arrays have the same inheritance relationship as their elements.</span></span> <span data-ttu-id="3c6c5-121">这称为*数组协方差*。</span><span class="sxs-lookup"><span data-stu-id="3c6c5-121">This is called *array covariance*.</span></span>  
  
 <span data-ttu-id="3c6c5-122">编译器会报告错误如果违反了上述规则，例如如果数据类型不兼容或者数组的秩不相等。</span><span class="sxs-lookup"><span data-stu-id="3c6c5-122">The compiler reports an error if the above rules are violated, for example if the data types are not compatible or the ranks are unequal.</span></span> <span data-ttu-id="3c6c5-123">您可以添加错误处理代码，以确保数组赋值前都兼容。</span><span class="sxs-lookup"><span data-stu-id="3c6c5-123">You can add error handling to your code to make sure that the arrays are compatible before attempting an assignment.</span></span> <span data-ttu-id="3c6c5-124">此外可以使用[TryCast 运算符](../../../../visual-basic/language-reference/operators/trycast-operator.md)关键字，如果你想要避免引发异常。</span><span class="sxs-lookup"><span data-stu-id="3c6c5-124">You can also use the [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) keyword if you want to avoid throwing an exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c6c5-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c6c5-125">See also</span></span>

- [<span data-ttu-id="3c6c5-126">数组</span><span class="sxs-lookup"><span data-stu-id="3c6c5-126">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="3c6c5-127">数组疑难解答</span><span class="sxs-lookup"><span data-stu-id="3c6c5-127">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [<span data-ttu-id="3c6c5-128">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="3c6c5-128">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="3c6c5-129">数组转换</span><span class="sxs-lookup"><span data-stu-id="3c6c5-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
