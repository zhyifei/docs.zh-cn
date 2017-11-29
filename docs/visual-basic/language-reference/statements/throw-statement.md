---
title: "Throw 语句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 50ada551c32b8296f0dad2ae929ca9c81a14a711
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="throw-statement-visual-basic"></a>Throw 语句 (Visual Basic)
引发过程中的异常。  
  
## <a name="syntax"></a>语法  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a>部件  
 `expression`  
 提供有关要引发的异常信息。 可选时驻留在`Catch`语句，否则为必选项。  
  
## <a name="remarks"></a>备注  
 `Throw`语句将引发异常，你可以处理与结构化异常处理代码 (`Try`...`Catch`...`Finally`) 或非结构化的异常处理代码 (`On Error GoTo`)。 你可以使用`Throw`语句来捕获代码中的错误，因为 Visual Basic 移动在调用堆栈中向上，直到它找到相应的异常处理代码。  
  
 A`Throw`不使用表达式的语句仅可在`Catch`语句，这种情况下该语句会再次引发当前处理的异常`Catch`语句。  
  
 `Throw`语句重置的调用堆栈`expression`异常。 如果`expression`未提供，调用堆栈保留不变。 你可以访问通过异常的调用堆栈<xref:System.Exception.StackTrace%2A>属性。  
  
## <a name="example"></a>示例  
 下面的代码使用`Throw`引发异常的语句：  
  
 [!code-vb[VbVbalrStatements#84](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/throw-statement_1.vb)]  
  
## <a name="requirements"></a>要求  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **模块：**`Interaction`  
  
 **程序集：** Visual Basic 运行库 （在 Microsoft.VisualBasic.dll 中)  
  
## <a name="see-also"></a>另请参阅  
 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [On Error 语句](../../../visual-basic/language-reference/statements/on-error-statement.md)
