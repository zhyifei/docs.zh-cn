---
title: 标识符太长
ms.date: 07/20/2015
f1_keywords:
- bc30033
- vbc30033
helpviewer_keywords:
- BC30033
ms.assetid: 3d07f6d0-9a2f-49ca-94e8-1e354932e855
ms.openlocfilehash: 4c3933a5ad0be2b909bee633ac3be3d47adf39f2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686135"
---
# <a name="identifier-is-too-long"></a><span data-ttu-id="fb924-102">标识符太长</span><span class="sxs-lookup"><span data-stu-id="fb924-102">Identifier is too long</span></span>
<span data-ttu-id="fb924-103">名称或标识符的每个编程元素被限制为 1023年个字符。</span><span class="sxs-lookup"><span data-stu-id="fb924-103">The name, or identifier, of every programming element is limited to 1023 characters.</span></span> <span data-ttu-id="fb924-104">此外，完全限定的名称不能超过 1023年个字符。</span><span class="sxs-lookup"><span data-stu-id="fb924-104">In addition, a fully qualified name cannot exceed 1023 characters.</span></span> <span data-ttu-id="fb924-105">这意味着，整个标识符字符串 (`<namespace>.<...>.<namespace>.<class>.<element>`) 不能超过 1023年个字符之间，包括成员访问运算符 (`.`) 字符。</span><span class="sxs-lookup"><span data-stu-id="fb924-105">This means that the entire identifier string (`<namespace>.<...>.<namespace>.<class>.<element>`) cannot be more than 1023 characters long, including the member-access operator (`.`) characters.</span></span>  
  
 <span data-ttu-id="fb924-106">**错误 ID:** BC30033</span><span class="sxs-lookup"><span data-stu-id="fb924-106">**Error ID:** BC30033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fb924-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="fb924-107">To correct this error</span></span>  
  
-   <span data-ttu-id="fb924-108">减小标识符的长度。</span><span class="sxs-lookup"><span data-stu-id="fb924-108">Reduce the length of the identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb924-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb924-109">See also</span></span>
- [<span data-ttu-id="fb924-110">已声明的元素名称</span><span class="sxs-lookup"><span data-stu-id="fb924-110">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
