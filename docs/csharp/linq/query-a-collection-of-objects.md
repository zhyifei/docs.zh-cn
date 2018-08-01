---
title: 查询对象集合（C# 中的 LINQ）
description: 了解如何使用 C# 中的 LINQ 查询集合。
ms.date: 11/30/2016
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: 87c7bbe789c165a6e189231df1979fc264a34dce
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "37403916"
---
# <a name="query-a-collection-of-objects"></a>查询对象的集合

此示例演示如何对一系列 `Student` 对象执行简单查询。 每个 `Student` 对象均包含一些关于学生的基本信息和表示学生在四门考试中的分数的列表。  
  
该应用程序充当本部分中使用相同 `students` 数据源的许多其他示例的框架。  
  
## <a name="example"></a>示例

以下查询将返回在第一堂考试中得分为 90 或更高的学生。  
  
[!code-csharp[csProgGuideLINQ#15](~/samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
该查询有意简单，以使你可以进行实验。 例如，你可以在 `where` 子句中尝试其他条件或使用 `orderby` 子句对结果进行排序。  
  
## <a name="see-also"></a>请参阅

[语言集成查询 (LINQ)](index.md)  
[字符串内插](../language-reference/tokens/interpolated.md)