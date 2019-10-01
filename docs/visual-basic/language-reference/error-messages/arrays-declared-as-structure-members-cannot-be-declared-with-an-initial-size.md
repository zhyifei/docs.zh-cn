---
title: 声明为结构成员的数组不能用初始大小声明
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: de9d77aa9ea853b6f044e91878044115588ca77c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701249"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="a4dc9-102">声明为结构成员的数组不能用初始大小声明</span><span class="sxs-lookup"><span data-stu-id="a4dc9-102">Arrays declared as structure members cannot be declared with an initial size</span></span>
<span data-ttu-id="a4dc9-103">用初始大小声明了结构中的数组。</span><span class="sxs-lookup"><span data-stu-id="a4dc9-103">An array in a structure is declared with an initial size.</span></span> <span data-ttu-id="a4dc9-104">不能初始化任何结构元素，并且声明数组大小是一种初始化形式。</span><span class="sxs-lookup"><span data-stu-id="a4dc9-104">You cannot initialize any structure element, and declaring an array size is one form of initialization.</span></span>  
  
 <span data-ttu-id="a4dc9-105">**错误 ID：** BC31043</span><span class="sxs-lookup"><span data-stu-id="a4dc9-105">**Error ID:** BC31043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a4dc9-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="a4dc9-106">To correct this error</span></span>  
  
1. <span data-ttu-id="a4dc9-107">将结构中的数组定义为动态（无初始大小）。</span><span class="sxs-lookup"><span data-stu-id="a4dc9-107">Define the array in your structure as dynamic (no initial size).</span></span>  
  
2. <span data-ttu-id="a4dc9-108">如果需要特定大小的数组，则可以在代码运行时使用[ReDim 语句](../../../visual-basic/language-reference/statements/redim-statement.md)将动态数组的维数。</span><span class="sxs-lookup"><span data-stu-id="a4dc9-108">If you require a certain size of array, you can redimension a dynamic array with a [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) when your code is running.</span></span> <span data-ttu-id="a4dc9-109">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="a4dc9-109">The following example illustrates this.</span></span>  
  
    ```vb  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a4dc9-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4dc9-110">See also</span></span>

- [<span data-ttu-id="a4dc9-111">数组</span><span class="sxs-lookup"><span data-stu-id="a4dc9-111">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="a4dc9-112">如何：声明结构</span><span class="sxs-lookup"><span data-stu-id="a4dc9-112">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
