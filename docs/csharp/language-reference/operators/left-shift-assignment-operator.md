---
title: '&lt;&lt;= 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: 4513c4b78dea3e8102c72a43249b4a44ffa2421d
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333247"
---
# <a name="ltlt-operator-c-reference"></a>&lt;&lt;= 运算符（C# 参考）

左移赋值运算符。

## <a name="remarks"></a>备注

形式如下的表达式

```csharp
x <<= y
```

计算结果为

```csharp
x = x << y
```

不同的是 `x` 只计算一次。 [<< 运算符](left-shift-operator.md) 将 `x` 向左移动 `y` 指定的位数。

不能直接重载 `<<=` 运算符，但用户定义的类型可重载 [<< 运算符](left-shift-operator.md)（参阅[运算符](../keywords/operator.md)）。

## <a name="example"></a>示例

[!code-csharp[csRefOperators#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#12)]

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 运算符](index.md)
