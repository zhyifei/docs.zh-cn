---
title: 如何：组相关的常量值组合在一起 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 04697092534daa6f83a29e69dcdc509644fa6147
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558678"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="8f810-102">如何：组相关的常量值组合在一起 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f810-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="8f810-103">枚举是要分成一组相关的常量的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="8f810-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="8f810-104">创建一个枚举，其中`Enum`声明部分中的一个类或模块的语句。</span><span class="sxs-lookup"><span data-stu-id="8f810-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="8f810-105">有关详细信息，请参阅[如何：声明枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)。</span><span class="sxs-lookup"><span data-stu-id="8f810-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="8f810-106">向组相关的常量值</span><span class="sxs-lookup"><span data-stu-id="8f810-106">To group related constant values</span></span>  
  
1.  <span data-ttu-id="8f810-107">编写的声明，包括代码访问级别，`Enum`关键字，并且是有效的名称。</span><span class="sxs-lookup"><span data-stu-id="8f810-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="8f810-108">此示例将创建`Private`枚举， `temperatureValues`。</span><span class="sxs-lookup"><span data-stu-id="8f810-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-group-related-constant-values-together_1.vb)]  
  
2.  <span data-ttu-id="8f810-109">枚举中定义常量。</span><span class="sxs-lookup"><span data-stu-id="8f810-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="8f810-110">此示例将创建`Public`枚举`temperatureValues`并为其赋值。</span><span class="sxs-lookup"><span data-stu-id="8f810-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-group-related-constant-values-together_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8f810-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f810-111">See also</span></span>
- [<span data-ttu-id="8f810-112">枚举和名称限定</span><span class="sxs-lookup"><span data-stu-id="8f810-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="8f810-113">如何：为枚举成员，请参阅</span><span class="sxs-lookup"><span data-stu-id="8f810-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="8f810-114">何时使用枚举</span><span class="sxs-lookup"><span data-stu-id="8f810-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="8f810-115">常量概述</span><span class="sxs-lookup"><span data-stu-id="8f810-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="8f810-116">常量和文本数据类型</span><span class="sxs-lookup"><span data-stu-id="8f810-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="8f810-117">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="8f810-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
