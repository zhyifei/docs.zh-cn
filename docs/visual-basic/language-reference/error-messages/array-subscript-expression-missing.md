---
title: 缺少数组下标表达式
ms.date: 07/20/2015
f1_keywords:
- bc30306
- vbc30306
helpviewer_keywords:
- BC30306
ms.assetid: 3c0d9732-ee37-436f-a1df-29d65712f48a
ms.openlocfilehash: 4dadad63f4321e88b79f2006a9e6b7befa27909a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58837554"
---
# <a name="array-subscript-expression-missing"></a><span data-ttu-id="3f44f-102">缺少数组下标表达式</span><span class="sxs-lookup"><span data-stu-id="3f44f-102">Array subscript expression missing</span></span>
<span data-ttu-id="3f44f-103">数组初始化省略了一个或多个定义数组边界的下标。</span><span class="sxs-lookup"><span data-stu-id="3f44f-103">An array initialization leaves out one or more of the subscripts that define the array bounds.</span></span> <span data-ttu-id="3f44f-104">例如，该语句可能包含表达式`myArray (5,5,,10)`，其中省略了第三个下标。</span><span class="sxs-lookup"><span data-stu-id="3f44f-104">For example, the statement might contain the expression `myArray (5,5,,10)`, which leaves out the third subscript.</span></span>  
  
 <span data-ttu-id="3f44f-105">**错误 ID:** BC30306</span><span class="sxs-lookup"><span data-stu-id="3f44f-105">**Error ID:** BC30306</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3f44f-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="3f44f-106">To correct this error</span></span>  
  
-   <span data-ttu-id="3f44f-107">提供缺少的下标。</span><span class="sxs-lookup"><span data-stu-id="3f44f-107">Supply the missing subscript.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f44f-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f44f-108">See also</span></span>

- [<span data-ttu-id="3f44f-109">数组</span><span class="sxs-lookup"><span data-stu-id="3f44f-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
