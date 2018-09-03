---
title: global 上下文关键字（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- global
- global_CSharpKeyword
helpviewer_keywords:
- global keyword [C#]
ms.assetid: 8932c16a-6959-42c2-86e7-2c4221ab788b
ms.openlocfilehash: 837245e31a9a795aa2f13cfc6c33fefb6402801d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43401069"
---
# <a name="global-c-reference"></a>global（C# 参考）

`global` 上下文关键字位于 [:: 运算符](../operators/namespace-alias-qualifer.md) 之前时引用全局命名空间（即任何 C# 程序的默认命名空间，否则其未被命名）。 有关详细信息，请参阅[如何：使用全局命名空间别名](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)。

## <a name="example"></a>示例

如下示例演示如何使用 `global` 上下文关键字来指定在全局命名空间中定义类 `TestApp`：

[!code-csharp[csrefKeywordsContextual#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#13)]

## <a name="see-also"></a>请参阅

- [命名空间](../../programming-guide/namespaces/index.md)