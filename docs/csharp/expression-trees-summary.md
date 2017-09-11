---
title: "表达式树摘要"
description: "总结如何使用表达式树创建将代码解释为数据并基于该代码生成新功能的动态程序。"
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: eb687ebd-1149-4453-9fc1-12a084495a66
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8088ce0c138cdb05a6e4a4fb6467e43efd252ba7
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="expression-trees-summary"></a><span data-ttu-id="22586-104">表达式树摘要</span><span class="sxs-lookup"><span data-stu-id="22586-104">Expression Trees Summary</span></span>

[<span data-ttu-id="22586-105">上一篇 - 翻译表达式</span><span class="sxs-lookup"><span data-stu-id="22586-105">Previous -- Translating Expressions</span></span>](expression-trees-translating.md)

<span data-ttu-id="22586-106">在此系列中，你已了解如何使用*表达式树*创建将代码解释为数据并基于该代码生成新功能的动态程序。</span><span class="sxs-lookup"><span data-stu-id="22586-106">In this series, you've seen how you can use *expression trees* to create dynamic programs that interpret code as data and build new functionality based on that code.</span></span>

<span data-ttu-id="22586-107">可以检查表达式树以了解算法的目的。</span><span class="sxs-lookup"><span data-stu-id="22586-107">You can examine expression trees to understand the intent of an algorithm.</span></span> <span data-ttu-id="22586-108">不仅可以检查该代码。</span><span class="sxs-lookup"><span data-stu-id="22586-108">You can not only examine that code.</span></span> <span data-ttu-id="22586-109">可以生成表示原始代码的修改版本的新表达式树。</span><span class="sxs-lookup"><span data-stu-id="22586-109">You can build new expression trees that represent modified versions of the original code.</span></span>

<span data-ttu-id="22586-110">还可以使用表达式树来查看算法，并将该算法翻译成另一种语言或环境。</span><span class="sxs-lookup"><span data-stu-id="22586-110">You can also use expression trees to look at an algorithm, and translate that algorithm into another language or environment.</span></span> 

## <a name="limitations"></a><span data-ttu-id="22586-111">限制</span><span class="sxs-lookup"><span data-stu-id="22586-111">Limitations</span></span>

<span data-ttu-id="22586-112">存在一些不好翻译成表达式树的较新的 C# 语言元素。</span><span class="sxs-lookup"><span data-stu-id="22586-112">There are some newer C# language elements that don't translate well into expression trees.</span></span> <span data-ttu-id="22586-113">表达式树不能包含 `await` 表达式或 `async` lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="22586-113">Expression trees cannot contain `await` expressions, or `async` lambda expressions.</span></span> <span data-ttu-id="22586-114">C# 6 发行中添加的许多功能不会完全按照表达式树中所编写的那样显示。</span><span class="sxs-lookup"><span data-stu-id="22586-114">Many of the features added in the C# 6 release don't appear exactly as written in expression trees.</span></span> <span data-ttu-id="22586-115">较新的功能可能会显示在表达式树中等效、早期的语法中。</span><span class="sxs-lookup"><span data-stu-id="22586-115">Instead, newer features will be exposed in expressions trees in the equivalent, earlier syntax.</span></span> <span data-ttu-id="22586-116">这可能不像你想象的那样有局限性。</span><span class="sxs-lookup"><span data-stu-id="22586-116">This may not be as much of a limitation as you might think.</span></span> <span data-ttu-id="22586-117">实际上，这意味着在引入新语言功能时，解释表达式树的代码将仍可能照常运行。</span><span class="sxs-lookup"><span data-stu-id="22586-117">In fact, it means that your code that interprets expression trees will likely still work the same when new language features are introduced.</span></span>

<span data-ttu-id="22586-118">即使具有这些限制，通过表达式树，仍可创建依赖于解释和修改表示为数据结构的代码的动态算法。</span><span class="sxs-lookup"><span data-stu-id="22586-118">Even with these limitations, expression trees do enable you to create dynamic algorithms that rely on interpreting and modifying code that is represetned as a data structure.</span></span> <span data-ttu-id="22586-119">它是一种功能强大的工具，作为 .NET 生态系统的一种功能，它可使丰富的库（如实体框架）完成其所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="22586-119">It's a powerful tool, and it's one of the features of the .NET ecosystem that enables rich libraries such as Entity Framework to accomplish what they do.</span></span>


