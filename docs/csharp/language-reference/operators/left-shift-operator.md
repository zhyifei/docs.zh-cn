---
title: '&lt;&lt; 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: 79a48d88e2c83b5ad78804367ee3c07f78622c08
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333520"
---
# <a name="ltlt-operator-c-reference"></a>&lt;&lt; 运算符（C# 参考）

左移运算符 (`<<`) 将第一个操作数向左移动第二个操作数指定的位数。 第二个操作数的类型必须为 [int](../keywords/int.md) 或预定义隐式数值转换为 `int` 的类型。

## <a name="remarks"></a>备注

如果第一个操作数是 [int](../keywords/int.md) 或 [uint](../keywords/uint.md)（32 位数），则移位计数由第二个操作数的低序五位给定。 也就是说，实际的移位计数为 0 到 31 位。

如果第一个操作数是 [long](../keywords/long.md) 或 [ulong](../keywords/ulong.md)（64 位数），则移位计数由第二个操作数的低序六位给定。 也就是说，实际的移位计数为 0 到 63 位。

将丢弃移位后不在第一个操作数类型范围内的任何高序位，低序空位补零。 移位操作从不导致溢位。

用户定义的类型可以重载 `<<` 运算符（参阅[运算符](../keywords/operator.md)）；第一个操作数的类型必须是用户定义的类型，第二个操作数的类型必须是 `int`。 重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。

## <a name="example"></a>示例

[!code-csharp[csRefOperators#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#14)]

## <a name="comments"></a>注释

请注意，`i<<1` 和 `i<<33` 的结果相同，因为 1 和 33 的低序五位相同。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 运算符](index.md)
