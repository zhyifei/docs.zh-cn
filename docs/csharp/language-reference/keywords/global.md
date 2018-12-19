---
title: global 上下文关键字 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- global
- global_CSharpKeyword
helpviewer_keywords:
- global keyword [C#]
ms.assetid: 8932c16a-6959-42c2-86e7-2c4221ab788b
ms.openlocfilehash: b9273feb38b14dce61facc0f59b0890c431b9a7a
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240786"
---
# <a name="global-c-reference"></a><span data-ttu-id="7ec11-102">global（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="7ec11-102">global (C# Reference)</span></span>

<span data-ttu-id="7ec11-103">`global` 上下文关键字位于 [:: 运算符](../operators/namespace-alias-qualifer.md) 之前时引用全局命名空间（即任何 C# 程序的默认命名空间，否则其未被命名）。</span><span class="sxs-lookup"><span data-stu-id="7ec11-103">The `global` contextual keyword, when it comes before the [:: operator](../operators/namespace-alias-qualifer.md), refers to the global namespace, which is the default namespace for any C# program and is otherwise unnamed.</span></span> <span data-ttu-id="7ec11-104">有关更多信息，请参见[如何：使用全局命名空间别名](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)。</span><span class="sxs-lookup"><span data-stu-id="7ec11-104">For more information, see [How to: Use the Global Namespace Alias](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).</span></span>

## <a name="example"></a><span data-ttu-id="7ec11-105">示例</span><span class="sxs-lookup"><span data-stu-id="7ec11-105">Example</span></span>

<span data-ttu-id="7ec11-106">如下示例演示如何使用 `global` 上下文关键字来指定在全局命名空间中定义类 `TestApp`：</span><span class="sxs-lookup"><span data-stu-id="7ec11-106">The following example shows how to use the `global` contextual keyword to specify that the class `TestApp` is defined in the global namespace:</span></span>

[!code-csharp[csrefKeywordsContextual#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#13)]

## <a name="see-also"></a><span data-ttu-id="7ec11-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ec11-107">See also</span></span>

- [<span data-ttu-id="7ec11-108">命名空间</span><span class="sxs-lookup"><span data-stu-id="7ec11-108">Namespaces</span></span>](../../programming-guide/namespaces/index.md)