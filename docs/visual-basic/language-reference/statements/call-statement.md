---
title: "Call 语句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c72450fd6f931f36f640d3e384a6fd38d57a7a23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="call-statement-visual-basic"></a>Call 语句 (Visual Basic)
将传输到的控件`Function`， `Sub`，或动态链接库 (DLL) 过程。  
  
## <a name="syntax"></a>语法  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a>部件  
 `procedureName`  
 必需。 要调用的过程的名称。  
  
 `argumentList`  
 可选。 变量或表达式表示被调用时传递给过程的自变量列表。 用逗号分隔多个自变量。 如果包含`argumentList`，必须将它括在括号中。  
  
## <a name="remarks"></a>备注  
 你可以使用`Call`关键字调用过程时。 对于大多数过程调用中，你不需要使用此关键字。  
  
 通常使用`Call`关键字时调用的表达式不能启动标识符与。 利用`Call`用于其他用途的关键字，则不建议。  
  
 如果该过程返回一个值，`Call`语句将放弃它。  
  
## <a name="example"></a>示例  
 下面的代码演示两个示例其中`Call`关键字是必需调用过程。 在这两个示例中，调用的表达式不能启动标识符与。  
  
 [!code-vb[VbVbalrStatements#97](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/call-statement_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
