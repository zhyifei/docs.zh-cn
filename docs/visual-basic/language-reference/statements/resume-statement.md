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
ms.openlocfilehash: 95137a9f6a4a4a18655b51b95300bfaf93cca193
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333032"
---
# <a name="resume-statement"></a>Resume 语句
完成错误处理例程后，继续执行。  
  
 建议尽可能地在代码中使用结构化异常处理，而不是使用非结构化异常处理和 `On Error` 和 `Resume` 语句。 有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。  
  
## <a name="syntax"></a>语法  
  
```vb  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a>部件  
 `Resume`  
 必需。 如果错误发生在与错误处理程序相同的过程中，则执行将继续执行导致错误的语句。 如果错误发生在调用的过程中，则执行将在最近从包含错误处理例程的过程中调用的语句处继续。  
  
 `Next`  
 可选。 如果错误发生在与错误处理程序相同的过程中，则执行将继续执行导致错误的语句之后的语句。 如果在被调用的过程中发生错误，则继续执行，并在最后调用包含错误处理例程（或 `On Error Resume Next` 语句）的过程后的语句之后的语句之后继续执行。  
  
 `line`  
 可选。 执行在所需 `line` 参数中指定的行处恢复。 `line` 参数是行标签或行号，必须与错误处理程序位于同一过程中。  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 建议尽可能地在代码中使用结构化异常处理，而不是使用非结构化异常处理和 `On Error` 和 `Resume` 语句。 有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。  
  
 如果在错误处理例程中的任意位置使用 `Resume` 语句，则会发生错误。  
  
 不能在包含 `Try...Catch...Finally` 语句的任何过程中使用 `Resume` 语句。  
  
## <a name="example"></a>示例  
 此示例使用 `Resume` 语句来结束过程中的错误处理，然后使用导致错误的语句继续执行。 生成错误号55以说明 `Resume` 语句的使用。  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a>要求  
 **命名空间：** [Microsoft](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **程序集：** Visual Basic 运行时库（在 Microsoft. .dll 中）  
  
## <a name="see-also"></a>另请参阅

- [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Error 语句](../../../visual-basic/language-reference/statements/error-statement.md)
- [On Error 语句](../../../visual-basic/language-reference/statements/on-error-statement.md)
