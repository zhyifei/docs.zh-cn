---
title: 可选参数必须指定默认值
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: eb782b2fa1fb73c7407b57a0942e5eebb30474ff
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040927"
---
# <a name="optional-parameters-must-specify-a-default-value"></a>可选参数必须指定默认值

可选参数必须提供默认值，如果调用过程未提供任何参数，则可以使用这些默认值。

**错误 ID：** BC30812

## <a name="example"></a>示例

下面的示例生成 BC30812：

```vb
Sub Proc1(x As Integer, Optional y As String)
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="to-correct-this-error"></a>更正此错误

指定可选参数的默认值：

```vb
Sub Proc1(x As Integer, Optional y As String = "Default Value")
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="see-also"></a>请参阅

- [Optional](../modifiers/optional.md)
