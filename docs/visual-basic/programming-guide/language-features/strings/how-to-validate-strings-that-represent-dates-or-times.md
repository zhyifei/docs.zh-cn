---
title: 如何：验证表示日期或时间的字符串
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 34af6dffeb0d05eaeed38354f8007554b60e91b0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344346"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="49316-102">如何：验证表示日期或时间的字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49316-102">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>
<span data-ttu-id="49316-103">下面的代码示例设置 `Boolean` 值，该值指示字符串是否表示有效的日期或时间。</span><span class="sxs-lookup"><span data-stu-id="49316-103">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49316-104">示例</span><span class="sxs-lookup"><span data-stu-id="49316-104">Example</span></span>  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="49316-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="49316-105">Compiling the Code</span></span>  
 <span data-ttu-id="49316-106">将 `("01/01/03")` 和 `"9:30 PM"` 替换为要验证的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="49316-106">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="49316-107">你可以将字符串替换为带有 `String` 变量的另一个硬编码字符串，或者替换为返回字符串的方法，如 `InputBox`。</span><span class="sxs-lookup"><span data-stu-id="49316-107">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="49316-108">可靠的编程</span><span class="sxs-lookup"><span data-stu-id="49316-108">Robust Programming</span></span>  
 <span data-ttu-id="49316-109">使用此方法在尝试将 `String` 转换为 `DateTime` 变量之前验证字符串。</span><span class="sxs-lookup"><span data-stu-id="49316-109">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="49316-110">首先检查日期或时间，您可以避免在运行时生成异常。</span><span class="sxs-lookup"><span data-stu-id="49316-110">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49316-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49316-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [<span data-ttu-id="49316-112">在 Visual Basic 中验证字符串</span><span class="sxs-lookup"><span data-stu-id="49316-112">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
