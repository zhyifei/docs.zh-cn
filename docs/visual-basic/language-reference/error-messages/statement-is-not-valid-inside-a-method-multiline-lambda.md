---
title: 语句在方法-多行 lambda 内无效
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: 994cafc44a37d16d0f70caec560f530c6a836ec0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841558"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a><span data-ttu-id="709bc-102">语句在方法/多行 lambda 内无效</span><span class="sxs-lookup"><span data-stu-id="709bc-102">Statement is not valid inside a method/multiline lambda</span></span>
<span data-ttu-id="709bc-103">语句内无效`Sub`， `Function`，属性`Get`，或属性`Set`过程。</span><span class="sxs-lookup"><span data-stu-id="709bc-103">The statement is not valid within a `Sub`, `Function`, property `Get`, or property `Set` procedure.</span></span> <span data-ttu-id="709bc-104">某些语句可以放置在模块或类级别。</span><span class="sxs-lookup"><span data-stu-id="709bc-104">Some statements can be placed at the module or class level.</span></span> <span data-ttu-id="709bc-105">其他人，例如`Option Strict`，必须为命名空间级别并且位于所有其他声明之前。</span><span class="sxs-lookup"><span data-stu-id="709bc-105">Others, such as `Option Strict`, must be at namespace level and precede all other declarations.</span></span>  
  
 <span data-ttu-id="709bc-106">**错误 ID:** BC30024</span><span class="sxs-lookup"><span data-stu-id="709bc-106">**Error ID:** BC30024</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="709bc-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="709bc-107">To correct this error</span></span>  
  
-   <span data-ttu-id="709bc-108">从过程中删除该语句。</span><span class="sxs-lookup"><span data-stu-id="709bc-108">Remove the statement from the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="709bc-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="709bc-109">See also</span></span>

- [<span data-ttu-id="709bc-110">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="709bc-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="709bc-111">Function 语句</span><span class="sxs-lookup"><span data-stu-id="709bc-111">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="709bc-112">Get 语句</span><span class="sxs-lookup"><span data-stu-id="709bc-112">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="709bc-113">Set 语句</span><span class="sxs-lookup"><span data-stu-id="709bc-113">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
