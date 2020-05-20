---
title: by 上下文关键字 - C# 参考
ms.date: 07/20/2015
f1_keywords:
- by
- by_CSharpKeyword
helpviewer_keywords:
- by keyword [C#]
ms.assetid: efe6f0e3-be40-4df2-a144-c7db968ae052
ms.openlocfilehash: 4fa32a0dbfd8210ef8537aee849a55414b107a7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713729"
---
# <a name="by-c-reference"></a><span data-ttu-id="b4480-102">by（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="b4480-102">by (C# Reference)</span></span>

<span data-ttu-id="b4480-103">`by` 上下文关键字用于在查询表达式的 `group` 子句中指定应返回项的分组方式。</span><span class="sxs-lookup"><span data-stu-id="b4480-103">The `by` contextual keyword is used in the `group` clause in a query expression to specify how the returned items should be grouped.</span></span> <span data-ttu-id="b4480-104">有关详细信息，请参阅 [group 子句](./group-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="b4480-104">For more information, see [group clause](./group-clause.md).</span></span>

## <a name="example"></a><span data-ttu-id="b4480-105">示例</span><span class="sxs-lookup"><span data-stu-id="b4480-105">Example</span></span>

<span data-ttu-id="b4480-106">下面的示例演示在 `group` 字句中使用 `by` 关键字指定应根据每个学生的姓氏首字母对学生分组。</span><span class="sxs-lookup"><span data-stu-id="b4480-106">The following example shows the use of the `by` contextual keyword in a `group` clause to specify that the students should be grouped according to the first letter of the last name of each student.</span></span>

[!code-csharp[csrefKeywordsContextual#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#10)]

## <a name="see-also"></a><span data-ttu-id="b4480-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4480-107">See also</span></span>

- [<span data-ttu-id="b4480-108">C# 中的 LINQ</span><span class="sxs-lookup"><span data-stu-id="b4480-108">LINQ in C#</span></span>](../../linq/index.md)
