---
title: "如何：在查询中使用 Lambda 表达式（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: lambda expressions [C#], in LINQ
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 279d76aa29f27d35bc907d6779a146a23c7e162a
ms.sourcegitcommit: bf8a3ba647252010bdce86dd914ac6c61b5ba89d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2018
---
# <a name="how-to-use-lambda-expressions-in-a-query-c-programming-guide"></a>如何：在查询中使用 Lambda 表达式（C# 编程指南）
不会直接在查询语法中使用 lambda 表达式，而是在方法调用中使用它们，并且查询表达式可以包含方法调用。 事实上，一些查询操作只能采用方法语法进行表示。 有关查询语法与方法语法之间的差异的详细信息，请参阅 [LINQ 中的查询语法和方法语法](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示如何通过 <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> 标准查询运算符，在基于方法的查询中使用 lambda 表达式。 请注意，此示例中的 <xref:System.Linq.Enumerable.Where%2A> 方法具有一个 <xref:System.Func%601> 委托类型的输入参数，该委托采用整数作为输入并返回一个布尔值。 Lambda 表达式可以转换为该委托。 如果这是使用 <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType> 方法的 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 查询，则参数类型会是 `Expression<Func<int,bool>>`，但 lambda 表达式看起来完全相同。 有关表达式类型的详细信息，请参阅 <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType>。  
  
 [!code-csharp[csProgGuideLINQ#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_1.cs)]  
  
## <a name="example"></a>示例  
 下面的示例演示如何在查询表达式的方法调用中使用 lambda 表达式。 需要 lambda 的原因是无法使用查询语法调用 <xref:System.Linq.Enumerable.Sum%2A> 标准查询运算符。  
  
 查询首先根据学生的年级（在 `GradeLevel` 枚举中定义）对学生进行分组。 然后为每个组添加每个学生的总分。 这需要两个 `Sum` 操作。 内部 `Sum` 为每个学生计算总分，而外部 `Sum` 保留组中所有学生的正在运行的合并总分。  
  
 [!code-csharp[csProgGuideLINQ#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_2.cs)]  
  
## <a name="compiling-the-code"></a>编译代码  
 若要运行此代码，请将方法复制并粘贴到[如何：查询对象的集合](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md)中提供的 `StudentClass` 中，然后从 `Main` 方法调用它。  
  
## <a name="see-also"></a>请参阅  
 [Lambda 表达式](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
 [表达式树](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)
