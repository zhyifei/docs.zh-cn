---
title: "并发编程 - C# 指南"
description: "了解如何并行运行任务（很可能占用大量 CPU）"
keywords: "C#, 异步, 占用大量 CPU, 网络倾向"
ms.date: 08/24/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 0f8b42de-858a-44a3-87d9-998211f26377
redirect_url: /dotnet/csharp/tutorials/index
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 00cf3b04178ca48c9f8f35eb16bc216389e6b272
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="-concurrent-programming"></a><span data-ttu-id="600d9-104">🔧 并发编程</span><span class="sxs-lookup"><span data-stu-id="600d9-104">🔧 Concurrent Programming</span></span>

> <span data-ttu-id="600d9-105">**注意**</span><span class="sxs-lookup"><span data-stu-id="600d9-105">**Note**</span></span>
> 
> <span data-ttu-id="600d9-106">尚未编写此主题！</span><span class="sxs-lookup"><span data-stu-id="600d9-106">This topic hasn’t been written yet!</span></span> 
>
> <span data-ttu-id="600d9-107">欢迎提供建议，以帮助我们确定范围和方法。</span><span class="sxs-lookup"><span data-stu-id="600d9-107">We welcome your input to help shape the scope and approach.</span></span> <span data-ttu-id="600d9-108">可在 GitHub 处跟踪有关此[问题](https://github.com/dotnet/docs/issues/953)的状态并提供相关建议。</span><span class="sxs-lookup"><span data-stu-id="600d9-108">You can track the status and provide input on this [issue](https://github.com/dotnet/docs/issues/953) at GitHub.</span></span>
> 
> <span data-ttu-id="600d9-109">如果想要查看此主题的早期草稿和概述，请就此问题留下包含联系信息的备注。</span><span class="sxs-lookup"><span data-stu-id="600d9-109">If you would like to review early drafts and outlines of this topic, please leave a note with your contact information in the issue.</span></span>
>
> <span data-ttu-id="600d9-110">了解如何参与 [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md) 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="600d9-110">Learn more about how you can contribute on [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>
>

