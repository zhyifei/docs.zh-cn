---
title: "如何：验证表示日期或时间的字符串 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ed3201ef2bbef97eebbafa5ef128ca015adac013
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="5ddbd-102">如何：验证表示日期或时间的字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ddbd-102">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>
<span data-ttu-id="5ddbd-103">下面的代码示例设置`Boolean`值，该值指示字符串是否表示有效的日期或时间。</span><span class="sxs-lookup"><span data-stu-id="5ddbd-103">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ddbd-104">示例</span><span class="sxs-lookup"><span data-stu-id="5ddbd-104">Example</span></span>  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-strings-that-represent-dates-or-times_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5ddbd-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="5ddbd-105">Compiling the Code</span></span>  
 <span data-ttu-id="5ddbd-106">替换`("01/01/03")`和`"9:30 PM"`包含的日期和你想要验证的时间。</span><span class="sxs-lookup"><span data-stu-id="5ddbd-106">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="5ddbd-107">你可以将另一个硬编码字符串的字符串替换`String`变量，或的方法，返回一个字符串，如`InputBox`。</span><span class="sxs-lookup"><span data-stu-id="5ddbd-107">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="5ddbd-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="5ddbd-108">Robust Programming</span></span>  
 <span data-ttu-id="5ddbd-109">使用此方法尝试将转换之前验证字符串`String`到`DateTime`变量。</span><span class="sxs-lookup"><span data-stu-id="5ddbd-109">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="5ddbd-110">通过首先检查日期或时间，可以避免生成在运行时异常。</span><span class="sxs-lookup"><span data-stu-id="5ddbd-110">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ddbd-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ddbd-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Information.IsDate%2A>  
 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>  
 [<span data-ttu-id="5ddbd-112">在 Visual Basic 中验证字符串</span><span class="sxs-lookup"><span data-stu-id="5ddbd-112">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
