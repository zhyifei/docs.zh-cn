---
title: 如何：引用枚举成员
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: 01db5b84783eda45cd7867dc8fea8a69fc18b98a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353995"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a><span data-ttu-id="2d3c4-102">如何：引用枚举成员 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d3c4-102">How to: Refer to an Enumeration Member (Visual Basic)</span></span>
<span data-ttu-id="2d3c4-103">枚举提供了一种简便的方法来处理相关常量集，并将常量值与名称相关联。</span><span class="sxs-lookup"><span data-stu-id="2d3c4-103">Enumerations provide a convenient way to work with sets of related constants and to associate constant values with names.</span></span> <span data-ttu-id="2d3c4-104">例如，可以为一组与星期几相关联的整数常量声明一个枚举，然后在代码中使用星期几的名称而不是整数值。</span><span class="sxs-lookup"><span data-stu-id="2d3c4-104">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
 <span data-ttu-id="2d3c4-105">您可以避免对 `Imports` 语句使用完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="2d3c4-105">You can avoid using fully qualified names with the `Imports` statement.</span></span> <span data-ttu-id="2d3c4-106">有关详细信息，请参阅[枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)。</span><span class="sxs-lookup"><span data-stu-id="2d3c4-106">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-refer-to-an-enumeration-member"></a><span data-ttu-id="2d3c4-107">引用枚举成员</span><span class="sxs-lookup"><span data-stu-id="2d3c4-107">To refer to an enumeration member</span></span>  
  
- <span data-ttu-id="2d3c4-108">用枚举限定成员名称。</span><span class="sxs-lookup"><span data-stu-id="2d3c4-108">Qualify the member name with the enumeration.</span></span> <span data-ttu-id="2d3c4-109">例如，下面的示例将 `FirstDayOfWeek` 枚举的 `Saturday` 成员分配给变量 `DayValue`。</span><span class="sxs-lookup"><span data-stu-id="2d3c4-109">For example, the following example assigns the `Saturday` member of the `FirstDayOfWeek` enumeration to the variable `DayValue`.</span></span>  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="2d3c4-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d3c4-110">See also</span></span>

- [<span data-ttu-id="2d3c4-111">如何：声明枚举</span><span class="sxs-lookup"><span data-stu-id="2d3c4-111">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="2d3c4-112">枚举和名称限定</span><span class="sxs-lookup"><span data-stu-id="2d3c4-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="2d3c4-113">如何：在 Visual Basic 中循环访问枚举</span><span class="sxs-lookup"><span data-stu-id="2d3c4-113">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="2d3c4-114">如何：确定与枚举值关联的字符串</span><span class="sxs-lookup"><span data-stu-id="2d3c4-114">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="2d3c4-115">何时使用枚举</span><span class="sxs-lookup"><span data-stu-id="2d3c4-115">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
