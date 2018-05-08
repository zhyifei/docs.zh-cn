---
title: Resume 语句
ms.date: 07/20/2015
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
ms.openlocfilehash: 1d03f631893be51529f29af824de0d684bf43804
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
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
 必须的。 如果错误发生的错误处理程序相同的过程中，将导致错误的语句处继续执行。 如果在调用过程中出错，请在上一次调用不包含错误处理例程的过程的语句处继续执行。  
  
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
  
## <a name="see-also"></a>请参阅  
 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Error 语句](../../../visual-basic/language-reference/statements/error-statement.md)  
 [On Error 语句](../../../visual-basic/language-reference/statements/on-error-statement.md)
