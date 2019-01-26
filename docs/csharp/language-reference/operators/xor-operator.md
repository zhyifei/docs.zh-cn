---
title: ^ 运算符 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^_CSharpKeyword
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
ms.openlocfilehash: 152be2d81d1bf340b839d74f169d63d7260f7ca5
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333702"
---
# <a name="-operator-c-reference"></a>^ 运算符（C# 参考）

针对整型类型和 `bool` 预定义了二元 `^` 运算符。 对于整型类型，`^` 会计算其操作数的按位异或。 对于 `bool` 操作数，`^` 计算其操作数的逻辑异或；即，当且仅当其一个操作数为 `true` 时，结果才为 `true`。

## <a name="remarks"></a>备注

用户定义的类型可以重载 `^` 运算符（请参阅[运算符](../keywords/operator.md)）。 对整数类型的操作通常可用于枚举。

## <a name="example"></a>示例

[!code-csharp[csRefOperators#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#30)]

上一示例中的 `0xf8 ^ 0x3f` 计算执行了以下两个二进制值的按位异或，这与十六进制值 F8 和 3F 对应：

`1111 1000`

`0011 1111`

异或的结果是 `1100 0111`，即十六进制中的 C7。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 运算符](index.md)
