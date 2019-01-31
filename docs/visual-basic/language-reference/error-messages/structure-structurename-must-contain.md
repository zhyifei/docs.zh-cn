---
title: 结构“<structurename>”至少必须包含一个实例成员变量或至少必须包含一个未标记为“Custom”的实例事件声明
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: a8a85f4f089de9be6f2ecadac05256b30d3014b0
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267451"
---
# <a name="structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a><span data-ttu-id="99608-102">结构\<结构名称 > 必须包含至少一个实例成员变量或未标记为 Custom 的至少一个实例事件声明</span><span class="sxs-lookup"><span data-stu-id="99608-102">Structure '\<structurename>' must contain at least one instance member variable or at least one instance event declaration not marked 'Custom'</span></span>
<span data-ttu-id="99608-103">结构定义不包括任何非共享的变量或非共享的非自定义事件。</span><span class="sxs-lookup"><span data-stu-id="99608-103">A structure definition does not include any nonshared variables or nonshared noncustom events.</span></span>  
  
 <span data-ttu-id="99608-104">每个结构都必须有一个变量或统称为适用于所有实例 （非共享） 而不是每个特定实例的事件 ([共享](../../../visual-basic/language-reference/modifiers/shared.md))。</span><span class="sxs-lookup"><span data-stu-id="99608-104">Every structure must have either a variable or an event that applies to each specific instance (nonshared) instead of to all instances collectively ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span></span> <span data-ttu-id="99608-105">非共享的常数、 属性和过程不满足此要求。</span><span class="sxs-lookup"><span data-stu-id="99608-105">Nonshared constants, properties, and procedures do not satisfy this requirement.</span></span> <span data-ttu-id="99608-106">此外，如果有任何非共享的变量和只能有一个非共享的事件，该事件不能为`Custom`事件。</span><span class="sxs-lookup"><span data-stu-id="99608-106">In addition, if there are no nonshared variables and only one nonshared event, that event cannot be a `Custom` event.</span></span>  
  
 <span data-ttu-id="99608-107">**错误 ID:** BC30941</span><span class="sxs-lookup"><span data-stu-id="99608-107">**Error ID:** BC30941</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="99608-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="99608-108">To correct this error</span></span>  
  
-   <span data-ttu-id="99608-109">定义至少一个变量或事件不是`Shared`。</span><span class="sxs-lookup"><span data-stu-id="99608-109">Define at least one variable or event that is not `Shared`.</span></span> <span data-ttu-id="99608-110">如果定义只能有一个事件，它必须为非自定义以及非共享。</span><span class="sxs-lookup"><span data-stu-id="99608-110">If you define only one event, it must be noncustom as well as nonshared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99608-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="99608-111">See also</span></span>
- [<span data-ttu-id="99608-112">结构</span><span class="sxs-lookup"><span data-stu-id="99608-112">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="99608-113">如何：声明结构</span><span class="sxs-lookup"><span data-stu-id="99608-113">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="99608-114">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="99608-114">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
