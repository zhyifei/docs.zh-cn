---
title: 声明为结构成员的数组不能用初始大小声明
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: 5d58b531b670715716e849cd37227bc899195df6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935364"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="a7acd-102">声明为结构成员的数组不能用初始大小声明</span><span class="sxs-lookup"><span data-stu-id="a7acd-102">Arrays declared as structure members cannot be declared with an initial size</span></span>
<span data-ttu-id="a7acd-103">初始大小声明数组在结构中。</span><span class="sxs-lookup"><span data-stu-id="a7acd-103">An array in a structure is declared with an initial size.</span></span> <span data-ttu-id="a7acd-104">无法初始化结构的任何元素，并声明的数组大小是一种形式的初始化。</span><span class="sxs-lookup"><span data-stu-id="a7acd-104">You cannot initialize any structure element, and declaring an array size is one form of initialization.</span></span>  
  
 <span data-ttu-id="a7acd-105">**错误 ID:** BC31043</span><span class="sxs-lookup"><span data-stu-id="a7acd-105">**Error ID:** BC31043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a7acd-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="a7acd-106">To correct this error</span></span>  
  
1. <span data-ttu-id="a7acd-107">定义数组结构中为动态 （不是初始大小）。</span><span class="sxs-lookup"><span data-stu-id="a7acd-107">Define the array in your structure as dynamic (no initial size).</span></span>  
  
2. <span data-ttu-id="a7acd-108">如果需要特定大小的数组，可以重新使用的动态数组设置其维数[ReDim 语句](../../../visual-basic/language-reference/statements/redim-statement.md)时运行代码。</span><span class="sxs-lookup"><span data-stu-id="a7acd-108">If you require a certain size of array, you can redimension a dynamic array with a [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) when your code is running.</span></span> <span data-ttu-id="a7acd-109">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="a7acd-109">The following example illustrates this.</span></span>  
  
    ```  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a7acd-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7acd-110">See also</span></span>

- [<span data-ttu-id="a7acd-111">数组</span><span class="sxs-lookup"><span data-stu-id="a7acd-111">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="a7acd-112">如何：声明结构</span><span class="sxs-lookup"><span data-stu-id="a7acd-112">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
