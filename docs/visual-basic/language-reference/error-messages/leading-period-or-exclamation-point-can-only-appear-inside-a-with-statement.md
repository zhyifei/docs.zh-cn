---
title: 前导“.”或“!”只能出现在“With”语句内
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 15390fb506fe9bca10f6917f5b26451a5569bece
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921116"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a><span data-ttu-id="5f687-102">前导“.”或“!”只能出现在“With”语句内</span><span class="sxs-lookup"><span data-stu-id="5f687-102">Leading '.' or '!' can only appear inside a 'With' statement</span></span>
<span data-ttu-id="5f687-103">句点 （.） 或感叹号 （！） 不深入了解`With`块内不使用左侧的表达式。</span><span class="sxs-lookup"><span data-stu-id="5f687-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="5f687-104">成员访问 (`.`) 和字典成员访问 (`!`) 需要一个表达式，指定包含该成员的元素。</span><span class="sxs-lookup"><span data-stu-id="5f687-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="5f687-105">这必须紧靠左侧的访问器或作为目标的`With`块，其中包含成员访问。</span><span class="sxs-lookup"><span data-stu-id="5f687-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="5f687-106">**错误 ID:** BC30157</span><span class="sxs-lookup"><span data-stu-id="5f687-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5f687-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="5f687-107">To correct this error</span></span>  
  
1. <span data-ttu-id="5f687-108">确保`With`块的格式正确。</span><span class="sxs-lookup"><span data-stu-id="5f687-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2. <span data-ttu-id="5f687-109">如果没有任何`With`块中，将表达式添加到包含该成员的定义元素的计算结果的访问器的左侧。</span><span class="sxs-lookup"><span data-stu-id="5f687-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f687-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f687-110">See also</span></span>

- [<span data-ttu-id="5f687-111">代码中的特殊字符</span><span class="sxs-lookup"><span data-stu-id="5f687-111">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="5f687-112">With...End With 语句</span><span class="sxs-lookup"><span data-stu-id="5f687-112">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
