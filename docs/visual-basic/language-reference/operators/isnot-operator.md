---
title: IsNot 运算符
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 616506f64d20e1f150b443433f1b69040136a5ba
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336065"
---
# <a name="isnot-operator-visual-basic"></a>IsNot 运算符 (Visual Basic)

比较两个对象引用变量。

## <a name="syntax"></a>语法

```vb
result = object1 IsNot object2
```

## <a name="parts"></a>部件
 `result`（必需）。 一个 `Boolean` 值。

 `object1`（必需）。 任何 `Object` 变量或表达式。

 `object2`（必需）。 任何 `Object` 变量或表达式。

## <a name="remarks"></a>备注
 `IsNot` 运算符确定两个对象引用是否引用不同的对象。 但是，它不会执行值比较。 如果 `object1` 和 `object2` 都引用完全相同的对象实例，则 `result` `False`;否则，将 `True``result`。

 `IsNot` 与 `Is` 运算符相反。 `IsNot` 的优势在于，您可以避免使用 `Not` 和 `Is`的语法，这可能很难阅读。

 您可以使用 `Is` 和 `IsNot` 运算符来测试早期绑定对象和后期绑定对象。

## <a name="example"></a>示例
 下面的代码示例使用 `Is` 运算符和 `IsNot` 运算符来完成相同的比较。

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a>另请参阅

- [Is 运算符](is-operator.md)
- [TypeOf 运算符](typeof-operator.md)
- [Visual Basic 中的运算符优先级](operator-precedence.md)
- [如何：测试两个对象是否相同](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
