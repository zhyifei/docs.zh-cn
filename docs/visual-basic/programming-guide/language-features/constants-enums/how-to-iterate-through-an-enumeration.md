---
title: 如何：在 Visual Basic 中循环访问枚举
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: 06609d38c805e5f073a2f3a299ecc3aa7cf7be01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646573"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a><span data-ttu-id="a77d0-102">如何：在 Visual Basic 中循环访问枚举</span><span class="sxs-lookup"><span data-stu-id="a77d0-102">How to: Iterate Through An Enumeration in Visual Basic</span></span>
<span data-ttu-id="a77d0-103">枚举提供了使用相关常量集以及将常量值与名称相关联的一个便捷方法。</span><span class="sxs-lookup"><span data-stu-id="a77d0-103">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="a77d0-104">若要循环枚举，你可以将其移到数组使用<xref:System.Enum.GetValues%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="a77d0-104">To iterate through an enumeration, you can move it into an array using the <xref:System.Enum.GetValues%2A> method.</span></span> <span data-ttu-id="a77d0-105">你还可以循环访问枚举使用`For...Each`语句中，使用<xref:System.Enum.GetNames%2A>或<xref:System.Enum.GetValues%2A>方法以提取的字符串或数值的值。</span><span class="sxs-lookup"><span data-stu-id="a77d0-105">You could also iterate through an enumeration using a `For...Each` statement, using the <xref:System.Enum.GetNames%2A> or <xref:System.Enum.GetValues%2A> method to extract the string or numeric value.</span></span>  
  
### <a name="to-iterate-through-an-enumeration"></a><span data-ttu-id="a77d0-106">若要循环访问枚举</span><span class="sxs-lookup"><span data-stu-id="a77d0-106">To iterate through an enumeration</span></span>  
  
-   <span data-ttu-id="a77d0-107">声明数组并将在枚举转换为其与<xref:System.Enum.GetValues%2A>然后再将数组传递作为你的方法将任何其他变量。</span><span class="sxs-lookup"><span data-stu-id="a77d0-107">Declare an array and convert the enumeration to it with the <xref:System.Enum.GetValues%2A> method before passing the array as you would any other variable.</span></span> <span data-ttu-id="a77d0-108">下面的示例显示在枚举每个成员<xref:Microsoft.VisualBasic.FirstDayOfWeek>如该示例循环访问枚举。</span><span class="sxs-lookup"><span data-stu-id="a77d0-108">The following example displays each member of the enumeration <xref:Microsoft.VisualBasic.FirstDayOfWeek> as it iterates through the enumeration.</span></span>  
  
     [!code-vb[VbEnumsTask#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-iterate-through-an-enumeration_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a77d0-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="a77d0-109">See Also</span></span>  
 [<span data-ttu-id="a77d0-110">枚举概述</span><span class="sxs-lookup"><span data-stu-id="a77d0-110">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [<span data-ttu-id="a77d0-111">如何： 声明枚举</span><span class="sxs-lookup"><span data-stu-id="a77d0-111">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="a77d0-112">何时使用枚举</span><span class="sxs-lookup"><span data-stu-id="a77d0-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="a77d0-113">如何：确定与枚举值关联的字符串</span><span class="sxs-lookup"><span data-stu-id="a77d0-113">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="a77d0-114">如何：引用枚举成员</span><span class="sxs-lookup"><span data-stu-id="a77d0-114">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="a77d0-115">枚举和名称限定</span><span class="sxs-lookup"><span data-stu-id="a77d0-115">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="a77d0-116">数组</span><span class="sxs-lookup"><span data-stu-id="a77d0-116">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
