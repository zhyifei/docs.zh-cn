---
title: "F# 指南"
description: "了解有关 F # 中，在.NET 运行的函数编程语言。"
keywords: .NET, .NET Core
author: jackfoxy
ms.author: phcart
ms.date: 12/01/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ea27fb37-dad1-4bd4-a3cc-4f5c70767ae9
ms.openlocfilehash: 45f5d2ca794ccea7a35cf6c0bf9d58a3e6500453
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="f-guide"></a><span data-ttu-id="dff9b-104">F# 指南</span><span class="sxs-lookup"><span data-stu-id="dff9b-104">F# Guide</span></span>

<span data-ttu-id="dff9b-105">F # 是一功能的编程语言，它在.NET 上运行。</span><span class="sxs-lookup"><span data-stu-id="dff9b-105">F# is a functional programming language which runs on .NET.</span></span>  <span data-ttu-id="dff9b-106">除了支持函数编程构造，它还具有对象编程功能。</span><span class="sxs-lookup"><span data-stu-id="dff9b-106">In addition to supporting functional programming constructs, it also has object programming capabilities.</span></span>  <span data-ttu-id="dff9b-107">此混合函数编程和面向对象的功能使 F # 完成任何任务的编程语言。</span><span class="sxs-lookup"><span data-stu-id="dff9b-107">This hybrid of functional programming with object-oriented capabilities makes F# a pragmatic language for accomplishing any task.</span></span>

## <a name="if-youre-new-to-f"></a><span data-ttu-id="dff9b-108">如果您是初次接触 F #</span><span class="sxs-lookup"><span data-stu-id="dff9b-108">If You're New to F#</span></span> #

<span data-ttu-id="dff9b-109">如果你是新手 F #，以开始[教程的 F #](tour.md)若要获取的语言的概述和一些其编程概念。</span><span class="sxs-lookup"><span data-stu-id="dff9b-109">If you're new to F#, begin with the [Tour of F#](tour.md) to get an overview of the language and some of its programming concepts.</span></span>  <span data-ttu-id="dff9b-110">如果你使用 Visual Studio，该教程的项目模板将包含相同的内容。</span><span class="sxs-lookup"><span data-stu-id="dff9b-110">If you're using Visual Studio, the Tutorial project template contains the same content.</span></span>

## <a name="if-youre-experienced-with-f"></a><span data-ttu-id="dff9b-111">如果你有使用 F # 经验</span><span class="sxs-lookup"><span data-stu-id="dff9b-111">If You're Experienced with F#</span></span> #

<span data-ttu-id="dff9b-112">如果你知道方面 F # 中，或者想要了解有关特定语言构造的详细信息，请参阅[语言参考](language-reference/index.md)。</span><span class="sxs-lookup"><span data-stu-id="dff9b-112">If you know your way around F#, or want to learn more about a specific language construct, see the [Language Reference](language-reference/index.md).</span></span>  <span data-ttu-id="dff9b-113">它是所有的 F # 语言功能的全面指南。</span><span class="sxs-lookup"><span data-stu-id="dff9b-113">It's a thorough guide of all F# language capabilities.</span></span>

<span data-ttu-id="dff9b-114">此外， [F # 核心库参考](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference)是可用于了解 FSharp.Core，这是属于 F # 核心库的重大资源。</span><span class="sxs-lookup"><span data-stu-id="dff9b-114">Additionally, the [F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) is a great resource for learning about FSharp.Core, the core library which is a part of F#.</span></span>

## <a name="the-f-software-foundation"></a><span data-ttu-id="dff9b-115">F# 软件基金会</span><span class="sxs-lookup"><span data-stu-id="dff9b-115">The F# Software Foundation</span></span>

<span data-ttu-id="dff9b-116">尽管 Microsoft 是主 F # 语言和其工具的开发人员，F # 还支持独立的基础，F # 软件 Foundation (FSSF)。</span><span class="sxs-lookup"><span data-stu-id="dff9b-116">Although Microsoft is the primary developer of the F# language and its tooling, F# is also backed by an independent foundation, the F# Software Foundation (FSSF).</span></span>

<span data-ttu-id="dff9b-117">F# 软件基金会的任务是提升、保护和改进 F# 编程语言，以及支持和促进国际化的多元 F# 程序员社区的成长。</span><span class="sxs-lookup"><span data-stu-id="dff9b-117">The mission of the F# Software Foundation is to promote, protect, and advance the F# programming language, and to support and facilitate the growth of a diverse and international community of F# programmers.</span></span>

<span data-ttu-id="dff9b-118">若要了解详细信息并参与，请查看 [fsharp.org](http://fsharp.org)。</span><span class="sxs-lookup"><span data-stu-id="dff9b-118">To learn more and get involved, check out [fsharp.org](http://fsharp.org).</span></span>

## <a name="documentation"></a><span data-ttu-id="dff9b-119">文档</span><span class="sxs-lookup"><span data-stu-id="dff9b-119">Documentation</span></span>

* [<span data-ttu-id="dff9b-120">教程</span><span class="sxs-lookup"><span data-stu-id="dff9b-120">Tutorials</span></span>](tutorials/getting-started/index.md)
* <span data-ttu-id="dff9b-121">[作为一类值的函数](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span><span class="sxs-lookup"><span data-stu-id="dff9b-121">[Functions as First-Class Values](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span></span>
* [<span data-ttu-id="dff9b-122">语言参考</span><span class="sxs-lookup"><span data-stu-id="dff9b-122">Language Reference</span></span>](language-reference/index.md)
* [<span data-ttu-id="dff9b-123">F# 核心库参考</span><span class="sxs-lookup"><span data-stu-id="dff9b-123">F# Core Library Reference</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference)

## <a name="online-reading-resources"></a><span data-ttu-id="dff9b-124">联机阅读资源</span><span class="sxs-lookup"><span data-stu-id="dff9b-124">Online Reading Resources</span></span>

* [<span data-ttu-id="dff9b-125">F# 的趣味和益处 Gitbook</span><span class="sxs-lookup"><span data-stu-id="dff9b-125">F# for Fun and Profit Gitbook</span></span>](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) 
* [<span data-ttu-id="dff9b-126">F# 编程 Wikibook</span><span class="sxs-lookup"><span data-stu-id="dff9b-126">F# Programming Wikibook</span></span>](https://en.wikibooks.org/wiki/F_Sharp_Programming)

## <a name="video-learning-resources"></a><span data-ttu-id="dff9b-127">视频学习资源</span><span class="sxs-lookup"><span data-stu-id="dff9b-127">Video Learning Resources</span></span>

* [<span data-ttu-id="dff9b-128">YouTube 上的 F# 系列编程简介</span><span class="sxs-lookup"><span data-stu-id="dff9b-128">Introduction to Programming with F# series on YouTube</span></span>](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC)
* [<span data-ttu-id="dff9b-129">FSharpTV 上的 F# 系列简介</span><span class="sxs-lookup"><span data-stu-id="dff9b-129">Introduction to F# series on FSharpTV</span></span>](https://fsharp.tv/courses/fsharp-programming-intro/)

## <a name="further-resources"></a><span data-ttu-id="dff9b-130">其他资源</span><span class="sxs-lookup"><span data-stu-id="dff9b-130">Further Resources</span></span>

* [<span data-ttu-id="dff9b-131">Ffsharp.org 上的 F# 学习资源</span><span class="sxs-lookup"><span data-stu-id="dff9b-131">F# Learning Resources on fsharp.org</span></span>](http://fsharp.org/learn.html)
* [<span data-ttu-id="dff9b-132">F# 代码段网站</span><span class="sxs-lookup"><span data-stu-id="dff9b-132">F# Snippets Website</span></span>](http://www.fssnip.net)
* [<span data-ttu-id="dff9b-133">F# 软件基金会</span><span class="sxs-lookup"><span data-stu-id="dff9b-133">F# Software Foundation</span></span>](http://fsharp.org)