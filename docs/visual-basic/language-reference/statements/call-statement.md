---
title: Call 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: af0b62d6cfacbcf94f527e049e07e51bf496a6cf
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392763"
---
# <a name="call-statement-visual-basic"></a>Call 语句 (Visual Basic)

将控制转移到 `Function`、@no__t 1 或动态链接库（DLL）过程。

## <a name="syntax"></a>语法

```vb
[ Call ] procedureName [ (argumentList) ]
```

## <a name="parts"></a>部件

|||
|---|---|
|`procedureName`|必需。 要调用的过程的名称。|
|`argumentList`|可选。 表示在调用过程时传递给过程的参数的变量或表达式列表。 多个参数之间用逗号分隔。 如果包含 `argumentList`，则必须将其括在括号中。|
|||
  
## <a name="remarks"></a>备注

 在调用过程时，可以使用 @no__t 关键字。 对于大多数过程调用，不需要使用此关键字。

 当被调用的表达式不是以标识符开头时，通常使用 `Call` 关键字。 不建议将 @no__t 关键字用于其他用途。

 如果过程返回值，则 `Call` 语句将其丢弃。

## <a name="example"></a>示例

 下面的代码演示了两个示例，其中 `Call` 关键字是调用过程所必需的。 在这两个示例中，调用的表达式不以标识符开头。

 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a>请参阅

- [Function 语句](function-statement.md)
- [Sub 语句](sub-statement.md)
- [Declare 语句](declare-statement.md)
- [Lambda 表达式](../../programming-guide/language-features/procedures/lambda-expressions.md)
