---
title: 对 join 子句的结果进行排序（C# 中的 LINQ）
description: 了解如何对 C# 中的 LINQ join 子句的结果进行排序。
ms.date: 12/1/2016
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: 13cd6cb202cf67def17310db6d98e368ce837646
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516981"
---
# <a name="order-the-results-of-a-join-clause"></a>对 join 子句的结果进行排序

此示例演示如何对联接运算的结果进行排序。 请注意，排序在联接之后执行。 虽然可以在联接之前将 `orderby` 子句用于一个或多个源序列，不过通常不建议这样做。 某些 LINQ 提供程序可能不会在联接之后保留该排序。

## <a name="example"></a>示例

此查询创建一个分组联接，然后基于类别元素（仍处于范围中）对组进行排序。 在匿名类型初始值设定项内，一个子查询对来自产品序列的所有匹配元素进行排序。

[!code-csharp[csProgGuideLINQ#81](~/samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]

## <a name="see-also"></a>请参阅

- [语言集成查询 (LINQ)](index.md)  
- [orderby 子句](../language-reference/keywords/orderby-clause.md)  
- [join 子句](../language-reference/keywords/join-clause.md)  