---
title: "&#39;ReDim &#39;只能更改最右边的维度"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 989a06f94824dfd051d1a7d2e7749dbb8c8e11a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="39redim39-can-only-change-the-right-most-dimension"></a><span data-ttu-id="76587-102">&#39;ReDim &#39;只能更改最右边的维度</span><span class="sxs-lookup"><span data-stu-id="76587-102">&#39;ReDim&#39; can only change the right-most dimension</span></span>
<span data-ttu-id="76587-103">`ReDim` 语句尝试使用 `Preserve` 关键字来更改一个数组的维度，它不是最后一个维度。</span><span class="sxs-lookup"><span data-stu-id="76587-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="76587-104">使用 `Preserve`时，只能调整数组最后一个维度的大小。</span><span class="sxs-lookup"><span data-stu-id="76587-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="76587-105">对于其他所有维度，必须指定与现有数组相同的大小。</span><span class="sxs-lookup"><span data-stu-id="76587-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="76587-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="76587-106">To correct this error</span></span>  
  
-   <span data-ttu-id="76587-107">删除 `Preserve` 关键字。</span><span class="sxs-lookup"><span data-stu-id="76587-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76587-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76587-108">See Also</span></span>  
 [<span data-ttu-id="76587-109">Visual Basic 中的数组</span><span class="sxs-lookup"><span data-stu-id="76587-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="76587-110">在 Visual Basic 中的数组维数</span><span class="sxs-lookup"><span data-stu-id="76587-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="76587-111">ReDim 语句</span><span class="sxs-lookup"><span data-stu-id="76587-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="76587-112">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="76587-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="76587-113">保留-删除</span><span class="sxs-lookup"><span data-stu-id="76587-113">Preserve - delete</span></span>](http://msdn.microsoft.com/en-us/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
