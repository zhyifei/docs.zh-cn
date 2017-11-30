---
title: "如何：引用枚举成员 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ae4e6eb9c011095c6cf0abe1ee3ac7a68f156f01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a><span data-ttu-id="07421-102">如何：引用枚举成员 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07421-102">How to: Refer to an Enumeration Member (Visual Basic)</span></span>
<span data-ttu-id="07421-103">枚举提供一种简便方式，以使用集相关的常数的并将与名称关联常量值。</span><span class="sxs-lookup"><span data-stu-id="07421-103">Enumerations provide a convenient way to work with sets of related constants and to associate constant values with names.</span></span> <span data-ttu-id="07421-104">例如，可以为一组与星期几相关联的整数常量声明一个枚举，然后在代码中使用星期几的名称而不是整数值。</span><span class="sxs-lookup"><span data-stu-id="07421-104">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
 <span data-ttu-id="07421-105">你可以避免使用具有完全限定的名称`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="07421-105">You can avoid using fully qualified names with the `Imports` statement.</span></span> <span data-ttu-id="07421-106">有关详细信息，请参阅[枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)。</span><span class="sxs-lookup"><span data-stu-id="07421-106">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-refer-to-an-enumeration-member"></a><span data-ttu-id="07421-107">若要引用枚举成员</span><span class="sxs-lookup"><span data-stu-id="07421-107">To refer to an enumeration member</span></span>  
  
-   <span data-ttu-id="07421-108">限定枚举成员名称。</span><span class="sxs-lookup"><span data-stu-id="07421-108">Qualify the member name with the enumeration.</span></span> <span data-ttu-id="07421-109">例如，下面的示例将`Saturday`的成员`FirstDayOfWeek`枚举变量`DayValue`。</span><span class="sxs-lookup"><span data-stu-id="07421-109">For example, the following example assigns the `Saturday` member of the `FirstDayOfWeek` enumeration to the variable `DayValue`.</span></span>  
  
     [!code-vb[VbEnumsTask#19](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-refer-to-an-enumeration-member_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="07421-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07421-110">See Also</span></span>  
 [<span data-ttu-id="07421-111">如何： 声明枚举</span><span class="sxs-lookup"><span data-stu-id="07421-111">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="07421-112">枚举和名称限定</span><span class="sxs-lookup"><span data-stu-id="07421-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="07421-113">如何： 循环访问 Visual Basic 中的一个枚举</span><span class="sxs-lookup"><span data-stu-id="07421-113">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="07421-114">如何：确定与枚举值关联的字符串</span><span class="sxs-lookup"><span data-stu-id="07421-114">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="07421-115">何时使用枚举</span><span class="sxs-lookup"><span data-stu-id="07421-115">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
