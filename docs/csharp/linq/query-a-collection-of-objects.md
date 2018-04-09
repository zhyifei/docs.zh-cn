---
title: 查询对象的集合
description: 如何查询集合。
keywords: .NET、.NET Core、C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: a62e5c6324d15376f1b42ad078eeb883b05ef14f
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="query-a-collection-of-objects"></a>查询对象的集合
此示例演示如何对一系列 `Student` 对象执行简单查询。 每个 `Student` 对象均包含一些关于学生的基本信息和表示学生在四门考试中的分数的列表。  
  
 该应用程序充当本部分中使用相同 `students` 数据源的许多其他示例的框架。  
  
## <a name="example"></a>示例  
 以下查询将返回在第一堂考试中得分为 90 或更高的学生。  
  
 [!code-csharp[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
 该查询有意简单，以使你可以进行实验。 例如，你可以在 `where` 子句中尝试其他条件或使用 `orderby` 子句对结果进行排序。  
  

## <a name="see-also"></a>请参阅  
 [LINQ 查询表达式](index.md)  
 [字符串内插](../language-reference/tokens/interpolated.md)
