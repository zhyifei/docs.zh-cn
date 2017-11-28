---
title: "在查询表达式中处理 null 值"
description: "如何：在查询表达式中处理 null 值。"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: ac63ae8b-724d-4251-9334-528f4e884ae7
ms.openlocfilehash: d16256e31b073a599504ffef6501ed34430a7694
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="handle-null-values-in-query-expressions"></a>在查询表达式中处理 null 值

此示例显示如何在源集合中处理可能的 null 值。 <xref:System.Collections.Generic.IEnumerable%601> 等对象集合可包含值为 [null](../language-reference/keywords/null.md) 的元素。 如果源集合为 null 或包含值为 null 的元素，并且查询不处理 null 值，则在执行查询时将引发 <xref:System.NullReferenceException>。  
  
## <a name="example"></a>示例

 可采用防御方式进行编码，以避免空引用异常，如以下示例所示：  
  
 [!code-csharp[csProgGuideLINQ#82](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]  
  
 在前面的示例中，`where` 子句筛选出类别序列中的所有 null 元素。 此方法独立于 join 子句中的 null 检查。 在此示例中，带有 null 的条件表达式有效，因为 `Products.CategoryID` 的类型为 `int?`，这是 `Nullable<int>` 的速记形式。  
  
## <a name="example"></a>示例

 在 join 子句中，如果只有一个比较键是可以为 null 的类型，则可以在查询表达式中将另一个比较键转换为可以为 null 的类型。 在以下示例中，假定 `EmployeeID` 是包含 `int?` 类型的值列：  
  
 [!code-csharp[csProgGuideLINQ#83](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Nullable%601>  
 [LINQ 查询表达式](index.md)  
 [可以为 null 的类型](../programming-guide/nullable-types/index.md)
