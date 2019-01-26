---
title: '! 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- '! operator [C#]'
- logical negation operator (!) [C#]
- NOT operator [C#]
ms.assetid: f5ae133f-8f64-4560-b34f-cd9cd5eed4ad
ms.openlocfilehash: 6b6d1796032f536aac0be49d4f101c1380b4e98f
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333221"
---
# <a name="-operator-c-reference"></a>! 运算符（C# 参考）

逻辑非运算符 (`!`) 是一种否定其操作数的一元运算符。 它针对 `bool` 定义，当且仅当其操作数为 `false` 时返回 `true`。

## <a name="remarks"></a>备注

用户定义的类型可以重载 `!` 运算符（请参阅[运算符](../keywords/operator.md)）。

## <a name="example"></a>示例

[!code-csharp[csRefOperators#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#7)]

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 运算符](index.md)