---
title: C# 简介 - 熟悉开发工具
description: 本文介绍用于在计算机上开发 C# 和 .NET 应用程序的工具的基本知识。
ms.date: 10/23/2018
ms.openlocfilehash: db0b3228272a17feaa11ec754fa0aa4952a0d1ee
ms.sourcegitcommit: a3db1a9eafca89f95ccf361bc1833b47fbb2bb30
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2019
ms.locfileid: "58920657"
---
# <a name="become-familiar-with-the-net-development-tools"></a><span data-ttu-id="8b7f0-103">熟悉 .NET 开发工具</span><span class="sxs-lookup"><span data-stu-id="8b7f0-103">Become familiar with the .NET development tools</span></span>

<span data-ttu-id="8b7f0-104">在计算机上演练教程的第一步是设置开发环境。</span><span class="sxs-lookup"><span data-stu-id="8b7f0-104">The first step in running a tutorial on your machine is to set up a development environment.</span></span>
<span data-ttu-id="8b7f0-105">.NET 主题 [10 分钟入门](https://www.microsoft.com/net/core)介绍了如何在 Mac、PC 或 Linux 上设置本地开发环境。</span><span class="sxs-lookup"><span data-stu-id="8b7f0-105">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

<span data-ttu-id="8b7f0-106">或者，也可以安装 [.NET Core SDK](https://www.microsoft.com/net/download) 和 [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="8b7f0-106">Alternatively, you can install the [.NET Core SDK](https://www.microsoft.com/net/download) and [Visual Studio Code](https://code.visualstudio.com/).</span></span>

## <a name="basic-application-development-flow"></a><span data-ttu-id="8b7f0-107">基本的应用程序开发流</span><span class="sxs-lookup"><span data-stu-id="8b7f0-107">Basic application development flow</span></span>

<span data-ttu-id="8b7f0-108">你将使用 [`dotnet new`](../../../core/tools/dotnet-new.md) 命令创建应用程序。</span><span class="sxs-lookup"><span data-stu-id="8b7f0-108">You'll create applications using the [`dotnet new`](../../../core/tools/dotnet-new.md) command.</span></span> <span data-ttu-id="8b7f0-109">此命令生成应用程序所需的文件和资产。</span><span class="sxs-lookup"><span data-stu-id="8b7f0-109">This command generates the files and assets necessary for your application.</span></span> <span data-ttu-id="8b7f0-110">C# 简介的所有教程都使用 `console` 应用程序类型。</span><span class="sxs-lookup"><span data-stu-id="8b7f0-110">The introduction to C# tutorials all use the `console` application type.</span></span> <span data-ttu-id="8b7f0-111">了解基础知识后，可以扩展到其他应用程序类型。</span><span class="sxs-lookup"><span data-stu-id="8b7f0-111">Once you've got the basics, you can expand to other application types.</span></span>

<span data-ttu-id="8b7f0-112">你将使用的其他命令是 [`dotnet build`](../../../core/tools/dotnet-build.md) 以生成可执行文件，还有 [`dotnet run`](../../../core/tools/dotnet-run.md) 以运行可执行文件。</span><span class="sxs-lookup"><span data-stu-id="8b7f0-112">The other commands you'll use are [`dotnet build`](../../../core/tools/dotnet-build.md) to build the executable, and [`dotnet run`](../../../core/tools/dotnet-run.md) to run the executable.</span></span>

## <a name="pick-your-tutorial"></a><span data-ttu-id="8b7f0-113">选择教程</span><span class="sxs-lookup"><span data-stu-id="8b7f0-113">Pick your tutorial</span></span>

<span data-ttu-id="8b7f0-114">可以从下列任一教程入手：</span><span class="sxs-lookup"><span data-stu-id="8b7f0-114">You can start with any of the following tutorials:</span></span>

## [<a name="numbers-in-c"></a><span data-ttu-id="8b7f0-115">C# 中的数字</span><span class="sxs-lookup"><span data-stu-id="8b7f0-115">Numbers in C#</span></span>](numbers-in-csharp-local.md)

<span data-ttu-id="8b7f0-116">在 [C# 中的数字](numbers-in-csharp-local.md)教程中，将了解计算机如何存储数字，以及如何对不同类型的数字执行计算。</span><span class="sxs-lookup"><span data-stu-id="8b7f0-116">In the [Numbers in C#](numbers-in-csharp-local.md) tutorial, you'll learn how computers store numbers and how to perform calculations with different numeric types.</span></span> <span data-ttu-id="8b7f0-117">读者将学习四舍五入的基础知识，以及如何使用 C# 执行数学运算。</span><span class="sxs-lookup"><span data-stu-id="8b7f0-117">You'll learn the basics of rounding and how to perform mathematical calculations using C#.</span></span>

<span data-ttu-id="8b7f0-118">若要更好地学习本教程，需要已完成 [Hello world](hello-world.yml) 课程。</span><span class="sxs-lookup"><span data-stu-id="8b7f0-118">This tutorial assumes that you have finished the [Hello world](hello-world.yml) lesson.</span></span>

## [<a name="branches-and-loops"></a><span data-ttu-id="8b7f0-119">分支和循环</span><span class="sxs-lookup"><span data-stu-id="8b7f0-119">Branches and loops</span></span>](branches-and-loops-local.md)

<span data-ttu-id="8b7f0-120">在[分支和循环](branches-and-loops-local.md)教程中，将了解根据变量中存储的值选择不同代码执行路径的基础知识。</span><span class="sxs-lookup"><span data-stu-id="8b7f0-120">The [Branches and loops](branches-and-loops-local.md) tutorial teaches the basics of selecting different paths of code execution based on the values stored in variables.</span></span> <span data-ttu-id="8b7f0-121">读者将学习控制流的基础知识，这是程序决定选择不同操作的基本依据。</span><span class="sxs-lookup"><span data-stu-id="8b7f0-121">You'll learn the basics of control flow, which is the basis of how programs make decisions and choose different actions.</span></span>

<span data-ttu-id="8b7f0-122">若要更好地学习本教程，需要先完成 [Hello World](hello-world.yml) 和 [C# 中的数字](numbers-in-csharp-local.md)课程。</span><span class="sxs-lookup"><span data-stu-id="8b7f0-122">This tutorial assumes that you have finished the [Hello world](hello-world.yml) and [Numbers in C#](numbers-in-csharp-local.md) lessons.</span></span>

## [<a name="list-collection"></a><span data-ttu-id="8b7f0-123">列表集合</span><span class="sxs-lookup"><span data-stu-id="8b7f0-123">List collection</span></span>](arrays-and-collections.md)

<span data-ttu-id="8b7f0-124">[列表集合](arrays-and-collections.md)课程将介绍存储一系列数据的列表集合类型。</span><span class="sxs-lookup"><span data-stu-id="8b7f0-124">The [List collection](arrays-and-collections.md) lesson gives you a tour of the List collection type that stores sequences of data.</span></span> <span data-ttu-id="8b7f0-125">读者将学习如何添加和删除项、如何搜索项，以及如何对列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="8b7f0-125">You'll learn how to add and remove items, search for items, and sort the lists.</span></span> <span data-ttu-id="8b7f0-126">读者将探索各种列表。</span><span class="sxs-lookup"><span data-stu-id="8b7f0-126">You'll explore different kinds of lists.</span></span> 

<span data-ttu-id="8b7f0-127">若要更好地学习本教程，需要已完成上面列出的课程。</span><span class="sxs-lookup"><span data-stu-id="8b7f0-127">This tutorial assumes that you have finished the lessons listed above.</span></span>

## [<a name="introduction-to-classes"></a><span data-ttu-id="8b7f0-128">类简介</span><span class="sxs-lookup"><span data-stu-id="8b7f0-128">Introduction to classes</span></span>](introduction-to-classes.md)

<span data-ttu-id="8b7f0-129">只能在计算机上使用自己的本地开发环境和 .NET Core 演练最后一个 C# 简介教程。</span><span class="sxs-lookup"><span data-stu-id="8b7f0-129">This final introduction to C# tutorial is only available to run on your machine, using your own local development environment and .NET Core.</span></span>
<span data-ttu-id="8b7f0-130">读者将生成控制台应用程序，并了解 C# 语言中面向对象的基本功能的工作原理。</span><span class="sxs-lookup"><span data-stu-id="8b7f0-130">You'll build a console application and see the basic object-oriented features that are part of the C# language.</span></span>
