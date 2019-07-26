---
title: 数组界限不能出现在类型说明符中
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: 951f710160ae1023671773c21c73946f5ae94c2b
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512766"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a><span data-ttu-id="0beb6-102">数组界限不能出现在类型说明符中</span><span class="sxs-lookup"><span data-stu-id="0beb6-102">Array bounds cannot appear in type specifiers</span></span>

<span data-ttu-id="0beb6-103">数组大小不能声明为数据类型说明符的一部分。</span><span class="sxs-lookup"><span data-stu-id="0beb6-103">Array sizes cannot be declared as part of a data type specifier.</span></span>

<span data-ttu-id="0beb6-104">**错误 ID:** BC30638</span><span class="sxs-lookup"><span data-stu-id="0beb6-104">**Error ID:** BC30638</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="0beb6-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="0beb6-105">To correct this error</span></span>

- <span data-ttu-id="0beb6-106">指定紧随变量名称后面的数组大小, 而不是将数组大小放在类型之后, 如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="0beb6-106">Specify the size of the array immediately following the variable name instead of placing the array size after the type, as shown in the following example.</span></span>

  ```vb
  Dim Array(8) As Integer
  ```

- <span data-ttu-id="0beb6-107">定义一个数组, 并用所需的元素数对其进行初始化, 如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="0beb6-107">Define an array and initialize it with the desired number of elements, as shown in the following example.</span></span>

  ```vb
  Dim Array2() As Integer = New Integer(8) {}
  ```

## <a name="see-also"></a><span data-ttu-id="0beb6-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="0beb6-108">See also</span></span>

- [<span data-ttu-id="0beb6-109">数组</span><span class="sxs-lookup"><span data-stu-id="0beb6-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
