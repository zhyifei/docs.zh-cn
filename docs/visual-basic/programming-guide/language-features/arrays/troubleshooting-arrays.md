---
title: "数组疑难解答 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0417ae8d37642a65b14cc81ae9dcf3a3c32d63ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-arrays-visual-basic"></a><span data-ttu-id="3a1b7-102">数组疑难解答 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a1b7-102">Troubleshooting Arrays (Visual Basic)</span></span>
<span data-ttu-id="3a1b7-103">此页列出与数组一起使用时可能发生的一些常见问题的方法。</span><span class="sxs-lookup"><span data-stu-id="3a1b7-103">This page lists some common problems that can occur when working with arrays.</span></span>  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a><span data-ttu-id="3a1b7-104">编译错误声明并初始化数组</span><span class="sxs-lookup"><span data-stu-id="3a1b7-104">Compilation Errors Declaring and Initializing an Array</span></span>  
 <span data-ttu-id="3a1b7-105">编译错误可能会产生误解的声明、 创建和初始化数组的规则。</span><span class="sxs-lookup"><span data-stu-id="3a1b7-105">Compilation errors can arise from misunderstanding of the rules for declaring, creating, and initializing arrays.</span></span> <span data-ttu-id="3a1b7-106">错误的最常见原因如下所示：</span><span class="sxs-lookup"><span data-stu-id="3a1b7-106">The most common causes of errors are the following:</span></span>  
  
-   <span data-ttu-id="3a1b7-107">提供[New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)子句后在数组变量声明中指定维的长度。</span><span class="sxs-lookup"><span data-stu-id="3a1b7-107">Supplying a [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) clause after specifying dimension lengths in the array variable declaration.</span></span> <span data-ttu-id="3a1b7-108">下面的代码行显示了无效的此类型的声明。</span><span class="sxs-lookup"><span data-stu-id="3a1b7-108">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   <span data-ttu-id="3a1b7-109">为多个顶级数组交错数组的指定维的长度。</span><span class="sxs-lookup"><span data-stu-id="3a1b7-109">Specifying dimension lengths for more than the top-level array of a jagged array.</span></span> <span data-ttu-id="3a1b7-110">下面的代码行显示此类型的一个无效的声明。</span><span class="sxs-lookup"><span data-stu-id="3a1b7-110">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   <span data-ttu-id="3a1b7-111">省略`New`关键字时指定的元素值。</span><span class="sxs-lookup"><span data-stu-id="3a1b7-111">Omitting the `New` keyword when specifying the element values.</span></span> <span data-ttu-id="3a1b7-112">下面的代码行显示此类型的一个无效的声明。</span><span class="sxs-lookup"><span data-stu-id="3a1b7-112">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   <span data-ttu-id="3a1b7-113">提供`New`子句时没有使用大括号 (`{}`)。</span><span class="sxs-lookup"><span data-stu-id="3a1b7-113">Supplying a `New` clause without braces (`{}`).</span></span> <span data-ttu-id="3a1b7-114">下面的代码行显示了无效的此类型的声明。</span><span class="sxs-lookup"><span data-stu-id="3a1b7-114">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a><span data-ttu-id="3a1b7-115">访问超出界限的数组</span><span class="sxs-lookup"><span data-stu-id="3a1b7-115">Accessing an Array Out of Bounds</span></span>  
 <span data-ttu-id="3a1b7-116">初始化数组的过程将分配给每个维度的上限和下限。</span><span class="sxs-lookup"><span data-stu-id="3a1b7-116">The process of initializing an array assigns an upper bound and a lower bound to each dimension.</span></span> <span data-ttu-id="3a1b7-117">每次访问数组的元素必须指定有效的索引或下标，对于每个维度。</span><span class="sxs-lookup"><span data-stu-id="3a1b7-117">Every access to an element of the array must specify a valid index, or subscript, for every dimension.</span></span> <span data-ttu-id="3a1b7-118">如果任何索引其下限低于或高于其上限<xref:System.IndexOutOfRangeException>异常结果。</span><span class="sxs-lookup"><span data-stu-id="3a1b7-118">If any index is below its lower bound or above its upper bound, an <xref:System.IndexOutOfRangeException> exception results.</span></span> <span data-ttu-id="3a1b7-119">编译器无法检测此类错误，因此在运行时出错。</span><span class="sxs-lookup"><span data-stu-id="3a1b7-119">The compiler cannot detect such an error, so an error occurs at run time.</span></span>  
  
### <a name="determining-bounds"></a><span data-ttu-id="3a1b7-120">确定边界</span><span class="sxs-lookup"><span data-stu-id="3a1b7-120">Determining Bounds</span></span>  
 <span data-ttu-id="3a1b7-121">如果另一个组件将数组传递给你的代码，例如作为过程自变量，你不知道该数组的大小或其维度的长度。</span><span class="sxs-lookup"><span data-stu-id="3a1b7-121">If another component passes an array to your code, for example as a procedure argument, you do not know the size of that array or the lengths of its dimensions.</span></span> <span data-ttu-id="3a1b7-122">然后再尝试访问任何元素，你始终应该确定对于数组的每个维度的上限。</span><span class="sxs-lookup"><span data-stu-id="3a1b7-122">You should always determine the upper bound for every dimension of an array before you attempt to access any elements.</span></span> <span data-ttu-id="3a1b7-123">如果数组创建以某种方式以外[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]`New`子句，下限可能不是 0，并且它是最安全的做法是，以确定该下限。</span><span class="sxs-lookup"><span data-stu-id="3a1b7-123">If the array has been created by some means other than a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] `New` clause, the lower bound might be something other than 0, and it is safest to determine that lower bound as well.</span></span>  
  
### <a name="specifying-the-dimension"></a><span data-ttu-id="3a1b7-124">指定维度</span><span class="sxs-lookup"><span data-stu-id="3a1b7-124">Specifying the Dimension</span></span>  
 <span data-ttu-id="3a1b7-125">在确定多维数组的边界时，一定要小心如何指定的维度。</span><span class="sxs-lookup"><span data-stu-id="3a1b7-125">When determining the bounds of a multidimensional array, take care how you specify the dimension.</span></span> <span data-ttu-id="3a1b7-126">`dimension`参数<xref:System.Array.GetLowerBound%2A>和<xref:System.Array.GetUpperBound%2A>方法是从 0 开始时`Rank`参数[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<xref:Microsoft.VisualBasic.Information.LBound%2A>和<xref:Microsoft.VisualBasic.Information.UBound%2A>函数都是基于 1 的。</span><span class="sxs-lookup"><span data-stu-id="3a1b7-126">The `dimension` parameters of the <xref:System.Array.GetLowerBound%2A> and <xref:System.Array.GetUpperBound%2A> methods are 0-based, while the `Rank` parameters of the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Information.LBound%2A> and <xref:Microsoft.VisualBasic.Information.UBound%2A> functions are 1-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a1b7-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a1b7-127">See Also</span></span>  
 [<span data-ttu-id="3a1b7-128">阵列</span><span class="sxs-lookup"><span data-stu-id="3a1b7-128">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="3a1b7-129">如何：在 Visual Basic 中初始化数组变量</span><span class="sxs-lookup"><span data-stu-id="3a1b7-129">How to: Initialize an Array Variable in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
