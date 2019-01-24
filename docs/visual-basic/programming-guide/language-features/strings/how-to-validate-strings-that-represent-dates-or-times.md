---
title: 如何：验证表示日期或时间的字符串 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 1a838d9d156ad9c05a70a4d4d72db1a288731c9b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685394"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="0fa6f-102">如何：验证表示日期或时间的字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0fa6f-102">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>
<span data-ttu-id="0fa6f-103">下面的代码示例设置`Boolean`值，该值指示字符串是否表示有效的日期或时间。</span><span class="sxs-lookup"><span data-stu-id="0fa6f-103">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fa6f-104">示例</span><span class="sxs-lookup"><span data-stu-id="0fa6f-104">Example</span></span>  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-strings-that-represent-dates-or-times_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0fa6f-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="0fa6f-105">Compiling the Code</span></span>  
 <span data-ttu-id="0fa6f-106">替换`("01/01/03")`和`"9:30 PM"`使用日期和你想要验证的时间。</span><span class="sxs-lookup"><span data-stu-id="0fa6f-106">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="0fa6f-107">您可以将使用另一个硬编码字符串、 字符串替换为`String`变量，或使用一种方法，返回一个字符串，如`InputBox`。</span><span class="sxs-lookup"><span data-stu-id="0fa6f-107">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0fa6f-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="0fa6f-108">Robust Programming</span></span>  
 <span data-ttu-id="0fa6f-109">使用此方法尝试转换之前验证字符串`String`到`DateTime`变量。</span><span class="sxs-lookup"><span data-stu-id="0fa6f-109">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="0fa6f-110">通过首先检查包含日期或时间，可以避免生成在运行时异常。</span><span class="sxs-lookup"><span data-stu-id="0fa6f-110">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fa6f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fa6f-111">See also</span></span>
- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [<span data-ttu-id="0fa6f-112">在 Visual Basic 中验证字符串</span><span class="sxs-lookup"><span data-stu-id="0fa6f-112">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
