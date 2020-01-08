---
title: 如何：验证表示日期或时间的字符串
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 5321e7a85c45ddb6ce17433bd25ce9ca2165f0a3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348402"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>如何：验证表示日期或时间的字符串 (Visual Basic)
下面的代码示例设置 `Boolean` 值，该值指示字符串是否表示有效的日期或时间。  
  
## <a name="example"></a>示例  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compile-the-code"></a>编译代码  
 将 `("01/01/03")` 和 `"9:30 PM"` 替换为要验证的日期和时间。 你可以将字符串替换为带有 `String` 变量的另一个硬编码字符串，或者替换为返回字符串的方法，如 `InputBox`。  
  
## <a name="robust-programming"></a>可靠的编程  
 使用此方法在尝试将 `String` 转换为 `DateTime` 变量之前验证字符串。 首先检查日期或时间，您可以避免在运行时生成异常。  
  
## <a name="see-also"></a>另请参阅

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [在 Visual Basic 中验证字符串](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
