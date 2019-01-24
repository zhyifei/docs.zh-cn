---
title: 如何：引用枚举成员 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: efaaecb231b340798012206a0f23fde0ad4cdbeb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601992"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a><span data-ttu-id="8659d-102">如何：引用枚举成员 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8659d-102">How to: Refer to an Enumeration Member (Visual Basic)</span></span>
<span data-ttu-id="8659d-103">枚举提供简便的方法来处理相关常量集以及要将常量值与名称相关联。</span><span class="sxs-lookup"><span data-stu-id="8659d-103">Enumerations provide a convenient way to work with sets of related constants and to associate constant values with names.</span></span> <span data-ttu-id="8659d-104">例如，可以为一组与星期几相关联的整数常量声明一个枚举，然后在代码中使用星期几的名称而不是整数值。</span><span class="sxs-lookup"><span data-stu-id="8659d-104">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
 <span data-ttu-id="8659d-105">你可以避免使用具有完全限定的名称`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="8659d-105">You can avoid using fully qualified names with the `Imports` statement.</span></span> <span data-ttu-id="8659d-106">有关详细信息，请参阅[枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)。</span><span class="sxs-lookup"><span data-stu-id="8659d-106">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-refer-to-an-enumeration-member"></a><span data-ttu-id="8659d-107">若要引用枚举成员</span><span class="sxs-lookup"><span data-stu-id="8659d-107">To refer to an enumeration member</span></span>  
  
-   <span data-ttu-id="8659d-108">有资格使用枚举的成员名称。</span><span class="sxs-lookup"><span data-stu-id="8659d-108">Qualify the member name with the enumeration.</span></span> <span data-ttu-id="8659d-109">例如，下面的示例将分配`Saturday`的成员`FirstDayOfWeek`给该变量的枚举`DayValue`。</span><span class="sxs-lookup"><span data-stu-id="8659d-109">For example, the following example assigns the `Saturday` member of the `FirstDayOfWeek` enumeration to the variable `DayValue`.</span></span>  
  
     [!code-vb[VbEnumsTask#19](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-refer-to-an-enumeration-member_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8659d-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="8659d-110">See also</span></span>
- [<span data-ttu-id="8659d-111">如何：声明枚举</span><span class="sxs-lookup"><span data-stu-id="8659d-111">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="8659d-112">枚举和名称限定</span><span class="sxs-lookup"><span data-stu-id="8659d-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="8659d-113">如何：循环访问在 Visual Basic 中枚举</span><span class="sxs-lookup"><span data-stu-id="8659d-113">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="8659d-114">如何：确定与枚举值关联的字符串</span><span class="sxs-lookup"><span data-stu-id="8659d-114">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="8659d-115">何时使用枚举</span><span class="sxs-lookup"><span data-stu-id="8659d-115">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
