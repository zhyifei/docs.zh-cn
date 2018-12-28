---
title: “ReDim”只能更改最右边的维度
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 5b4f054c5d1dfad52ce19e1a9f9d246945866703
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2018
ms.locfileid: "53767383"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a><span data-ttu-id="aa694-102">“ReDim”只能更改最右边的维度</span><span class="sxs-lookup"><span data-stu-id="aa694-102">'ReDim' can only change the right-most dimension</span></span>
<span data-ttu-id="aa694-103">`ReDim` 语句尝试使用 `Preserve` 关键字来更改一个数组的维度，它不是最后一个维度。</span><span class="sxs-lookup"><span data-stu-id="aa694-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="aa694-104">使用 `Preserve`时，只能调整数组最后一个维度的大小。</span><span class="sxs-lookup"><span data-stu-id="aa694-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="aa694-105">对于其他所有维度，必须指定与现有数组相同的大小。</span><span class="sxs-lookup"><span data-stu-id="aa694-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="aa694-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="aa694-106">To correct this error</span></span>  
  
-   <span data-ttu-id="aa694-107">删除 `Preserve` 关键字。</span><span class="sxs-lookup"><span data-stu-id="aa694-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa694-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa694-108">See Also</span></span>  
 [<span data-ttu-id="aa694-109">Visual Basic 中的数组</span><span class="sxs-lookup"><span data-stu-id="aa694-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="aa694-110">在 Visual Basic 中的数组维数</span><span class="sxs-lookup"><span data-stu-id="aa694-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="aa694-111">ReDim 语句</span><span class="sxs-lookup"><span data-stu-id="aa694-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="aa694-112">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="aa694-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="aa694-113">保留 - 删除</span><span class="sxs-lookup"><span data-stu-id="aa694-113">Preserve - delete</span></span>](https://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
