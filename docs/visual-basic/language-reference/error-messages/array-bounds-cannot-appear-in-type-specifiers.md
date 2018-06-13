---
title: 数组界限不能出现在类型说明符中
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: 45787db51de562f2266c587fd2bb15ef29ebefbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583678"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a><span data-ttu-id="0fe28-102">数组界限不能出现在类型说明符中</span><span class="sxs-lookup"><span data-stu-id="0fe28-102">Array bounds cannot appear in type specifiers</span></span>
<span data-ttu-id="0fe28-103">数组大小不能声明为数据类型说明符的一部分。</span><span class="sxs-lookup"><span data-stu-id="0fe28-103">Array sizes cannot be declared as part of a data type specifier.</span></span>  
  
 <span data-ttu-id="0fe28-104">**错误 ID:** BC30638</span><span class="sxs-lookup"><span data-stu-id="0fe28-104">**Error ID:** BC30638</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0fe28-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="0fe28-105">To correct this error</span></span>  
  
-   <span data-ttu-id="0fe28-106">指定紧靠而不是类型之后，将数组大小的变量名称，如下面的示例中所示的数组的大小。</span><span class="sxs-lookup"><span data-stu-id="0fe28-106">Specify the size of the array immediately following the variable name instead of placing the array size after the type, as shown in the following example.</span></span>  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   <span data-ttu-id="0fe28-107">定义一个数组，并将其与所需的元素数进行初始化，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="0fe28-107">Define an array and initialize it with the desired number of elements, as shown in the following example.</span></span>  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0fe28-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fe28-108">See Also</span></span>  
 [<span data-ttu-id="0fe28-109">数组</span><span class="sxs-lookup"><span data-stu-id="0fe28-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
