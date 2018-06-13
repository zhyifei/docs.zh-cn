---
title: 声明为 For Each 循环控制变量的数组在声明时不能指定初始大小值
ms.date: 07/20/2015
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords:
- BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
ms.openlocfilehash: f6cf397b1e76313ab399d5e39a43ae0263df619c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587979"
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="bb799-102">声明为 For Each 循环控制变量的数组在声明时不能指定初始大小值</span><span class="sxs-lookup"><span data-stu-id="bb799-102">Array declared as for loop control variable cannot be declared with an initial size</span></span>
<span data-ttu-id="bb799-103">A`For Each`循环使用数组作为其*元素*迭代变量但初始化该数组。</span><span class="sxs-lookup"><span data-stu-id="bb799-103">A `For Each` loop uses an array as its *element* iteration variable but initializes that array.</span></span>  
  
 <span data-ttu-id="bb799-104">以下语句显示可以如何生成此错误。</span><span class="sxs-lookup"><span data-stu-id="bb799-104">The following statements show how this error can be generated.</span></span>  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 <span data-ttu-id="bb799-105">第一个`For Each`语句访问的元素的正确方法是`arrayList`。</span><span class="sxs-lookup"><span data-stu-id="bb799-105">The first `For Each` statement is the correct way to access elements of `arrayList`.</span></span> <span data-ttu-id="bb799-106">第二个`For Each`语句会生成此错误。</span><span class="sxs-lookup"><span data-stu-id="bb799-106">The second `For Each` statement generates this error.</span></span>  
  
 <span data-ttu-id="bb799-107">**错误 ID:** BC32039</span><span class="sxs-lookup"><span data-stu-id="bb799-107">**Error ID:** BC32039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bb799-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="bb799-108">To correct this error</span></span>  
  
-   <span data-ttu-id="bb799-109">从的声明中删除初始化*元素*迭代变量。</span><span class="sxs-lookup"><span data-stu-id="bb799-109">Remove the initialization from the declaration of the *element* iteration variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb799-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb799-110">See Also</span></span>  
 [<span data-ttu-id="bb799-111">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="bb799-111">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="bb799-112">数组</span><span class="sxs-lookup"><span data-stu-id="bb799-112">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="bb799-113">集合</span><span class="sxs-lookup"><span data-stu-id="bb799-113">Collections</span></span>](../../../standard/collections/index.md)
