---
title: "F# 指南"
description: "了解有关 F # 编程语言，函数编程提供一流的支持的.NET 开放源代码语言。"
keywords: .NET, .NET Core
author: jackfoxy
ms.author: phcart
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ea27fb37-dad1-4bd4-a3cc-4f5c70767ae9
ms.openlocfilehash: 4ddd77cef6cf70a63f1af81359d82eda27a01593
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="f-guide"></a><span data-ttu-id="45adc-104">F# 指南</span><span class="sxs-lookup"><span data-stu-id="45adc-104">F# Guide</span></span>

<span data-ttu-id="45adc-105">F# 是一种用于 .NET 的跨平台开放源编程语言，提供一流的函数编程支持，同时还支持面向对象的编程和命令性编程。</span><span class="sxs-lookup"><span data-stu-id="45adc-105">F# is a cross-platform, open source programming language for .NET which provides first-class support for functional programming, along with support of object-oriented and imperative programming.</span></span>  <span data-ttu-id="45adc-106">Visual F# 编译器和工具是 Microsoft 针对 F# 编程语言的实现和工具，使 F# 成为 .NET 的第一等成员。</span><span class="sxs-lookup"><span data-stu-id="45adc-106">The Visual F# compiler and tooling are Microsoft's implementation and tooling for the F# programming language, making F# a first-class member of .NET.</span></span>

## <a name="if-youre-new-to-f"></a><span data-ttu-id="45adc-107">如果您是初次接触 F #</span><span class="sxs-lookup"><span data-stu-id="45adc-107">If You're New to F#</span></span> #

<span data-ttu-id="45adc-108">如果你是新手 F #，以开始[教程的 F #](tour.md)以获取语言的概述。</span><span class="sxs-lookup"><span data-stu-id="45adc-108">If you're new to F#, begin with the [Tour of F#](tour.md) to get an overview of the language.</span></span>

<span data-ttu-id="45adc-109">此外，还建议你将完成[函数作为一类值](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Progamming](introduction-to-functional-programming/index.md)-->若要了解对使用 F # 至关重要的函数编程概念。</span><span class="sxs-lookup"><span data-stu-id="45adc-109">It's also recommended that you go through the [Functions as First-Class Values](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Progamming](introduction-to-functional-programming/index.md)--> to learn Functional Programming concepts which are essential to working with F#.</span></span>

<span data-ttu-id="45adc-110">[教程](tutorials/getting-started/index.md)还包含针对各种技能水平的分步指南以及该语言的各功能。</span><span class="sxs-lookup"><span data-stu-id="45adc-110">The [Tutorials](tutorials/getting-started/index.md) also have step-by-step guides for various skill levels and features of the language.</span></span>

## <a name="if-youre-experienced-with-f"></a><span data-ttu-id="45adc-111">如果你有使用 F # 经验</span><span class="sxs-lookup"><span data-stu-id="45adc-111">If You're Experienced with F#</span></span> #

<span data-ttu-id="45adc-112">如果熟知 F#，会在[语言参考](language-reference/index.md)中发现很多用法，语言参考中详细记录了语言的每个方面，并补充提供了许多代码示例。</span><span class="sxs-lookup"><span data-stu-id="45adc-112">If you know your way around F#, you'll find a lot of use in the [Language Reference](language-reference/index.md), which documents each aspect of the language thoroughly, supplemented by numerous code samples.</span></span>  <span data-ttu-id="45adc-113">还会在 [F# 核心库参考](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference)中发现很多用法。</span><span class="sxs-lookup"><span data-stu-id="45adc-113">You'll also find a lot of use in the [F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference).</span></span>  <span data-ttu-id="45adc-114">F # 核心库参考最终将移动，离开 MSDN 和到这些当前文档。</span><span class="sxs-lookup"><span data-stu-id="45adc-114">The F# Core Library Reference will eventually move away from MSDN and into these current docs.</span></span>

## <a name="the-f-software-foundation"></a><span data-ttu-id="45adc-115">F# 软件基金会</span><span class="sxs-lookup"><span data-stu-id="45adc-115">The F# Software Foundation</span></span>

<span data-ttu-id="45adc-116">尽管 Microsoft 是 F# 语言和 Visual F# 工具的主要开发者，但 F# 还由独立的基金会 - F# 软件基金会 (FSSF) 提供支持。</span><span class="sxs-lookup"><span data-stu-id="45adc-116">Although Microsoft is the primary developer of the F# language and Visual F# Tooling, F# is also backed by an independent foundation, the F# Software Foundation (FSSF).</span></span>

<span data-ttu-id="45adc-117">F# 软件基金会的任务是提升、保护和改进 F# 编程语言，以及支持和促进国际化的多元 F# 程序员社区的成长。</span><span class="sxs-lookup"><span data-stu-id="45adc-117">The mission of the F# Software Foundation is to promote, protect, and advance the F# programming language, and to support and facilitate the growth of a diverse and international community of F# programmers.</span></span>

<span data-ttu-id="45adc-118">若要了解详细信息并参与，请查看 [fsharp.org](http://fsharp.org)。</span><span class="sxs-lookup"><span data-stu-id="45adc-118">To learn more and get involved, check out [fsharp.org](http://fsharp.org).</span></span>

## <a name="documentation"></a><span data-ttu-id="45adc-119">文档</span><span class="sxs-lookup"><span data-stu-id="45adc-119">Documentation</span></span>

* [<span data-ttu-id="45adc-120">教程</span><span class="sxs-lookup"><span data-stu-id="45adc-120">Tutorials</span></span>](tutorials/getting-started/index.md)
* <span data-ttu-id="45adc-121">[作为一类值的函数](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span><span class="sxs-lookup"><span data-stu-id="45adc-121">[Functions as First-Class Values](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span></span>
* [<span data-ttu-id="45adc-122">语言参考</span><span class="sxs-lookup"><span data-stu-id="45adc-122">Language Reference</span></span>](language-reference/index.md)
* [<span data-ttu-id="45adc-123">F# 核心库参考</span><span class="sxs-lookup"><span data-stu-id="45adc-123">F# Core Library Reference</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference)

## <a name="online-reading-resources"></a><span data-ttu-id="45adc-124">联机阅读资源</span><span class="sxs-lookup"><span data-stu-id="45adc-124">Online Reading Resources</span></span>

* [<span data-ttu-id="45adc-125">F# 的趣味和益处 Gitbook</span><span class="sxs-lookup"><span data-stu-id="45adc-125">F# for Fun and Profit Gitbook</span></span>](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) 
* [<span data-ttu-id="45adc-126">F# 编程 Wikibook</span><span class="sxs-lookup"><span data-stu-id="45adc-126">F# Programming Wikibook</span></span>](https://en.wikibooks.org/wiki/F_Sharp_Programming)

## <a name="video-learning-resources"></a><span data-ttu-id="45adc-127">视频学习资源</span><span class="sxs-lookup"><span data-stu-id="45adc-127">Video Learning Resources</span></span>

* [<span data-ttu-id="45adc-128">YouTube 上的 F# 系列编程简介</span><span class="sxs-lookup"><span data-stu-id="45adc-128">Introduction to Programming with F# series on YouTube</span></span>](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC)
* [<span data-ttu-id="45adc-129">FSharpTV 上的 F# 系列简介</span><span class="sxs-lookup"><span data-stu-id="45adc-129">Introduction to F# series on FSharpTV</span></span>](https://fsharp.tv/courses/fsharp-programming-intro/)

## <a name="further-resources"></a><span data-ttu-id="45adc-130">其他资源</span><span class="sxs-lookup"><span data-stu-id="45adc-130">Further Resources</span></span>

* [<span data-ttu-id="45adc-131">Ffsharp.org 上的 F# 学习资源</span><span class="sxs-lookup"><span data-stu-id="45adc-131">F# Learning Resources on fsharp.org</span></span>](http://fsharp.org/learn.html)
* [<span data-ttu-id="45adc-132">F# 代码段网站</span><span class="sxs-lookup"><span data-stu-id="45adc-132">F# Snippets Website</span></span>](http://www.fssnip.net)
* [<span data-ttu-id="45adc-133">F# 软件基金会</span><span class="sxs-lookup"><span data-stu-id="45adc-133">F# Software Foundation</span></span>](http://fsharp.org)
