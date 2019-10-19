---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 50d5a768393e90d28d150b451405e35e6f4c7953
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583043"
---
# <a name="withevents-visual-basic"></a>WithEvents (Visual Basic)
指定一个或多个已声明的成员变量引用可引发事件的类的实例。

## <a name="remarks"></a>备注

使用 `WithEvents` 定义变量时，可以通过声明方式指定方法使用 `Handles` 关键字来处理变量的事件。

只能在类或模块级别使用 `WithEvents`。 这意味着 `WithEvents` 变量的声明上下文必须是类或模块，不能是源文件、命名空间、结构或过程。

不能对结构成员使用 `WithEvents`。

您只能用 `WithEvents` 声明单个变量（而非数组）。

## <a name="rules"></a>规则

**元素类型。** 必须将 `WithEvents` 变量声明为对象变量，以便它们可以接受类实例。 但是，不能将它们声明为 `Object`。 您必须将它们声明为可引发事件的特定类。

@No__t_0 修饰符可以在此上下文中使用： [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)

## <a name="example"></a>示例

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a>请参阅

- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [关键字](../../../visual-basic/language-reference/keywords/index.md)
- [事件](../../../visual-basic/programming-guide/language-features/events/index.md)
