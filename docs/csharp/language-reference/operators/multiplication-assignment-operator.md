---
title: '*= 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 2038f3b55d46f3503496275b3d25b17663b8c1db
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333429"
---
# <a name="-operator-c-reference"></a>\*= 运算符（C# 参考）

二进制乘法赋值运算符。

## <a name="remarks"></a>备注

使用 `*=` 赋值运算符的表达式，如

```csharp
x *= y
```

等效于

```csharp
x = x * y
```

不同的是 `x` 只计算一次。 针对数值类型预定义了 [\* 运算符](multiplication-operator.md)以进行乘法运算。

不能直接重载 `*=` 运算符，但用户定义的类型可重载 [\* 运算符](multiplication-operator.md)（参阅[运算符](../keywords/operator.md)）。

## <a name="example"></a>示例

[!code-csharp[csRefOperators#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#13)]

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 运算符](index.md)
