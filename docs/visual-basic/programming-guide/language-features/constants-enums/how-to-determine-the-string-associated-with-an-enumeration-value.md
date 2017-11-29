---
title: "如何：确定与枚举值关联的字符串 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 01e2b0cfa6b1e426b38198581c7d493c8907b79b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a><span data-ttu-id="5dc88-102">如何：确定与枚举值关联的字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5dc88-102">How to: Determine the String Associated with an Enumeration Value (Visual Basic)</span></span>
<span data-ttu-id="5dc88-103"><xref:System.Enum.GetValues%2A>和<xref:System.Enum.GetNames%2A>方法可用于确定字符串和与枚举成员关联的值。</span><span class="sxs-lookup"><span data-stu-id="5dc88-103">The <xref:System.Enum.GetValues%2A> and <xref:System.Enum.GetNames%2A> methods allow you to determine the strings and values associated with enumeration members.</span></span>  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a><span data-ttu-id="5dc88-104">若要确定与枚举关联的字符串</span><span class="sxs-lookup"><span data-stu-id="5dc88-104">To determine the string associated with an enumeration</span></span>  
  
-   <span data-ttu-id="5dc88-105">使用<xref:System.Enum.GetNames%2A>方法来检索与枚举成员关联的字符串。</span><span class="sxs-lookup"><span data-stu-id="5dc88-105">Use the <xref:System.Enum.GetNames%2A> method to retrieve the strings associated with the enumeration members.</span></span> <span data-ttu-id="5dc88-106">此示例声明枚举， `flavorEnum`，然后使用<xref:System.Enum.GetNames%2A>方法以显示与每个成员关联的字符串。</span><span class="sxs-lookup"><span data-stu-id="5dc88-106">This example declares an enumeration, `flavorEnum`, then uses the <xref:System.Enum.GetNames%2A> method to display the strings associated with each member.</span></span>  
  
     [!code-vb[VbEnumsTask#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-determine-the-string-associated-with-an-enumeration-value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5dc88-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5dc88-107">See Also</span></span>  
 <xref:System.Enum.GetValues%2A>  
 <xref:System.Enum.GetNames%2A>  
 <xref:System.Enum>  
 [<span data-ttu-id="5dc88-108">如何： 声明枚举</span><span class="sxs-lookup"><span data-stu-id="5dc88-108">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="5dc88-109">如何：引用枚举成员</span><span class="sxs-lookup"><span data-stu-id="5dc88-109">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="5dc88-110">枚举和名称限定</span><span class="sxs-lookup"><span data-stu-id="5dc88-110">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="5dc88-111">如何： 循环访问 Visual Basic 中的一个枚举</span><span class="sxs-lookup"><span data-stu-id="5dc88-111">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="5dc88-112">何时使用枚举</span><span class="sxs-lookup"><span data-stu-id="5dc88-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="5dc88-113">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="5dc88-113">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
