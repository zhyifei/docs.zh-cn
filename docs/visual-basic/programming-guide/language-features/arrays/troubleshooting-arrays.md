---
title: 数组疑难解答 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: 69d5294eacc59718adb1b0a226594d2cf69273f5
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2019
ms.locfileid: "64913469"
---
# <a name="troubleshooting-arrays-visual-basic"></a><span data-ttu-id="48c3f-102">数组疑难解答 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48c3f-102">Troubleshooting Arrays (Visual Basic)</span></span>
<span data-ttu-id="48c3f-103">此页列出了在使用数组时可能发生的一些常见问题。</span><span class="sxs-lookup"><span data-stu-id="48c3f-103">This page lists some common problems that can occur when working with arrays.</span></span>  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a><span data-ttu-id="48c3f-104">编译错误声明和初始化数组</span><span class="sxs-lookup"><span data-stu-id="48c3f-104">Compilation Errors Declaring and Initializing an Array</span></span>  
 <span data-ttu-id="48c3f-105">编译错误则可能会产生误解的声明、 创建和初始化数组的规则。</span><span class="sxs-lookup"><span data-stu-id="48c3f-105">Compilation errors can arise from misunderstanding of the rules for declaring, creating, and initializing arrays.</span></span> <span data-ttu-id="48c3f-106">错误的最常见原因如下所示：</span><span class="sxs-lookup"><span data-stu-id="48c3f-106">The most common causes of errors are the following:</span></span>  
  
- <span data-ttu-id="48c3f-107">提供[New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)子句后的数组变量声明中指定维的长度。</span><span class="sxs-lookup"><span data-stu-id="48c3f-107">Supplying a [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) clause after specifying dimension lengths in the array variable declaration.</span></span> <span data-ttu-id="48c3f-108">下面的代码行显示无效的此类型声明。</span><span class="sxs-lookup"><span data-stu-id="48c3f-108">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
- <span data-ttu-id="48c3f-109">对多个顶级数组交错数组的指定维的长度。</span><span class="sxs-lookup"><span data-stu-id="48c3f-109">Specifying dimension lengths for more than the top-level array of a jagged array.</span></span> <span data-ttu-id="48c3f-110">以下代码行显示此类型的一个无效的声明。</span><span class="sxs-lookup"><span data-stu-id="48c3f-110">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
- <span data-ttu-id="48c3f-111">省略`New`关键字时指定的元素值。</span><span class="sxs-lookup"><span data-stu-id="48c3f-111">Omitting the `New` keyword when specifying the element values.</span></span> <span data-ttu-id="48c3f-112">以下代码行显示此类型的一个无效的声明。</span><span class="sxs-lookup"><span data-stu-id="48c3f-112">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
- <span data-ttu-id="48c3f-113">提供`New`子句时没有使用大括号 (`{}`)。</span><span class="sxs-lookup"><span data-stu-id="48c3f-113">Supplying a `New` clause without braces (`{}`).</span></span> <span data-ttu-id="48c3f-114">下面的代码行显示无效的此类型声明。</span><span class="sxs-lookup"><span data-stu-id="48c3f-114">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a><span data-ttu-id="48c3f-115">访问数组超出界限</span><span class="sxs-lookup"><span data-stu-id="48c3f-115">Accessing an Array Out of Bounds</span></span>  
 <span data-ttu-id="48c3f-116">初始化数组的过程将分配给每个维度的上限和下限。</span><span class="sxs-lookup"><span data-stu-id="48c3f-116">The process of initializing an array assigns an upper bound and a lower bound to each dimension.</span></span> <span data-ttu-id="48c3f-117">每次访问数组的元素必须指定有效的索引或每个维度的下标。</span><span class="sxs-lookup"><span data-stu-id="48c3f-117">Every access to an element of the array must specify a valid index, or subscript, for every dimension.</span></span> <span data-ttu-id="48c3f-118">如果任何索引其下限低于或高于其上限<xref:System.IndexOutOfRangeException>异常结果。</span><span class="sxs-lookup"><span data-stu-id="48c3f-118">If any index is below its lower bound or above its upper bound, an <xref:System.IndexOutOfRangeException> exception results.</span></span> <span data-ttu-id="48c3f-119">编译器无法检测此类错误，因此在运行时出错。</span><span class="sxs-lookup"><span data-stu-id="48c3f-119">The compiler cannot detect such an error, so an error occurs at run time.</span></span>  
  
### <a name="determining-bounds"></a><span data-ttu-id="48c3f-120">确定边界</span><span class="sxs-lookup"><span data-stu-id="48c3f-120">Determining Bounds</span></span>  
 <span data-ttu-id="48c3f-121">如果另一个组件将数组传递给你的代码，例如作为过程自变量，您不知道该数组的大小或它的维的长度。</span><span class="sxs-lookup"><span data-stu-id="48c3f-121">If another component passes an array to your code, for example as a procedure argument, you do not know the size of that array or the lengths of its dimensions.</span></span> <span data-ttu-id="48c3f-122">在尝试访问任何元素之前，您应首先确定数组的每个维度的上限。</span><span class="sxs-lookup"><span data-stu-id="48c3f-122">You should always determine the upper bound for every dimension of an array before you attempt to access any elements.</span></span> <span data-ttu-id="48c3f-123">如果已通过 Visual Basic 以外的某种方式创建数组`New`子句，更低绑定可能不是 0，并且是最安全，以确定该下限。</span><span class="sxs-lookup"><span data-stu-id="48c3f-123">If the array has been created by some means other than a Visual Basic `New` clause, the lower bound might be something other than 0, and it is safest to determine that lower bound as well.</span></span>  
  
### <a name="specifying-the-dimension"></a><span data-ttu-id="48c3f-124">指定维度</span><span class="sxs-lookup"><span data-stu-id="48c3f-124">Specifying the Dimension</span></span>  
 <span data-ttu-id="48c3f-125">在确定一个多维数组的边界时，请注意如何指定的维度。</span><span class="sxs-lookup"><span data-stu-id="48c3f-125">When determining the bounds of a multidimensional array, take care how you specify the dimension.</span></span> <span data-ttu-id="48c3f-126">`dimension`的参数<xref:System.Array.GetLowerBound%2A>并<xref:System.Array.GetUpperBound%2A>方法是基于 0 的同时`Rank`参数的 Visual basic<xref:Microsoft.VisualBasic.Information.LBound%2A>和<xref:Microsoft.VisualBasic.Information.UBound%2A>函数都是基于 1 的。</span><span class="sxs-lookup"><span data-stu-id="48c3f-126">The `dimension` parameters of the <xref:System.Array.GetLowerBound%2A> and <xref:System.Array.GetUpperBound%2A> methods are 0-based, while the `Rank` parameters of the Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> and <xref:Microsoft.VisualBasic.Information.UBound%2A> functions are 1-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48c3f-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="48c3f-127">See also</span></span>

- [<span data-ttu-id="48c3f-128">数组</span><span class="sxs-lookup"><span data-stu-id="48c3f-128">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="48c3f-129">如何：初始化数组变量在 Visual Basic 中</span><span class="sxs-lookup"><span data-stu-id="48c3f-129">How to: Initialize an Array Variable in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
