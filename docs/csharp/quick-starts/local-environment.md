---
title: "本地环境教程 - C# 本地快速入门"
description: "本快速入门教程介绍了本地运行快速入门教程的基础知识"
author: billwagner
ms.topic: article
ms.date: 12/07/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 9957f524e04f8ff64d4f640cf085b16cf9a2c0c6
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="local-environment"></a><span data-ttu-id="91d0a-103">本地环境</span><span class="sxs-lookup"><span data-stu-id="91d0a-103">Local environment</span></span>

<span data-ttu-id="91d0a-104">在本地试用本快速入门教程的第一步是，在本地计算机上设置开发环境。</span><span class="sxs-lookup"><span data-stu-id="91d0a-104">The first step to trying a quickstart locally is to setup a development environment on your local machine.</span></span>
<span data-ttu-id="91d0a-105">.NET 主题 [10 分钟入门](https://www.microsoft.com/net/core)介绍了如何在 Mac、PC 或 Linux 上设置本地开发环境。</span><span class="sxs-lookup"><span data-stu-id="91d0a-105">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

<span data-ttu-id="91d0a-106">或者，也可以安装 [.NET Core SDK](http://dot.net/core) 和 [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="91d0a-106">Alternatively, you can install the [.NET Core SDK](http://dot.net/core) and [Visual Studio Code](https://code.visualstudio.com/).</span></span>

## <a name="basic-application-development-flow"></a><span data-ttu-id="91d0a-107">基本的应用程序开发流</span><span class="sxs-lookup"><span data-stu-id="91d0a-107">Basic application development flow</span></span>

<span data-ttu-id="91d0a-108">你将使用 [`dotnet new`](../../core/tools/dotnet-new.md) 命令创建应用程序。</span><span class="sxs-lookup"><span data-stu-id="91d0a-108">You'll create applications using the [`dotnet new`](../../core/tools/dotnet-new.md) command.</span></span> <span data-ttu-id="91d0a-109">此命令生成应用程序所需的文件和资产。</span><span class="sxs-lookup"><span data-stu-id="91d0a-109">This command generates the files and assets necessary for your application.</span></span> <span data-ttu-id="91d0a-110">所有快速入门均使用 `console` 应用程序类型。</span><span class="sxs-lookup"><span data-stu-id="91d0a-110">The quickstarts all use the `console` application type.</span></span>

<span data-ttu-id="91d0a-111">你将使用的其他命令是 [`dotnet build`](../../core/tools/dotnet-build.md) 以生成可执行文件，还有 [`dotnet run`](../../core/tools/dotnet-run.md) 以运行可执行文件。</span><span class="sxs-lookup"><span data-stu-id="91d0a-111">The other commands you'll use are [`dotnet build`](../../core/tools/dotnet-build.md) to build the executable, and [`dotnet run`](../../core/tools/dotnet-run.md) to run the executable.</span></span>

## <a name="pick-your-quickstart"></a><span data-ttu-id="91d0a-112">选取你的快速入门</span><span class="sxs-lookup"><span data-stu-id="91d0a-112">Pick your quickstart</span></span>

<span data-ttu-id="91d0a-113">可以从下列任一快速入门教程入手：</span><span class="sxs-lookup"><span data-stu-id="91d0a-113">You can start with any of the following quickstarts:</span></span>

## <a name="numbers-in-cnumbers-in-csharp-localmd"></a>[<span data-ttu-id="91d0a-114">C# 中的数字</span><span class="sxs-lookup"><span data-stu-id="91d0a-114">Numbers in C#</span></span>](numbers-in-csharp-local.md)

<span data-ttu-id="91d0a-115">在 [C# 中的数字](numbers-in-csharp-local.md)快速入门教程中，将了解计算机如何存储数字，以及如何对不同类型的数字执行运算。</span><span class="sxs-lookup"><span data-stu-id="91d0a-115">In the [Numbers in C#](numbers-in-csharp-local.md) quickstart, you'll learn how computers store numbers and how to perform calculations with different numeric types.</span></span> <span data-ttu-id="91d0a-116">读者将学习四舍五入的基础知识，以及如何使用 C# 执行数学运算。</span><span class="sxs-lookup"><span data-stu-id="91d0a-116">You'll learn the basics of rounding, and how to perform mathematical calculations using C#.</span></span> 

<span data-ttu-id="91d0a-117">若要更好地学习本快速入门教程，需要已完成 [Hello world](hello-world.yml) 教程。</span><span class="sxs-lookup"><span data-stu-id="91d0a-117">This quickstart assumes that you have finished the [Hello world](hello-world.yml) tutorial.</span></span>

## <a name="branches-and-loopsbranches-and-loops-localmd"></a>[<span data-ttu-id="91d0a-118">分支和循环</span><span class="sxs-lookup"><span data-stu-id="91d0a-118">Branches and loops</span></span>](branches-and-loops-local.md)

<span data-ttu-id="91d0a-119">在[分支和循环](branches-and-loops-local.md)快速入门教程中，将了解根据变量中存储的值选择不同代码执行路径的基础知识。</span><span class="sxs-lookup"><span data-stu-id="91d0a-119">The [Branches and loops](branches-and-loops-local.md) quickstart teaches the basics of selecting different paths of code execution based on the values stored in variables.</span></span> <span data-ttu-id="91d0a-120">读者将学习控制流的基础知识，这是程序决定选择不同操作的基本依据。</span><span class="sxs-lookup"><span data-stu-id="91d0a-120">You'll learn the basics of control flow, which is the basis of how programs make decisions and choose different actions.</span></span> 

<span data-ttu-id="91d0a-121">若要更好地学习本入门课程，需要已完成 [Hello World](hello-world.yml) 和 [C# 中的数字](numbers-in-csharp-local.md)课程。</span><span class="sxs-lookup"><span data-stu-id="91d0a-121">This beginning lesson assumes that you have finished the [Hello World](hello-world.yml) and [Numbers in C#](numbers-in-csharp-local.md) lessons.</span></span>

## <a name="list-collectionarrays-and-collectionsmd"></a>[<span data-ttu-id="91d0a-122">列表集合</span><span class="sxs-lookup"><span data-stu-id="91d0a-122">List collection</span></span>](arrays-and-collections.md)

<span data-ttu-id="91d0a-123">[列表集合](arrays-and-collections.md)课程将介绍存储一系列数据的列表集合类型。</span><span class="sxs-lookup"><span data-stu-id="91d0a-123">The [List collection](arrays-and-collections.md) lesson gives you a tour of the List collection type that stores sequences of data.</span></span> <span data-ttu-id="91d0a-124">读者将学习如何添加和删除项、如何搜索项，以及如何对列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="91d0a-124">You'll learn how to add and remove items, search for items, and sort the lists.</span></span> <span data-ttu-id="91d0a-125">读者将探索各种列表。</span><span class="sxs-lookup"><span data-stu-id="91d0a-125">You'll explore different kinds of lists.</span></span> 

<span data-ttu-id="91d0a-126">若要更好地学习本基础快速入门教程，需要已完成上面列出的快速入门教程。</span><span class="sxs-lookup"><span data-stu-id="91d0a-126">This beginning quickstart assumes that you have finished the quickstarts listed above.</span></span>

## <a name="introduction-to-classesintroduction-to-classesmd"></a>[<span data-ttu-id="91d0a-127">类简介</span><span class="sxs-lookup"><span data-stu-id="91d0a-127">Introduction to classes</span></span>](introduction-to-classes.md)

<span data-ttu-id="91d0a-128">只能在计算机上使用自己的本地开发环境和 .NET Core 演练最后一个快速入门教程。</span><span class="sxs-lookup"><span data-stu-id="91d0a-128">This final quickstart is only available to run on your machine, using your own local development environment and .NET Core.</span></span>
<span data-ttu-id="91d0a-129">读者将生成控制台应用程序，并了解 C# 语言中面向对象的基本功能的工作原理。</span><span class="sxs-lookup"><span data-stu-id="91d0a-129">You'll build a console application and see the basic object-oriented features that are part of the C# language.</span></span>
