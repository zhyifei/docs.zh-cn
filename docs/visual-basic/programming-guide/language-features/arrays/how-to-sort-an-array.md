---
title: 如何：在 Visual Basic 中对数组进行排序
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: a067c40e1dd0e881516cbc7769cb9afb879d1b9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646286"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="e8c7b-102">如何：在 Visual Basic 中对数组进行排序</span><span class="sxs-lookup"><span data-stu-id="e8c7b-102">How to: Sort An Array in Visual Basic</span></span>
<span data-ttu-id="e8c7b-103">此示例声明的数组`String`对象命名的`zooAnimals`、 填充它，并按字母顺序排序。</span><span class="sxs-lookup"><span data-stu-id="e8c7b-103">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8c7b-104">示例</span><span class="sxs-lookup"><span data-stu-id="e8c7b-104">Example</span></span>  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e8c7b-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="e8c7b-105">Compiling the Code</span></span>  
 <span data-ttu-id="e8c7b-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="e8c7b-106">This example requires:</span></span>  
  
-   <span data-ttu-id="e8c7b-107">访问 mscorlib.dll 和<xref:System>命名空间。</span><span class="sxs-lookup"><span data-stu-id="e8c7b-107">Access to Mscorlib.dll and the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e8c7b-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="e8c7b-108">Robust Programming</span></span>  
 <span data-ttu-id="e8c7b-109">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="e8c7b-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="e8c7b-110">数组为空 (<xref:System.ArgumentNullException>类)</span><span class="sxs-lookup"><span data-stu-id="e8c7b-110">Array is empty (<xref:System.ArgumentNullException> class)</span></span>  
  
-   <span data-ttu-id="e8c7b-111">数组是多维数组 (<xref:System.RankException>类)</span><span class="sxs-lookup"><span data-stu-id="e8c7b-111">Array is multidimensional (<xref:System.RankException> class)</span></span>  
  
-   <span data-ttu-id="e8c7b-112">数组的一个或多个元素不实现<xref:System.IComparable>接口 (<xref:System.InvalidOperationException>类)</span><span class="sxs-lookup"><span data-stu-id="e8c7b-112">One or more elements of the array do not implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8c7b-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8c7b-113">See Also</span></span>  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="e8c7b-114">数组</span><span class="sxs-lookup"><span data-stu-id="e8c7b-114">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="e8c7b-115">数组疑难解答</span><span class="sxs-lookup"><span data-stu-id="e8c7b-115">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)  
 [<span data-ttu-id="e8c7b-116">集合</span><span class="sxs-lookup"><span data-stu-id="e8c7b-116">Collections</span></span>](../../concepts/collections.md)  
 [<span data-ttu-id="e8c7b-117">For Each...Next 语句</span><span class="sxs-lookup"><span data-stu-id="e8c7b-117">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
