---
title: "使用 .NET 编译器 SDK - C# 指南"
description: "探索了 Roslyn API，以创建自动诊断和代码修复"
keywords: .NET, .NET Core, C#, Roslyn,
ms.date: 06/25/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: abed9e00-2ddc-468e-9cca-d033bd6a7e36
redirect_url: /dotnet/csharp/index
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b227d67fd5431da328e1686fd9afc6a3b9db035e
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="-using-the-net-compiler-sdk"></a><span data-ttu-id="44fac-104">🔧 使用 .NET 编译器 SDK</span><span class="sxs-lookup"><span data-stu-id="44fac-104">🔧 Using the .NET Compiler SDK</span></span>

> <span data-ttu-id="44fac-105">**注意**</span><span class="sxs-lookup"><span data-stu-id="44fac-105">**Note**</span></span>
> 
> <span data-ttu-id="44fac-106">尚未编写此主题！</span><span class="sxs-lookup"><span data-stu-id="44fac-106">This topic hasn’t been written yet!</span></span> 
>
> <span data-ttu-id="44fac-107">欢迎提供建议，以帮助我们确定范围和方法。</span><span class="sxs-lookup"><span data-stu-id="44fac-107">We welcome your input to help shape the scope and approach.</span></span> <span data-ttu-id="44fac-108">可在 GitHub 处跟踪有关此[问题](https://github.com/dotnet/docs/issues/972)的状态并提供相关建议。</span><span class="sxs-lookup"><span data-stu-id="44fac-108">You can track the status and provide input on this [issue](https://github.com/dotnet/docs/issues/972) at GitHub.</span></span>
> 
> <span data-ttu-id="44fac-109">如果想要查看此主题的早期草稿和概述，请就此问题留下包含联系信息的备注。</span><span class="sxs-lookup"><span data-stu-id="44fac-109">If you would like to review early drafts and outlines of this topic, please leave a note with your contact information in the issue.</span></span>
>
> <span data-ttu-id="44fac-110">了解如何参与 [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md) 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="44fac-110">Learn more about how you can contribute on [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>
>

<span data-ttu-id="44fac-111">这是整个部分的元主题。</span><span class="sxs-lookup"><span data-stu-id="44fac-111">This is a meta-topic for an entire section.</span></span> <span data-ttu-id="44fac-112">此处需要涉及的领域包括：</span><span class="sxs-lookup"><span data-stu-id="44fac-112">Areas that need to be covered here include:</span></span> 
* <span data-ttu-id="44fac-113">入门</span><span class="sxs-lookup"><span data-stu-id="44fac-113">Getting Started</span></span>
* <span data-ttu-id="44fac-114">示例和教程</span><span class="sxs-lookup"><span data-stu-id="44fac-114">Samples and tutorials</span></span>
* <span data-ttu-id="44fac-115">概念性内容</span><span class="sxs-lookup"><span data-stu-id="44fac-115">conceptual content</span></span>
* <span data-ttu-id="44fac-116">API 的整体模型</span><span class="sxs-lookup"><span data-stu-id="44fac-116">overall model of the APIs</span></span>
* <span data-ttu-id="44fac-117">指向 [roslyn-analyzerers](http://github.com/dotnet/roslyn-analyzers) 存储库中示例的链接</span><span class="sxs-lookup"><span data-stu-id="44fac-117">links to samples on the [roslyn-analyzers](http://github.com/dotnet/roslyn-analyzers) repository</span></span>
* <span data-ttu-id="44fac-118">指向其他参考内容的链接</span><span class="sxs-lookup"><span data-stu-id="44fac-118">links to other reference content</span></span>

