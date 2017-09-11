---
title: "let 子句（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- let_CSharpKeyword
- let
dev_langs:
- CSharp
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 37ec0cb0c8c374a0b5250d82e880c96696b5584a
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="let-clause-c-reference"></a><span data-ttu-id="dd910-102">let 子句（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="dd910-102">let clause (C# Reference)</span></span>
<span data-ttu-id="dd910-103">在查询表达式中，存储子表达式的结果有时很有帮助，可在后续子句中使用。</span><span class="sxs-lookup"><span data-stu-id="dd910-103">In a query expression, it is sometimes useful to store the result of a sub-expression in order to use it in subsequent clauses.</span></span> <span data-ttu-id="dd910-104">可以通过 `let` 关键字执行此操作，该关键字创建一个新的范围变量并通过提供的表达式结果初始化该变量。</span><span class="sxs-lookup"><span data-stu-id="dd910-104">You can do this with the `let` keyword, which creates a new range variable and initializes it with the result of the expression you supply.</span></span> <span data-ttu-id="dd910-105">使用值进行初始化后，范围变量不能用于存储另一个值。</span><span class="sxs-lookup"><span data-stu-id="dd910-105">Once initialized with a value, the range variable cannot be used to store another value.</span></span> <span data-ttu-id="dd910-106">但是，如果范围变量持有可查询类型，则可以查询该变量。</span><span class="sxs-lookup"><span data-stu-id="dd910-106">However, if the range variable holds a queryable type, it can be queried.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd910-107">示例</span><span class="sxs-lookup"><span data-stu-id="dd910-107">Example</span></span>  
 <span data-ttu-id="dd910-108">以两种方式使用以下示例 `let`：</span><span class="sxs-lookup"><span data-stu-id="dd910-108">In the following example `let` is used in two ways:</span></span>  
  
1.  <span data-ttu-id="dd910-109">创建一个可以查询其自身的可枚举类型。</span><span class="sxs-lookup"><span data-stu-id="dd910-109">To create an enumerable type that can itself be queried.</span></span>  
  
2.  <span data-ttu-id="dd910-110">使查询仅调用一次范围变量 `word` 上的 `ToLower`。</span><span class="sxs-lookup"><span data-stu-id="dd910-110">To enable the query to call `ToLower` only one time on the range variable `word`.</span></span> <span data-ttu-id="dd910-111">如果不使用 `let`，则不得不调用 `where` 子句中的每个谓词的 `ToLower`。</span><span class="sxs-lookup"><span data-stu-id="dd910-111">Without using `let`, you would have to call `ToLower` in each predicate in the `where` clause.</span></span>  
  
 <span data-ttu-id="dd910-112">[!code-cs[cscsrefQueryKeywords#28](../../../csharp/language-reference/keywords/codesnippet/CSharp/let-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="dd910-112">[!code-cs[cscsrefQueryKeywords#28](../../../csharp/language-reference/keywords/codesnippet/CSharp/let-clause_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd910-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd910-113">See Also</span></span>  
 <span data-ttu-id="dd910-114">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="dd910-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="dd910-115">[查询关键字 (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="dd910-115">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="dd910-116">[LINQ 查询表达式](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="dd910-116">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 <span data-ttu-id="dd910-117">[C# 中的 LINQ 入门](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) </span><span class="sxs-lookup"><span data-stu-id="dd910-117">[Getting Started with LINQ in C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) </span></span>  
 [<span data-ttu-id="dd910-118">如何：在查询表达式中处理异常</span><span class="sxs-lookup"><span data-stu-id="dd910-118">How to: Handle Exceptions in Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)

