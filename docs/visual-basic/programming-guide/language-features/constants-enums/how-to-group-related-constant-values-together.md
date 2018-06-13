---
title: 如何：将相关的常量值组合在一起 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 320373116ad4d61293690353fce6b7b152e79a4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646391"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="7da81-102">如何：将相关的常量值组合在一起 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7da81-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="7da81-103">枚举是将相关的常量组合在一起的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="7da81-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="7da81-104">创建一个包含枚举`Enum`声明部分中的一个类或模块的语句。</span><span class="sxs-lookup"><span data-stu-id="7da81-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="7da81-105">有关详细信息，请参阅[如何： 声明枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)。</span><span class="sxs-lookup"><span data-stu-id="7da81-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="7da81-106">到组相关的常量值</span><span class="sxs-lookup"><span data-stu-id="7da81-106">To group related constant values</span></span>  
  
1.  <span data-ttu-id="7da81-107">编写包含代码访问级别，声明`Enum`关键字和有效的名称。</span><span class="sxs-lookup"><span data-stu-id="7da81-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="7da81-108">此示例将创建`Private`枚举， `temperatureValues`。</span><span class="sxs-lookup"><span data-stu-id="7da81-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-group-related-constant-values-together_1.vb)]  
  
2.  <span data-ttu-id="7da81-109">枚举中定义常量。</span><span class="sxs-lookup"><span data-stu-id="7da81-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="7da81-110">此示例将创建`Public`枚举`temperatureValues`并为其赋值。</span><span class="sxs-lookup"><span data-stu-id="7da81-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-group-related-constant-values-together_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7da81-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="7da81-111">See Also</span></span>  
 [<span data-ttu-id="7da81-112">枚举和名称限定</span><span class="sxs-lookup"><span data-stu-id="7da81-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="7da81-113">如何：引用枚举成员</span><span class="sxs-lookup"><span data-stu-id="7da81-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="7da81-114">何时使用枚举</span><span class="sxs-lookup"><span data-stu-id="7da81-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="7da81-115">常量概述</span><span class="sxs-lookup"><span data-stu-id="7da81-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="7da81-116">常量和文本数据类型</span><span class="sxs-lookup"><span data-stu-id="7da81-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [<span data-ttu-id="7da81-117">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="7da81-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
