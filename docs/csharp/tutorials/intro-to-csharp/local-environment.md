---
title: C# 简介 - 熟悉开发工具
description: 本文介绍用于在计算机上开发 C# 和 .NET 应用程序的工具的基本知识。
ms.date: 10/23/2018
ms.openlocfilehash: b18c71c54e4450902f576a1074058abcd5e8aa91
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834076"
---
# <a name="become-familiar-with-the-net-development-tools"></a><span data-ttu-id="cbec6-103">熟悉 .NET 开发工具</span><span class="sxs-lookup"><span data-stu-id="cbec6-103">Become familiar with the .NET development tools</span></span>

<span data-ttu-id="cbec6-104">在计算机上演练教程的第一步是设置开发环境。</span><span class="sxs-lookup"><span data-stu-id="cbec6-104">The first step in running a tutorial on your machine is to set up a development environment.</span></span>
<span data-ttu-id="cbec6-105">.NET 教程 [Hello World 10 分钟入门](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro)介绍了如何在 Windows、Linux 或 macOS 上设置本地开发环境。</span><span class="sxs-lookup"><span data-stu-id="cbec6-105">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span>

<span data-ttu-id="cbec6-106">或者，也可以安装 [.NET Core SDK](https://dotnet.microsoft.com/download) 和 [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="cbec6-106">Alternatively, you can install the [.NET Core SDK](https://dotnet.microsoft.com/download) and [Visual Studio Code](https://code.visualstudio.com/).</span></span>

## <a name="basic-application-development-flow"></a><span data-ttu-id="cbec6-107">基本的应用程序开发流</span><span class="sxs-lookup"><span data-stu-id="cbec6-107">Basic application development flow</span></span>

<span data-ttu-id="cbec6-108">你将使用 [`dotnet new`](../../../core/tools/dotnet-new.md) 命令创建应用程序。</span><span class="sxs-lookup"><span data-stu-id="cbec6-108">You'll create applications using the [`dotnet new`](../../../core/tools/dotnet-new.md) command.</span></span> <span data-ttu-id="cbec6-109">此命令生成应用程序所需的文件和资产。</span><span class="sxs-lookup"><span data-stu-id="cbec6-109">This command generates the files and assets necessary for your application.</span></span> <span data-ttu-id="cbec6-110">C# 简介的所有教程都使用 `console` 应用程序类型。</span><span class="sxs-lookup"><span data-stu-id="cbec6-110">The introduction to C# tutorials all use the `console` application type.</span></span> <span data-ttu-id="cbec6-111">了解基础知识后，可以扩展到其他应用程序类型。</span><span class="sxs-lookup"><span data-stu-id="cbec6-111">Once you've got the basics, you can expand to other application types.</span></span>

<span data-ttu-id="cbec6-112">你将使用的其他命令是 [`dotnet build`](../../../core/tools/dotnet-build.md) 以生成可执行文件，还有 [`dotnet run`](../../../core/tools/dotnet-run.md) 以运行可执行文件。</span><span class="sxs-lookup"><span data-stu-id="cbec6-112">The other commands you'll use are [`dotnet build`](../../../core/tools/dotnet-build.md) to build the executable, and [`dotnet run`](../../../core/tools/dotnet-run.md) to run the executable.</span></span>

## <a name="pick-your-tutorial"></a><span data-ttu-id="cbec6-113">选择教程</span><span class="sxs-lookup"><span data-stu-id="cbec6-113">Pick your tutorial</span></span>

<span data-ttu-id="cbec6-114">可以从下列任一教程入手：</span><span class="sxs-lookup"><span data-stu-id="cbec6-114">You can start with any of the following tutorials:</span></span>

## <a name="numbers-in-cnumbers-in-csharp-localmd"></a>[<span data-ttu-id="cbec6-115">C# 中的数字</span><span class="sxs-lookup"><span data-stu-id="cbec6-115">Numbers in C#</span></span>](numbers-in-csharp-local.md)

<span data-ttu-id="cbec6-116">在 [C# 中的数字](numbers-in-csharp-local.md)教程中，将了解计算机如何存储数字，以及如何对不同类型的数字执行计算。</span><span class="sxs-lookup"><span data-stu-id="cbec6-116">In the [Numbers in C#](numbers-in-csharp-local.md) tutorial, you'll learn how computers store numbers and how to perform calculations with different numeric types.</span></span> <span data-ttu-id="cbec6-117">读者将学习四舍五入的基础知识，以及如何使用 C# 执行数学运算。</span><span class="sxs-lookup"><span data-stu-id="cbec6-117">You'll learn the basics of rounding and how to perform mathematical calculations using C#.</span></span>

<span data-ttu-id="cbec6-118">若要更好地学习本教程，需要已完成 [Hello world](hello-world.yml) 课程。</span><span class="sxs-lookup"><span data-stu-id="cbec6-118">This tutorial assumes that you have finished the [Hello world](hello-world.yml) lesson.</span></span>

## <a name="branches-and-loopsbranches-and-loops-localmd"></a>[<span data-ttu-id="cbec6-119">分支和循环</span><span class="sxs-lookup"><span data-stu-id="cbec6-119">Branches and loops</span></span>](branches-and-loops-local.md)

<span data-ttu-id="cbec6-120">在[分支和循环](branches-and-loops-local.md)教程中，将了解根据变量中存储的值选择不同代码执行路径的基础知识。</span><span class="sxs-lookup"><span data-stu-id="cbec6-120">The [Branches and loops](branches-and-loops-local.md) tutorial teaches the basics of selecting different paths of code execution based on the values stored in variables.</span></span> <span data-ttu-id="cbec6-121">读者将学习控制流的基础知识，这是程序决定选择不同操作的基本依据。</span><span class="sxs-lookup"><span data-stu-id="cbec6-121">You'll learn the basics of control flow, which is the basis of how programs make decisions and choose different actions.</span></span>

<span data-ttu-id="cbec6-122">若要更好地学习本教程，需要先完成 [Hello World](hello-world.yml) 和 [C# 中的数字](numbers-in-csharp-local.md)课程。</span><span class="sxs-lookup"><span data-stu-id="cbec6-122">This tutorial assumes that you have finished the [Hello world](hello-world.yml) and [Numbers in C#](numbers-in-csharp-local.md) lessons.</span></span>

## <a name="list-collectionarrays-and-collectionsmd"></a>[<span data-ttu-id="cbec6-123">列表集合</span><span class="sxs-lookup"><span data-stu-id="cbec6-123">List collection</span></span>](arrays-and-collections.md)

<span data-ttu-id="cbec6-124">[列表集合](arrays-and-collections.md)课程将介绍存储一系列数据的列表集合类型。</span><span class="sxs-lookup"><span data-stu-id="cbec6-124">The [List collection](arrays-and-collections.md) lesson gives you a tour of the List collection type that stores sequences of data.</span></span> <span data-ttu-id="cbec6-125">读者将学习如何添加和删除项、如何搜索项，以及如何对列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="cbec6-125">You'll learn how to add and remove items, search for items, and sort the lists.</span></span> <span data-ttu-id="cbec6-126">读者将探索各种列表。</span><span class="sxs-lookup"><span data-stu-id="cbec6-126">You'll explore different kinds of lists.</span></span> 

<span data-ttu-id="cbec6-127">若要更好地学习本教程，需要已完成上面列出的课程。</span><span class="sxs-lookup"><span data-stu-id="cbec6-127">This tutorial assumes that you have finished the lessons listed above.</span></span>

## <a name="introduction-to-classesintroduction-to-classesmd"></a>[<span data-ttu-id="cbec6-128">类简介</span><span class="sxs-lookup"><span data-stu-id="cbec6-128">Introduction to classes</span></span>](introduction-to-classes.md)

<span data-ttu-id="cbec6-129">只能在计算机上使用自己的本地开发环境和 .NET Core 演练最后一个 C# 简介教程。</span><span class="sxs-lookup"><span data-stu-id="cbec6-129">This final introduction to C# tutorial is only available to run on your machine, using your own local development environment and .NET Core.</span></span>
<span data-ttu-id="cbec6-130">读者将生成控制台应用程序，并了解 C# 语言中面向对象的基本功能的工作原理。</span><span class="sxs-lookup"><span data-stu-id="cbec6-130">You'll build a console application and see the basic object-oriented features that are part of the C# language.</span></span>
