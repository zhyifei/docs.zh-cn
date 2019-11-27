---
title: 如何：将相关的常量值组合在一起
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 151eefee4f69e1db8ba40f91334da8a051b95732
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354030"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="2f473-102">如何：将相关的常量值组合在一起 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f473-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="2f473-103">枚举是将相关常量组合在一起的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="2f473-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="2f473-104">在类或模块的声明部分中，使用 `Enum` 语句创建枚举。</span><span class="sxs-lookup"><span data-stu-id="2f473-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="2f473-105">有关详细信息，请参阅[如何：声明枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)。</span><span class="sxs-lookup"><span data-stu-id="2f473-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="2f473-106">对相关常数值分组</span><span class="sxs-lookup"><span data-stu-id="2f473-106">To group related constant values</span></span>  
  
1. <span data-ttu-id="2f473-107">编写包含代码访问级别、`Enum` 关键字和有效名称的声明。</span><span class="sxs-lookup"><span data-stu-id="2f473-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="2f473-108">此示例创建 `Private` 枚举，`temperatureValues`。</span><span class="sxs-lookup"><span data-stu-id="2f473-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. <span data-ttu-id="2f473-109">定义枚举中的常量。</span><span class="sxs-lookup"><span data-stu-id="2f473-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="2f473-110">此示例创建 `Public` 枚举 `temperatureValues` 并分配其值。</span><span class="sxs-lookup"><span data-stu-id="2f473-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2f473-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f473-111">See also</span></span>

- [<span data-ttu-id="2f473-112">枚举和名称限定</span><span class="sxs-lookup"><span data-stu-id="2f473-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="2f473-113">如何：引用枚举成员</span><span class="sxs-lookup"><span data-stu-id="2f473-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="2f473-114">何时使用枚举</span><span class="sxs-lookup"><span data-stu-id="2f473-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="2f473-115">常量概述</span><span class="sxs-lookup"><span data-stu-id="2f473-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="2f473-116">常量和文本数据类型</span><span class="sxs-lookup"><span data-stu-id="2f473-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="2f473-117">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="2f473-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
