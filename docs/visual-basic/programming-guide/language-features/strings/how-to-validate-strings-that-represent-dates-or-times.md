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
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>如何：验证表示日期或时间的字符串 (Visual Basic)
下面的代码示例设置`Boolean`值，该值指示字符串是否表示有效的日期或时间。  
  
## <a name="example"></a>示例  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-strings-that-represent-dates-or-times_1.vb)]  
  
## <a name="compiling-the-code"></a>编译代码  
 替换`("01/01/03")`和`"9:30 PM"`包含的日期和你想要验证的时间。 你可以将另一个硬编码字符串的字符串替换`String`变量，或的方法，返回一个字符串，如`InputBox`。  
  
## <a name="robust-programming"></a>可靠编程  
 使用此方法尝试将转换之前验证字符串`String`到`DateTime`变量。 通过首先检查日期或时间，可以避免生成在运行时异常。  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualBasic.Information.IsDate%2A>  
 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>  
 [在 Visual Basic 中验证字符串](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
