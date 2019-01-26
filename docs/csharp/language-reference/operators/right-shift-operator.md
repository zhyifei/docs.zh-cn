---
title: '&gt;&gt; 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: 80e38d8e75b9ad573b635d544d6381950f107583
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333677"
---
# <a name="gtgt-operator-c-reference"></a>&gt;&gt; 运算符（C# 参考）

右移运算符 (`>>`) 将第一个操作数向右移动第二个操作数指定的位数。

## <a name="remarks"></a>备注

如果第一个操作数是 [int](../keywords/int.md) 或 [uint](../keywords/uint.md)（32 位数），则移位计数由第二个操作数的低序五位给定（第二个操作数 & 0x1f）。

如果第一个操作数是 [long](../keywords/long.md) 或 [ulong](../keywords/ulong.md)（64 位数），则移位计数由第二个操作数的低序六位给定（第二个操作数 & 0x3f）。

如果第一个操作数是 [int](../keywords/int.md) 或 [long](../keywords/long.md)，则右移是一种算术移位（高阶空位设置为符号位）。 如果第一个操作数的类型为 [uint](../keywords/uint.md) 或 [ulong](../keywords/ulong.md)，则右移是一种逻辑移位（高序位补零）。

用户定义的类型可以重载 `>>` 运算符；第一个操作数的类型必须是用户定义的类型，第二个操作数的类型必须是 [int](../keywords/int.md)。有关详细信息，请参阅[运算符](../keywords/operator.md)。 重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。

## <a name="example"></a>示例

[!code-csharp[csRefOperators#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#26)]

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 运算符](index.md)