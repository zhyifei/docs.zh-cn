---
title: "F# 指南"
description: "本指南提供有关 F # 中，在.NET 运行的函数编程语言的各种学习资料的概述。"
author: jackfoxy
ms.author: phcart
ms.date: 03/19/2018
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ea27fb37-dad1-4bd4-a3cc-4f5c70767ae9
ms.openlocfilehash: 8be5ac5090e10ae9270e7eec529bd9b7c3c663fb
ms.sourcegitcommit: 32172ca05d5dcce7ef3d327b9c8639c736e0fe2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2018
---
# <a name="f-guide"></a>F# 指南

F # 是一种功能的编程语言.NET 上运行。 它还具有对对象，blend 功能和对象编程的任何问题的实际解决方案让你完全支持。

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

F # 即将其核心的工作效率。 对 F # 的工具支持是无处不在和完整的高级功能。

## <a name="learning-f"></a>学习 F # #

[F # 的教程](tour.md)及大量代码示例的主要语言功能的概述。 如果你不熟悉 F # 并想要感受语言的工作原理，则建议这样。

[要开始使用 Visual Studio 中的 F #](get-started/get-started-visual-studio.md)如果要在 Windows 上的虚拟机和模板，需要完整的 Visual Studio IDE （Integraded 开发环境） 体验。

[开始使用 Visual Studio 中的 F # 适用于 Mac](get-started/get-started-with-visual-studio-for-mac.md)如果是在 macOS 上并想要使用 Visual Studio IDE。

[要开始使用 Visual Studio 代码中的 F #](get-started/get-started-vscode.md)如果所需的轻量跨平台和功能打包 IDE 体验。

[要开始使用 F # 使用.NET 核心 CLI](get-started/get-started-command-line.md)如果你想要使用命令行工具。

## <a name="references"></a>参考资料

[F # 语言参考](language-reference/index.md)是官方、 全面引用所有 F # 语言功能。 每篇文章说明了的语法，并显示代码示例。 可以使用内容的表中的筛选器栏以查找特定的文章。

[F # 核心库参考](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference)为 F # 核心库的 API 参考。

## <a name="additional-guides"></a>附加指南

[F # 乐趣和利润](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/)是有关学习 F # 的全面且非常详细书。 其内容和作者均由 F # 社区钟爱。 目标受众是主要开发人员提供面向对象编程背景。

[F # 编程 Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming)是有关学习 F # wikibook。 它也是在 F # 社区的产品。 目标受众是那些不熟悉 F # 中，具有很少的面向对象编程背景的人员。

## <a name="learn-f-through-videos"></a>了解 F # 整个视频

[YouTube 上的 F # 教程](https://www.youtube.com/watch?v=c7eNDJN758U)将极佳介绍 F # 使用 Visual Studio、 1.5 小时内显示大量很好示例。 目标受众是那些不熟悉 F # 的 Visual Studio 开发人员。

[F # 的编程简介](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC)是一种很好的视频系列 Visual Studio Code 用作主要编辑器。 视频系列从头开始和结束的构建基于文本的 RPG 视频游戏。 目标受众是首选 Visual Studio Code （或的轻型 IDE） 以及对 F # 不熟悉的开发人员。

[What's New in 的 F # 的开发的 Visual Studio 2017](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers)是视频课程，F # 在 Visual Studio 2017 中显示的一些较新的功能。 目标受众是那些不熟悉 F # 的 Visual Studio 开发人员。

## <a name="other-useful-resources"></a>其他有用的资源

[F # 代码段网站](http://www.fssnip.net)包含的代码片段演示如何执行几乎任何操作在 F # 中，从绝对初学者到非常高级的代码段大规模集。

[F # 软件 Foundation Slack](http://fsharp.org/guides/slack/)是一个很好，新手设计和专家相似，就是高度处于活动状态，并且具有一些世界上最最佳 F # 程序员可用于聊天。 我们强烈建议联接。

## <a name="the-f-software-foundation"></a>F# 软件基金会

尽管 Microsoft 是主 F # 语言和 Visual Studio 中的其工具的开发人员，F # 还支持独立的基础，F # 软件 Foundation (FSSF)。

F# 软件基金会的任务是提升、保护和改进 F# 编程语言，以及支持和促进国际化的多元 F# 程序员社区的成长。

若要了解详细信息并参与，请查看 [fsharp.org](http://fsharp.org)。可以自由地加入，和 F # 开发人员 foundation 中的网络是你不想要错过的东西 ！
