---
title: 结构&#39; &lt;structurename&gt; &#39;必须包含至少一个实例成员变量或未标记为至少一个实例事件声明&#39;自定义&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 85a4babc808e274a99f2c9faf08a02abf8aa4e93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594492"
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a><span data-ttu-id="a502c-102">结构&#39; &lt;structurename&gt; &#39;必须包含至少一个实例成员变量或未标记为至少一个实例事件声明&#39;自定义&#39;</span><span class="sxs-lookup"><span data-stu-id="a502c-102">Structure &#39;&lt;structurename&gt;&#39; must contain at least one instance member variable or at least one instance event declaration not marked &#39;Custom&#39;</span></span>
<span data-ttu-id="a502c-103">结构定义不包含任何非共享的变量或非共享的非自定义事件。</span><span class="sxs-lookup"><span data-stu-id="a502c-103">A structure definition does not include any nonshared variables or nonshared noncustom events.</span></span>  
  
 <span data-ttu-id="a502c-104">每个结构必须具有一个变量或共同适用于所有实例 （共享） 而不是每个特定实例的事件 ([共享](../../../visual-basic/language-reference/modifiers/shared.md))。</span><span class="sxs-lookup"><span data-stu-id="a502c-104">Every structure must have either a variable or an event that applies to each specific instance (nonshared) instead of to all instances collectively ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span></span> <span data-ttu-id="a502c-105">共享的常量、 属性和过程无法满足此要求。</span><span class="sxs-lookup"><span data-stu-id="a502c-105">Nonshared constants, properties, and procedures do not satisfy this requirement.</span></span> <span data-ttu-id="a502c-106">此外，如果有任何非共享的变量和只能有一个非共享的事件，该事件不能为`Custom`事件。</span><span class="sxs-lookup"><span data-stu-id="a502c-106">In addition, if there are no nonshared variables and only one nonshared event, that event cannot be a `Custom` event.</span></span>  
  
 <span data-ttu-id="a502c-107">**错误 ID:** BC30941</span><span class="sxs-lookup"><span data-stu-id="a502c-107">**Error ID:** BC30941</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a502c-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="a502c-108">To correct this error</span></span>  
  
-   <span data-ttu-id="a502c-109">定义至少一个变量或不是事件`Shared`。</span><span class="sxs-lookup"><span data-stu-id="a502c-109">Define at least one variable or event that is not `Shared`.</span></span> <span data-ttu-id="a502c-110">如果你定义只能有一个事件，则它必须非自定义以及非共享。</span><span class="sxs-lookup"><span data-stu-id="a502c-110">If you define only one event, it must be noncustom as well as nonshared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a502c-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="a502c-111">See Also</span></span>  
 [<span data-ttu-id="a502c-112">结构</span><span class="sxs-lookup"><span data-stu-id="a502c-112">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="a502c-113">如何：声明结构</span><span class="sxs-lookup"><span data-stu-id="a502c-113">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="a502c-114">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="a502c-114">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
