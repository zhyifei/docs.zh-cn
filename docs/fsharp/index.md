---
title: F# 指南
description: '本指南提供有关 F # 中，在.NET 运行的函数编程语言的各种学习资料的概述。'
author: jackfoxy
ms.date: 03/19/2018
ms.openlocfilehash: cb829e904c006467e1470752b4fe8757ca694b05
ms.sourcegitcommit: 895c7602386a6dfe7ca4facce3d965b27e5c6e87
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2018
ms.locfileid: "34311996"
---
# <a name="f-guide"></a><span data-ttu-id="af002-103">F# 指南</span><span class="sxs-lookup"><span data-stu-id="af002-103">F# Guide</span></span>

<span data-ttu-id="af002-104">F # 是一种功能的编程语言.NET 上运行。</span><span class="sxs-lookup"><span data-stu-id="af002-104">F# is a functional programming language that runs on .NET.</span></span> <span data-ttu-id="af002-105">它还具有对对象，blend 功能和对象编程的任何问题的实际解决方案让你完全支持。</span><span class="sxs-lookup"><span data-stu-id="af002-105">It also has full support for objects, letting you blend functional and object programming for pragmatic solutions to any problem.</span></span>

```fsharp
open System // Get access to functionality in System namespace.

// Function: takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

// Use the EntryPoint attribute to run the program.
[<EntryPoint>]
let main args =
    // Define a list of names
    let names = [| "Don"; "Julia"; "Xi" |]
    
    // Print a fun greeting for each name!
    names
    |> Array.map getGreeting
    |> Array.iter (fun greeting -> printfn "%s" greeting)

    0
```

<span data-ttu-id="af002-106">F # 即将其核心的工作效率。</span><span class="sxs-lookup"><span data-stu-id="af002-106">F# is about productivity at its heart.</span></span> <span data-ttu-id="af002-107">对 F # 的工具支持是无处不在和完整的高级功能。</span><span class="sxs-lookup"><span data-stu-id="af002-107">The tooling support for F# is ubiquitous and full of advanced features.</span></span>

## <a name="learning-f"></a><span data-ttu-id="af002-108">学习 F #</span><span class="sxs-lookup"><span data-stu-id="af002-108">Learning F#</span></span> #

<span data-ttu-id="af002-109">[F # 的教程](tour.md)及大量代码示例的主要语言功能的概述。</span><span class="sxs-lookup"><span data-stu-id="af002-109">[Tour of F#](tour.md) gives an overview of major language features with lots of code samples.</span></span> <span data-ttu-id="af002-110">如果你不熟悉 F # 并想要感受语言的工作原理，则建议这样。</span><span class="sxs-lookup"><span data-stu-id="af002-110">This is recommended if you are new to F# and want to get a feel for how the language works.</span></span>

<span data-ttu-id="af002-111">[要开始使用 Visual Studio 中的 F #](get-started/get-started-visual-studio.md)如果要在 Windows 上的虚拟机和模板，需要完整的 Visual Studio IDE （Integraded 开发环境） 体验。</span><span class="sxs-lookup"><span data-stu-id="af002-111">[Get started with F# in Visual Studio](get-started/get-started-visual-studio.md) if you're on Windows and want the full Visual Studio IDE (Integraded Development Environment) experience.</span></span>

<span data-ttu-id="af002-112">[开始使用 Visual Studio 中的 F # 适用于 Mac](get-started/get-started-with-visual-studio-for-mac.md)如果是在 macOS 上并想要使用 Visual Studio IDE。</span><span class="sxs-lookup"><span data-stu-id="af002-112">[Get started with F# in Visual Studio for Mac](get-started/get-started-with-visual-studio-for-mac.md) if you're on macOS and want to use a Visual Studio IDE.</span></span>

<span data-ttu-id="af002-113">[要开始使用 Visual Studio 代码中的 F #](get-started/get-started-vscode.md)如果所需的轻量跨平台和功能打包 IDE 体验。</span><span class="sxs-lookup"><span data-stu-id="af002-113">[Get Started with F# in Visual Studio Code](get-started/get-started-vscode.md) if you want a lightweight, cross-platform, and feature-packed IDE experience.</span></span>

<span data-ttu-id="af002-114">[要开始使用 F # 使用.NET 核心 CLI](get-started/get-started-command-line.md)如果你想要使用命令行工具。</span><span class="sxs-lookup"><span data-stu-id="af002-114">[Get started with F# with the .NET Core CLI](get-started/get-started-command-line.md) if you want to use command-line tools.</span></span>

<span data-ttu-id="af002-115">[F # 和 Xamarin 入门](https://docs.microsoft.com/xamarin/cross-platform/platform/fsharp/)移动使用 F # 的编程。</span><span class="sxs-lookup"><span data-stu-id="af002-115">[Get started with F# and Xamarin](https://docs.microsoft.com/xamarin/cross-platform/platform/fsharp/) for mobile programming with F#.</span></span>

<span data-ttu-id="af002-116">[用于 Azure 笔记本的 F #](https://notebooks.azure.com/Microsoft/libraries/samples/html/FSharp%20for%20Azure%20Notebooks.ipynb)是一个教程，帮助您了解可用的托管 Jupyter 笔记本中的 F #。</span><span class="sxs-lookup"><span data-stu-id="af002-116">[F# for Azure Notebooks](https://notebooks.azure.com/Microsoft/libraries/samples/html/FSharp%20for%20Azure%20Notebooks.ipynb) is a tutorial for learning F# in a free, hosted Jupyter Notebook.</span></span>

## <a name="references"></a><span data-ttu-id="af002-117">参考资料</span><span class="sxs-lookup"><span data-stu-id="af002-117">References</span></span>

<span data-ttu-id="af002-118">[F # 语言参考](language-reference/index.md)是官方、 全面引用所有 F # 语言功能。</span><span class="sxs-lookup"><span data-stu-id="af002-118">[F# Language Reference](language-reference/index.md) is the official, comprehensive reference for all F# language features.</span></span> <span data-ttu-id="af002-119">每篇文章说明了的语法，并显示代码示例。</span><span class="sxs-lookup"><span data-stu-id="af002-119">Each article explains the syntax and shows code samples.</span></span> <span data-ttu-id="af002-120">可以使用内容的表中的筛选器栏以查找特定的文章。</span><span class="sxs-lookup"><span data-stu-id="af002-120">You can use the filter bar in the table of contents to find specific articles.</span></span>

<span data-ttu-id="af002-121">[F # 核心库参考](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference)为 F # 核心库的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="af002-121">[F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) is the API reference for the F# Core Library.</span></span>


## <a name="additional-guides"></a><span data-ttu-id="af002-122">附加指南</span><span class="sxs-lookup"><span data-stu-id="af002-122">Additional guides</span></span>

<span data-ttu-id="af002-123">[F # 乐趣和利润](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/)是有关学习 F # 的全面且非常详细书。</span><span class="sxs-lookup"><span data-stu-id="af002-123">[F# for Fun and Profit](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) is a comprehensive and very detailed book on learning F#.</span></span> <span data-ttu-id="af002-124">其内容和作者均由 F # 社区钟爱。</span><span class="sxs-lookup"><span data-stu-id="af002-124">Its contents and author are beloved by the F# community.</span></span> <span data-ttu-id="af002-125">目标受众是主要开发人员提供面向对象编程背景。</span><span class="sxs-lookup"><span data-stu-id="af002-125">The target audience is primarily developers with an object oriented programming background.</span></span>

<span data-ttu-id="af002-126">[F # 编程 Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming)是有关学习 F # wikibook。</span><span class="sxs-lookup"><span data-stu-id="af002-126">[F# Programming Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming) is a wikibook about learning F#.</span></span> <span data-ttu-id="af002-127">它也是在 F # 社区的产品。</span><span class="sxs-lookup"><span data-stu-id="af002-127">It is also a product of the F# community.</span></span> <span data-ttu-id="af002-128">目标受众是那些不熟悉 F # 中，具有很少的面向对象编程背景的人员。</span><span class="sxs-lookup"><span data-stu-id="af002-128">The target audience is people who are new to F#, with a little bit of object oriented programming background.</span></span>

## <a name="learn-f-through-videos"></a><span data-ttu-id="af002-129">了解 F # 整个视频</span><span class="sxs-lookup"><span data-stu-id="af002-129">Learn F# through videos</span></span>

<span data-ttu-id="af002-130">[YouTube 上的 F # 教程](https://www.youtube.com/watch?v=c7eNDJN758U)将极佳介绍 F # 使用 Visual Studio、 1.5 小时内显示大量很好示例。</span><span class="sxs-lookup"><span data-stu-id="af002-130">[F# tutorial on YouTube](https://www.youtube.com/watch?v=c7eNDJN758U) is a great introduction to F# using Visual Studio, showing lots of great examples over the course of 1.5 hours.</span></span> <span data-ttu-id="af002-131">目标受众是那些不熟悉 F # 的 Visual Studio 开发人员。</span><span class="sxs-lookup"><span data-stu-id="af002-131">The target audience is Visual Studio developers who are new to F#.</span></span>

<span data-ttu-id="af002-132">[F # 的编程简介](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC)是一种很好的视频系列 Visual Studio Code 用作主要编辑器。</span><span class="sxs-lookup"><span data-stu-id="af002-132">[Introduction to Programming with F#](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) is a great video series that uses Visual Studio Code as the main editor.</span></span> <span data-ttu-id="af002-133">视频系列从头开始和结束的构建基于文本的 RPG 视频游戏。</span><span class="sxs-lookup"><span data-stu-id="af002-133">The video series starts from nothing and ends with building a text-based RPG video game.</span></span> <span data-ttu-id="af002-134">目标受众是首选 Visual Studio Code （或的轻型 IDE） 以及对 F # 不熟悉的开发人员。</span><span class="sxs-lookup"><span data-stu-id="af002-134">The target audience is developers who prefer Visual Studio Code (or a lightweight IDE) and are new to F#.</span></span>

<span data-ttu-id="af002-135">[What's New in 的 F # 的开发的 Visual Studio 2017](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers)是视频课程，F # 在 Visual Studio 2017 中显示的一些较新的功能。</span><span class="sxs-lookup"><span data-stu-id="af002-135">[What's New in Visual Studio 2017 for F# For Developers](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) is a video course that shows some of the newer features for F# in Visual Studio 2017.</span></span> <span data-ttu-id="af002-136">目标受众是那些不熟悉 F # 的 Visual Studio 开发人员。</span><span class="sxs-lookup"><span data-stu-id="af002-136">The target audience is Visual Studio developers who are new to F#.</span></span>

## <a name="other-useful-resources"></a><span data-ttu-id="af002-137">其他有用的资源</span><span class="sxs-lookup"><span data-stu-id="af002-137">Other useful resources</span></span>

<span data-ttu-id="af002-138">[F # 代码段网站](http://www.fssnip.net)包含的代码片段演示如何执行几乎任何操作在 F # 中，从绝对初学者到非常高级的代码段大规模集。</span><span class="sxs-lookup"><span data-stu-id="af002-138">The [F# Snippets Website](http://www.fssnip.net) contains a massive set of code snippets showing how to do just about anything in F#, ranging from absolute beginner to highly advanced snippets.</span></span>

<span data-ttu-id="af002-139">[F # 软件 Foundation Slack](http://fsharp.org/guides/slack/)是一个很好，新手设计和专家相似，就是高度处于活动状态，并且具有一些世界上最最佳 F # 程序员可用于聊天。</span><span class="sxs-lookup"><span data-stu-id="af002-139">The [F# Software Foundation Slack](http://fsharp.org/guides/slack/) is a great place for beginners and experts alike, is highly active, and has some of world's best F# programmers available for a chat.</span></span> <span data-ttu-id="af002-140">我们强烈建议联接。</span><span class="sxs-lookup"><span data-stu-id="af002-140">We highly recommend joining.</span></span>

## <a name="the-f-software-foundation"></a><span data-ttu-id="af002-141">F# 软件基金会</span><span class="sxs-lookup"><span data-stu-id="af002-141">The F# Software Foundation</span></span>

<span data-ttu-id="af002-142">尽管 Microsoft 是主 F # 语言和 Visual Studio 中的其工具的开发人员，F # 还支持独立的基础，F # 软件 Foundation (FSSF)。</span><span class="sxs-lookup"><span data-stu-id="af002-142">Although Microsoft is the primary developer of the F# language and its tools in Visual Studio, F# is also backed by an independent foundation, the F# Software Foundation (FSSF).</span></span>

<span data-ttu-id="af002-143">F# 软件基金会的任务是提升、保护和改进 F# 编程语言，以及支持和促进国际化的多元 F# 程序员社区的成长。</span><span class="sxs-lookup"><span data-stu-id="af002-143">The mission of the F# Software Foundation is to promote, protect, and advance the F# programming language, and to support and facilitate the growth of a diverse and international community of F# programmers.</span></span>

<span data-ttu-id="af002-144">若要了解详细信息并参与，请查看 [fsharp.org](http://fsharp.org)。可以自由地加入，和 F # 开发人员 foundation 中的网络是你不想要错过的东西 ！</span><span class="sxs-lookup"><span data-stu-id="af002-144">To learn more and get involved, check out [fsharp.org](http://fsharp.org). It's free to join, and the network of F# developers in the foundation is something you don't want to miss out on!</span></span>
