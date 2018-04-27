---
title: 何时使用枚举 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5ab152687f4f9e4ba6bd032ae7c1352f65af715f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="when-to-use-an-enumeration-visual-basic"></a>何时使用枚举 (Visual Basic)
枚举提供轻松使用成组的相关的常数。 一个枚举，枚举，或`Enum`，是一组值的符号名称。 枚举将被视为数据类型，并可用于创建使用变量和属性集使用的常数。  
  
## <a name="when-to-use-an-enumeration"></a>何时使用枚举  
 当一个过程接受一组有限的变量时，请考虑使用枚举。 枚举可使更清楚且更具可读性的代码，尤其是在使用有意义的名称时。  
  
 使用枚举的好处包括：  
  
-   这样可以减少错误引起的转置或键入数字。  
  
-   便于在以后更改值。  
  
-   使代码易于阅读，这意味着它很少出现错误的概率到其中。  
  
-   确保向前兼容性。 枚举，与你的代码就很难如果有人在将来更改成员名称所对应的值失败。  
  
## <a name="naming-enumerations"></a>命名枚举  
 用于枚举成员的命名约定。 当 Visual Basic 遇到枚举成员名称时，如果其他引用的类型库包含相同的名称，可能会引发异常。 使用标识你的应用程序或组件中的值的唯一前缀。  
  
 当引用时枚举的成员，你必须限定枚举名称的成员名称，否则使用`Imports`语句。 有关详细信息，请参阅[枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)。  
  
## <a name="predefined-enumerations"></a>预定义的枚举  
 Visual Basic 提供了大量预定义的枚举，如`FirstDayOfWeek`和`MsgBoxResult`，以便于你的代码。 有关这些列表请参阅[常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md)。  
  
## <a name="see-also"></a>请参阅  
 [如何： 声明枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [如何：引用枚举成员](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [如何： 循环访问 Visual Basic 中的一个枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [如何：确定与枚举值关联的字符串](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [Enum 语句](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md)
