---
title: 缺少数组下标表达式
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30306
- vbc30306
helpviewer_keywords:
- BC30306
ms.assetid: 3c0d9732-ee37-436f-a1df-29d65712f48a
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aac09a90abf69fe53f46910fe4b542c6cc632c3a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="array-subscript-expression-missing"></a><span data-ttu-id="7cc76-102">缺少数组下标表达式</span><span class="sxs-lookup"><span data-stu-id="7cc76-102">Array subscript expression missing</span></span>
<span data-ttu-id="7cc76-103">数组初始化省略了一个或多个定义数组边界的下标。</span><span class="sxs-lookup"><span data-stu-id="7cc76-103">An array initialization leaves out one or more of the subscripts that define the array bounds.</span></span> <span data-ttu-id="7cc76-104">例如，语句可能包含表达式`myArray (5,5,,10)`，其中省略了第三个下标。</span><span class="sxs-lookup"><span data-stu-id="7cc76-104">For example, the statement might contain the expression `myArray (5,5,,10)`, which leaves out the third subscript.</span></span>  
  
 <span data-ttu-id="7cc76-105">**错误 ID:** BC30306</span><span class="sxs-lookup"><span data-stu-id="7cc76-105">**Error ID:** BC30306</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7cc76-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="7cc76-106">To correct this error</span></span>  
  
-   <span data-ttu-id="7cc76-107">提供缺少的下标。</span><span class="sxs-lookup"><span data-stu-id="7cc76-107">Supply the missing subscript.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cc76-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7cc76-108">See Also</span></span>  
 [<span data-ttu-id="7cc76-109">阵列</span><span class="sxs-lookup"><span data-stu-id="7cc76-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
