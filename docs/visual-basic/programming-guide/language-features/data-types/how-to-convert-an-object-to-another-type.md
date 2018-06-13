---
title: 如何：在 Visual Basic 中将一个对象转换为其他类型
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: 367991e4bbca710df54edf73179f855ff79bb56e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647613"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a><span data-ttu-id="8799d-102">如何：在 Visual Basic 中将一个对象转换为其他类型</span><span class="sxs-lookup"><span data-stu-id="8799d-102">How to: Convert an Object to Another Type in Visual Basic</span></span>
<span data-ttu-id="8799d-103">你将转换`Object`变量与另一个数据类型，使用转换关键字类似于[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)。</span><span class="sxs-lookup"><span data-stu-id="8799d-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8799d-104">示例</span><span class="sxs-lookup"><span data-stu-id="8799d-104">Example</span></span>  
 <span data-ttu-id="8799d-105">以下示例将转换`Object`变量`Integer`和`String`。</span><span class="sxs-lookup"><span data-stu-id="8799d-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span></span>  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 <span data-ttu-id="8799d-106">如果您知道的内容`Object`变量是否的特定的数据类型，则最好将变量转换为该数据类型。</span><span class="sxs-lookup"><span data-stu-id="8799d-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span></span> <span data-ttu-id="8799d-107">如果你继续使用`Object`变量，则会引发*装箱*和*取消装箱*（对于值类型） 或*后期绑定*（对于引用类型）。</span><span class="sxs-lookup"><span data-stu-id="8799d-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span></span> <span data-ttu-id="8799d-108">这些操作中，所有采用额外的执行时间，并会降低性能。</span><span class="sxs-lookup"><span data-stu-id="8799d-108">These operations all take extra execution time and make your performance slower.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8799d-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="8799d-109">Compiling the Code</span></span>  
 <span data-ttu-id="8799d-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="8799d-110">This example requires:</span></span>  
  
-   <span data-ttu-id="8799d-111">对 <xref:System?displayProperty=nameWithType> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="8799d-111">A reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8799d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="8799d-112">See Also</span></span>  
 <xref:System.Object>  
 [<span data-ttu-id="8799d-113">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="8799d-113">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="8799d-114">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="8799d-114">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="8799d-115">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="8799d-115">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="8799d-116">字符串和其他类型之间的转换</span><span class="sxs-lookup"><span data-stu-id="8799d-116">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [<span data-ttu-id="8799d-117">数组转换</span><span class="sxs-lookup"><span data-stu-id="8799d-117">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [<span data-ttu-id="8799d-118">结构</span><span class="sxs-lookup"><span data-stu-id="8799d-118">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="8799d-119">数据类型</span><span class="sxs-lookup"><span data-stu-id="8799d-119">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="8799d-120">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="8799d-120">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
