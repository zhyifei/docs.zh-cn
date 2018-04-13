---
title: 验证密码复杂性 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bdbe5f385c6b7a0898c4907b0d8afabdaed06fa0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a>演练：验证密码是否复杂 (Visual Basic)
此方法检查某些强密码特征，并使用有关哪些检查密码失败的信息更新的字符串参数。  
  
 密码可以在一个安全系统，用于授权的用户。 但是，密码必须是难以猜测未经授权的用户。 攻击者可以使用*字典攻击*程序，它循环访问的所有单词在字典 （或在不同语言中的多个字典） 并测试是否有任何单词就是用户的密码。 可以快速猜到弱的密码，例如"杨基棒球队"或"Mustang"。 强密码，如"？你L1N3vaFiNdMeyeP@sSWerd！"，大大降低可能会被猜到。 受密码保护的系统应确保用户选择强密码。  
  
 强密码很复杂 （包含大写、 小写、 数字和特殊字符的组合），不是一个单词。 此示例演示如何验证复杂性。  
  
## <a name="example"></a>示例  
  
### <a name="code"></a>代码  
 [!code-vb[VbVbcnRegEx#1](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]  
  
## <a name="compiling-the-code"></a>编译代码  
 通过传递包含该密码的字符串调用此方法。  
  
 此示例需要：  
  
-   对 <xref:System.Text.RegularExpressions> 命名空间成员的访问权限。 如果未在代码中完全限定成员名称，则添加 `Imports` 语句。 有关详细信息，请参阅 [Imports 语句（.NET 命名空间和类型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)。  
  
## <a name="security"></a>安全性  
 如果在通过网络迁移密码，你需要使用安全的方法来传输数据。 有关详细信息，请参阅[ASP.NET Web 应用程序安全性](https://msdn.microsoft.com/library/330a99hc)。  
  
 你可以提高准确性`ValidatePassword`通过添加其他复杂性检查的函数：  
  
-   密码和对用户的名称、 用户标识符和应用程序定义的字典及其子字符串进行比较。 在执行比较时此外，将看上去很相似字符视为等效项。 例如，将字母"l"和"e"视为等效于数字"1"和"3"。  
  
-   如果只有一个大写字符，请确保它不是密码的第一个字符。  
  
-   请确保密码的最后两个字符的字母字符。  
  
-   不允许从键盘的首行输入所有符号的密码。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Text.RegularExpressions.Regex>  
 [ASP.NET Web 应用程序安全性](https://msdn.microsoft.com/library/330a99hc)
