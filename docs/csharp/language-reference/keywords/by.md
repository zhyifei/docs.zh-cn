---
title: by 上下文关键字 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- by
- by_CSharpKeyword
helpviewer_keywords:
- by keyword [C#]
ms.assetid: efe6f0e3-be40-4df2-a144-c7db968ae052
ms.openlocfilehash: d8632c9fd722a7e9864628013e87b24d7e6633c5
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241296"
---
# <a name="by-c-reference"></a><span data-ttu-id="f98aa-102">by（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="f98aa-102">by (C# Reference)</span></span>

<span data-ttu-id="f98aa-103">`by` 上下文关键字用于在查询表达式的 `group` 子句中指定应返回项的分组方式。</span><span class="sxs-lookup"><span data-stu-id="f98aa-103">The `by` contextual keyword is used in the `group` clause in a query expression to specify how the returned items should be grouped.</span></span> <span data-ttu-id="f98aa-104">有关详细信息，请参阅 [group 子句](../../../csharp/language-reference/keywords/group-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="f98aa-104">For more information, see [group clause](../../../csharp/language-reference/keywords/group-clause.md).</span></span>

## <a name="example"></a><span data-ttu-id="f98aa-105">示例</span><span class="sxs-lookup"><span data-stu-id="f98aa-105">Example</span></span>

<span data-ttu-id="f98aa-106">下面的示例演示在 `group` 字句中使用 `by` 关键字指定应根据每个学生的姓氏首字母对学生分组。</span><span class="sxs-lookup"><span data-stu-id="f98aa-106">The following example shows the use of the `by` contextual keyword in a `group` clause to specify that the students should be grouped according to the first letter of the last name of each student.</span></span>

[!code-csharp[csrefKeywordsContextual#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#10)]

## <a name="see-also"></a><span data-ttu-id="f98aa-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="f98aa-107">See also</span></span>

- [<span data-ttu-id="f98aa-108">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="f98aa-108">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)
