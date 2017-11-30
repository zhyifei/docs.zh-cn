---
title: "如何：控制变量的可用性 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- access levels, declared elements
- Private keyword [Visual Basic], accessing variables
- access levels, variables
- Public keyword [Visual Basic], accessing variables
- Friend keyword [Visual Basic], accessing variables
- variables [Visual Basic], access level
- declared elements [Visual Basic], access level
- Protected keyword [Visual Basic], accessing variables
ms.assetid: eaf4f073-7922-43ce-ae1e-90ff376ae947
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 004fb101661fadeaee084e1f9374ca8332ac7234
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a>如何：控制变量的可用性 (Visual Basic)
通过指定控制变量的可用性其*访问级别*。 访问级别确定哪些代码有权读取或写入到该变量。  
  
-   *成员变量*（定义在模块级别和任何过程之外） 默认为公共访问，这意味着任何代码都可以查看它们可以访问它们。 可以通过指定访问修饰符来更改这种情况。  
  
-   *本地变量*（定义在过程内） 名义上具有公共访问，但只有其过程中的代码可以访问它们。 不能更改访问级别的本地变量，但你可以更改的过程的包含它的访问级别。  
  
 有关详细信息，请参阅[访问 Visual Basic 中的级别](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
## <a name="private-and-public-access"></a>私有和公共访问  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a>若要使变量只能在其模块、 类或结构内访问  
  
1.  位置[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)变量内模块、 类或结构，但在任何过程外部。  
  
2.  包括[私有](../../../../visual-basic/language-reference/modifiers/private.md)中的关键字`Dim`语句。  
  
     您可以读取或写入内任意位置模块、 类或结构，但不是能从变量之外。  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a>若要使变量可从任何可以看到它的代码访问  
  
1.  成员变量，将放置`Dim`内部模块、 类或结构，但在任何过程外部变量的语句。  
  
2.  包括[公共](../../../../visual-basic/language-reference/modifiers/public.md)中的关键字`Dim`语句。  
  
     您可以读取或从互操作的任何代码与您的程序集写入变量。  
  
 - 或 -  
  
1.  对于本地变量，请将`Dim`过程内的变量的语句。  
  
2.  不包括`Public`中的关键字`Dim`语句。  
  
     你可以读取或写入到任意位置在过程中，但不是能从变量之外。  
  
## <a name="protected-and-friend-access"></a>受保护和友元访问权限  
 你可以限制对其类和任何派生的类，或它的程序集的变量的访问级别。 你还可以指定这些限制，这将允许从代码访问任何派生类中或同一程序集中的任何其他位置中的联合。 通过组合中指定此联合`Protected`和`Friend`同一声明中的关键字。  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a>若要使变量只能从其类和任何派生的类中访问  
  
1.  位置`Dim`类的内部，但在任何过程外部变量的语句。  
  
2.  包括[受保护](../../../../visual-basic/language-reference/modifiers/protected.md)中的关键字`Dim`语句。  
  
     您可以读取或写入的任何类派生，而不是从任意位置在类中，以及从变量派生链中的任何类的外部。  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a>若要使变量只能在同一程序集内访问  
  
1.  位置`Dim`内部模块、 类或结构，但在任何过程外部变量的语句。  
  
2.  包括[友元](../../../../visual-basic/language-reference/modifiers/friend.md)中的关键字`Dim`语句。  
  
     你可以读取或写入到任意位置内模块、 类或结构，以及从同一程序集中，但不是能从任何代码从变量程序集外部的。  
  
## <a name="example"></a>示例  
 下面的示例演示使用的变量的声明`Public`， `Protected`， `Friend`， `Protected Friend`，和`Private`访问级别。 请注意，当`Dim`语句指定访问级别，您不需要包括`Dim`关键字。  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 限制性更强的变量的访问级别，它的使用变量越小的恶意代码可以不正确的机会。  
  
## <a name="see-also"></a>另请参阅  
 [在 Visual Basic 中的访问级别](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Public](../../../../visual-basic/language-reference/modifiers/public.md)  
 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)  
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)  
 [Private](../../../../visual-basic/language-reference/modifiers/private.md)
