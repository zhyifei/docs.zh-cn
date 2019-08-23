---
title: 无法根据这些实参推断类型形参的数据类型
ms.date: 07/20/2015
f1_keywords:
- bc36644
- bc36647
- vbc36647
- vbc36644
helpviewer_keywords:
- BC36644
- BC36647
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
ms.openlocfilehash: 81535e3272eaed587288c26c4a4b9649467abed8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963563"
---
# <a name="data-types-of-the-type-parameters-cannot-be-inferred-from-these-arguments"></a><span data-ttu-id="e5910-102">无法根据这些实参推断类型形参的数据类型</span><span class="sxs-lookup"><span data-stu-id="e5910-102">Data type(s) of the type parameter(s) cannot be inferred from these arguments</span></span>
<span data-ttu-id="e5910-103">无法根据这些参数推断出类型参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e5910-103">Data type(s) of the type parameter(s) cannot be inferred from these arguments.</span></span> <span data-ttu-id="e5910-104">显式指定数据类型可更正此错误。</span><span class="sxs-lookup"><span data-stu-id="e5910-104">Specifying the data type(s) explicitly might correct this error.</span></span>  
  
 <span data-ttu-id="e5910-105">当重载决策失败时发生此错误。</span><span class="sxs-lookup"><span data-stu-id="e5910-105">This error occurs when overload resolution has failed.</span></span> <span data-ttu-id="e5910-106">它以从属消息的形式发生，该消息指出已消除特定的重载候选。</span><span class="sxs-lookup"><span data-stu-id="e5910-106">It occurs as a subordinate message that states why a particular overload candidate has been eliminated.</span></span> <span data-ttu-id="e5910-107">错误消息说明编译器无法使用类型推理来查找类型参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e5910-107">The error message explains that the compiler cannot use type inference to find data types for the type parameters.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5910-108">当无法指定实参时（例如，对于查询表达式中的查询运算符），显示的错误消息不包括第二个句子。</span><span class="sxs-lookup"><span data-stu-id="e5910-108">When specifying arguments is not an option (for example, for query operators in query expressions), the error message appears without the second sentence.</span></span>  
  
 <span data-ttu-id="e5910-109">下面的代码演示了此错误。</span><span class="sxs-lookup"><span data-stu-id="e5910-109">The following code demonstrates the error.</span></span>  
  
```vb  
Module Module1  
  
    Sub Main()  
  
        '' Not Valid.  
        'OverloadedGenericMethod("Hello", "World")  
  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T)(ByVal x As String,   
                                      ByVal y As InterfaceExample(Of T))  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T, R)(ByVal x As T,   
                                         ByVal y As InterfaceExample(Of R))  
    End Sub  
  
End Module  
  
Interface InterfaceExample(Of T)  
End Interface  
```  
  
 <span data-ttu-id="e5910-110">**错误 ID:** BC36647 和 BC36644</span><span class="sxs-lookup"><span data-stu-id="e5910-110">**Error ID:** BC36647 and BC36644</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e5910-111">更正此错误</span><span class="sxs-lookup"><span data-stu-id="e5910-111">To correct this error</span></span>  
  
- <span data-ttu-id="e5910-112">你或许能够指定类型形参的数据类型，而无需依赖类型推断。</span><span class="sxs-lookup"><span data-stu-id="e5910-112">You may be able to specify a data type for the type parameter or parameters instead of relying on type inference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5910-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5910-113">See also</span></span>

- [<span data-ttu-id="e5910-114">宽松委托转换</span><span class="sxs-lookup"><span data-stu-id="e5910-114">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="e5910-115">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5910-115">Generic Procedures in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)
- [<span data-ttu-id="e5910-116">Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="e5910-116">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
