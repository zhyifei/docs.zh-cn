---
title: into - C# 参考
ms.date: 07/20/2015
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
ms.openlocfilehash: f0f5ff1e56a65e83385f814df2fadd957f53561e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713629"
---
# <a name="into-c-reference"></a>into（C# 参考）

可使用 `into` 上下文关键字创建临时标识符，将 [group](group-clause.md)、[join](join-clause.md) 或 [select](select-clause.md) 子句的结果存储至新标识符。 此标识符本身可以是附加查询命令的生成器。 有时称在 `group` 或 `select` 子句中使用新标识符为“延续”  。

## <a name="example"></a>示例

下面的示例演示使用 `into` 关键字来启用具有推断类型 `fruitGroup` 的临时标识符 `IGrouping`。 通过使用该标识符，可对每个组调用 <xref:System.Linq.Enumerable.Count%2A> 方法，并且仅选择那些包含两个或更多个单词的组。

[!code-csharp[cscsrefQueryKeywords#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Into.cs#18)]

仅当希望对每个组执行附加查询操作时，才需在 `into` 子句中使用 `group`。 有关详细信息，请参阅 [group 子句](group-clause.md)。

有关在 `into` 子句中使用 `join` 的示例，请参见 [join 子句](join-clause.md)。

## <a name="see-also"></a>另请参阅

- [查询关键字 (LINQ)](query-keywords.md)
- [C# 中的 LINQ](../../linq/index.md)
- [group 子句](group-clause.md)
