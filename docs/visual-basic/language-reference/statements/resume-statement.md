---
title: "Resume 语句"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Resume
- vb.ResumeNext
helpviewer_keywords:
- Next statement [Visual Basic], Resume
- Resume Next statement [Visual Basic]
- execution [Visual Basic], resuming
- run-time errors [Visual Basic], resuming after
- Resume statement [Visual Basic], syntax
- errors [Visual Basic], resuming after
- Error statement [Visual Basic], and Resume statement
- execution
- Resume statement [Visual Basic]
ms.assetid: e24d058b-1a5c-4274-acb9-7d295d3ea537
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3cb4334f302c07c81b6b8a7d0626be08cc69b1ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="resume-statement"></a>Resume 语句
错误处理例程完毕后恢复执行。  
  
 我们建议你使用结构化的异常处理，只要有可能，在代码中，而不是无需使用非结构化的异常处理和`On Error`和`Resume`语句。 有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。  
  
## <a name="syntax"></a>语法  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a>部件  
 `Resume`  
 必需。 如果错误发生的错误处理程序相同的过程中，将导致错误的语句处继续执行。 如果在调用过程中出错，请在上一次调用不包含错误处理例程的过程的语句处继续执行。  
  
 `Next`  
 可选。 如果在错误处理程序相同的过程中出错，请将紧跟导致错误的语句的语句处继续执行。 如果在调用过程中出错，请紧随上一次调用不包含错误处理例程的过程的语句处继续执行 (或`On Error Resume Next`语句)。  
  
 `line`  
 可选。 指定所需的代码行处继续执行`line`自变量。 `line`自变量是行标签或行号，并且必须在同一过程中的错误处理程序。  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  我们建议你使用结构化的异常处理，只要有可能，在代码中，而不是无需使用非结构化的异常处理和`On Error`和`Resume`语句。 有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。  
  
 如果你使用`Resume`语句中任意位置以外的其他错误处理例程中，将会出错。  
  
 `Resume`语句不能包含任何过程在`Try...Catch...Finally`语句。  
  
## <a name="example"></a>示例  
 此示例使用`Resume`语句来结束的错误处理过程中，然后继续执行导致错误的语句。 错误号 55 生成来演示使用`Resume`语句。  
  
 [!code-vb[VbVbalrErrorHandling#16](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/resume-statement_1.vb)]  
  
## <a name="requirements"></a>要求  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **程序集：** Visual Basic 运行库 （在 Microsoft.VisualBasic.dll 中)  
  
## <a name="see-also"></a>另请参阅  
 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Error 语句](../../../visual-basic/language-reference/statements/error-statement.md)  
 [On Error 语句](../../../visual-basic/language-reference/statements/on-error-statement.md)
