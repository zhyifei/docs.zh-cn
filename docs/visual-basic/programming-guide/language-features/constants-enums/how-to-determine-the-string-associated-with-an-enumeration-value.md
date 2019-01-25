---
title: 如何：确定与枚举值 (Visual Basic 中) 关联的字符串
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 92d2e9918429c9cf408f288f832e4615b95ad423
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690184"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a><span data-ttu-id="343cf-102">如何：确定与枚举值 (Visual Basic 中) 关联的字符串</span><span class="sxs-lookup"><span data-stu-id="343cf-102">How to: Determine the String Associated with an Enumeration Value (Visual Basic)</span></span>
<span data-ttu-id="343cf-103"><xref:System.Enum.GetValues%2A>和<xref:System.Enum.GetNames%2A>方法可用于确定字符串和枚举成员与相关联的值。</span><span class="sxs-lookup"><span data-stu-id="343cf-103">The <xref:System.Enum.GetValues%2A> and <xref:System.Enum.GetNames%2A> methods allow you to determine the strings and values associated with enumeration members.</span></span>  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a><span data-ttu-id="343cf-104">若要确定与枚举关联的字符串</span><span class="sxs-lookup"><span data-stu-id="343cf-104">To determine the string associated with an enumeration</span></span>  
  
-   <span data-ttu-id="343cf-105">使用<xref:System.Enum.GetNames%2A>方法来检索与枚举成员关联的字符串。</span><span class="sxs-lookup"><span data-stu-id="343cf-105">Use the <xref:System.Enum.GetNames%2A> method to retrieve the strings associated with the enumeration members.</span></span> <span data-ttu-id="343cf-106">此示例中声明枚举，这`flavorEnum`，然后使用<xref:System.Enum.GetNames%2A>方法来显示与每个成员关联的字符串。</span><span class="sxs-lookup"><span data-stu-id="343cf-106">This example declares an enumeration, `flavorEnum`, then uses the <xref:System.Enum.GetNames%2A> method to display the strings associated with each member.</span></span>  
  
     [!code-vb[VbEnumsTask#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-determine-the-string-associated-with-an-enumeration-value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="343cf-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="343cf-107">See also</span></span>
- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [<span data-ttu-id="343cf-108">如何：声明枚举</span><span class="sxs-lookup"><span data-stu-id="343cf-108">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="343cf-109">如何：为枚举成员，请参阅</span><span class="sxs-lookup"><span data-stu-id="343cf-109">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="343cf-110">枚举和名称限定</span><span class="sxs-lookup"><span data-stu-id="343cf-110">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="343cf-111">如何：循环访问在 Visual Basic 中枚举</span><span class="sxs-lookup"><span data-stu-id="343cf-111">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="343cf-112">何时使用枚举</span><span class="sxs-lookup"><span data-stu-id="343cf-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="343cf-113">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="343cf-113">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
