---
title: IsNot 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 32e8f9532244679d2994b0e3d98279d75f7e77b4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701035"
---
# <a name="isnot-operator-visual-basic"></a>IsNot 运算符 (Visual Basic)

比较两个对象引用变量。

## <a name="syntax"></a>语法

```vb
result = object1 IsNot object2
```

## <a name="parts"></a>部件
 `result`（必需）。 一个 `Boolean` 值。

 `object1`（必需）。 任何 @no__t 的变量或表达式。

 `object2`（必需）。 任何 @no__t 的变量或表达式。

## <a name="remarks"></a>备注
 @No__t-0 运算符确定两个对象引用是否引用不同的对象。 但是，它不会执行值比较。 如果 @no__t 0 和 `object2` 都引用完全相同的对象实例，`result` 为 `False`;否则，`result` `True`。

 @no__t 为 `Is` 运算符。 @No__t-0 的优点是你可以避免使用 `Not` 和 `Is` 的语法，这可能会很难阅读。

 您可以使用 @no__t 0 和 `IsNot` 运算符来测试早期绑定对象和后期绑定对象。

## <a name="example"></a>示例
 下面的代码示例使用 `Is` 运算符和 `IsNot` 运算符来完成相同的比较。

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a>请参阅

- [Is 运算符](is-operator.md)
- [TypeOf 运算符](typeof-operator.md)
- [Visual Basic 中的运算符优先级](operator-precedence.md)
- [如何：测试两个对象是否相同 @ no__t-0
