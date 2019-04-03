---
title: 数组界限不能出现在类型说明符中
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: f20ed883005641082eb89e2effa5221594910ffe
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838776"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a><span data-ttu-id="14b75-102">数组界限不能出现在类型说明符中</span><span class="sxs-lookup"><span data-stu-id="14b75-102">Array bounds cannot appear in type specifiers</span></span>
<span data-ttu-id="14b75-103">数组大小不能声明为数据类型说明符的一部分。</span><span class="sxs-lookup"><span data-stu-id="14b75-103">Array sizes cannot be declared as part of a data type specifier.</span></span>  
  
 <span data-ttu-id="14b75-104">**错误 ID:** BC30638</span><span class="sxs-lookup"><span data-stu-id="14b75-104">**Error ID:** BC30638</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="14b75-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="14b75-105">To correct this error</span></span>  
  
-   <span data-ttu-id="14b75-106">指定紧跟变量的名称，而不是数组大小类型之后，如下面的示例中所示的数组的大小。</span><span class="sxs-lookup"><span data-stu-id="14b75-106">Specify the size of the array immediately following the variable name instead of placing the array size after the type, as shown in the following example.</span></span>  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   <span data-ttu-id="14b75-107">定义一个数组并将其与所需的元素数进行初始化，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="14b75-107">Define an array and initialize it with the desired number of elements, as shown in the following example.</span></span>  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="14b75-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="14b75-108">See also</span></span>

- [<span data-ttu-id="14b75-109">数组</span><span class="sxs-lookup"><span data-stu-id="14b75-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
