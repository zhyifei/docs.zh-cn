---
title: 如何：创建预先计算的任务
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, creating pre-computed
ms.assetid: a73eafa2-1f49-4106-a19e-997186029b58
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ce34e609dc9b1e2a5f1822ce27f65be74a636c86
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-pre-computed-tasks"></a><span data-ttu-id="d8840-102">如何：创建预先计算的任务</span><span class="sxs-lookup"><span data-stu-id="d8840-102">How to: Create Pre-Computed Tasks</span></span>
<span data-ttu-id="d8840-103">本文档介绍如何使用 <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> 方法检索缓存中包含的异步下载操作的结果。</span><span class="sxs-lookup"><span data-stu-id="d8840-103">This document describes how to use the <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> method to retrieve the results of asynchronous download operations that are held in a cache.</span></span> <span data-ttu-id="d8840-104"><xref:System.Threading.Tasks.Task.FromResult%2A> 方法返回一个将所提供的值作为其 <xref:System.Threading.Tasks.Task%601> 属性的已完成的 <xref:System.Threading.Tasks.Task%601.Result%2A> 对象。</span><span class="sxs-lookup"><span data-stu-id="d8840-104">The <xref:System.Threading.Tasks.Task.FromResult%2A> method returns a finished <xref:System.Threading.Tasks.Task%601> object that holds the provided value as its <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="d8840-105">执行返回 <xref:System.Threading.Tasks.Task%601> 对象的异步运算，且已计算该 <xref:System.Threading.Tasks.Task%601> 对象的结果时，此方法将十分有用。</span><span class="sxs-lookup"><span data-stu-id="d8840-105">This method is useful when you perform an asynchronous operation that returns a <xref:System.Threading.Tasks.Task%601> object, and the result of that <xref:System.Threading.Tasks.Task%601> object is already computed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8840-106">示例</span><span class="sxs-lookup"><span data-stu-id="d8840-106">Example</span></span>  
 <span data-ttu-id="d8840-107">下面的示例从 Web 下载字符串。</span><span class="sxs-lookup"><span data-stu-id="d8840-107">The following example downloads strings from the web.</span></span> <span data-ttu-id="d8840-108">它定义了 `DownloadStringAsync` 方法。</span><span class="sxs-lookup"><span data-stu-id="d8840-108">It defines the `DownloadStringAsync` method.</span></span> <span data-ttu-id="d8840-109">此方法从 Web 异步下载字符串。</span><span class="sxs-lookup"><span data-stu-id="d8840-109">This method downloads strings from the web asynchronously.</span></span> <span data-ttu-id="d8840-110">此示例还使用 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 对象来缓存先前操作的结果。</span><span class="sxs-lookup"><span data-stu-id="d8840-110">This example also uses a <xref:System.Collections.Concurrent.ConcurrentDictionary%602> object to cache the results of previous operations.</span></span> <span data-ttu-id="d8840-111">如果此缓存中包含输入的地址，`DownloadStringAsync` 会使用 <xref:System.Threading.Tasks.Task.FromResult%2A> 方法来生成包含位于该地址的内容的 <xref:System.Threading.Tasks.Task%601> 对象。</span><span class="sxs-lookup"><span data-stu-id="d8840-111">If the input address is held in this cache, `DownloadStringAsync` uses the <xref:System.Threading.Tasks.Task.FromResult%2A> method to produce a <xref:System.Threading.Tasks.Task%601> object that holds the content at that address.</span></span> <span data-ttu-id="d8840-112">否则，`DownloadStringAsync` 从 Web 下载文件并将结果添加到缓存中。</span><span class="sxs-lookup"><span data-stu-id="d8840-112">Otherwise, `DownloadStringAsync` downloads the file from the web and adds the result to the cache.</span></span>  
  
 [!code-csharp[TPL_CachedDownloads#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cacheddownloads/cs/cacheddownloads.cs#1)]
 [!code-vb[TPL_CachedDownloads#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cacheddownloads/vb/cacheddownloads.vb#1)]  
  
 <span data-ttu-id="d8840-113">此示例计算两次下载多个字符串需要的时间。</span><span class="sxs-lookup"><span data-stu-id="d8840-113">This example computes the time that is required to download multiple strings two times.</span></span> <span data-ttu-id="d8840-114">与第一组下载操作相比，第二组下载操作应该会花费较少的时间，因为结果已包含在缓存中。</span><span class="sxs-lookup"><span data-stu-id="d8840-114">The second set of download operations should take less time than the first set because the results are held in the cache.</span></span> <span data-ttu-id="d8840-115"><xref:System.Threading.Tasks.Task.FromResult%2A> 方法可以使 `DownloadStringAsync` 方法创建包含这些预计算结果的 <xref:System.Threading.Tasks.Task%601> 对象。</span><span class="sxs-lookup"><span data-stu-id="d8840-115">The <xref:System.Threading.Tasks.Task.FromResult%2A> method enables the `DownloadStringAsync` method to create <xref:System.Threading.Tasks.Task%601> objects that hold these pre-computed results.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d8840-116">编译代码</span><span class="sxs-lookup"><span data-stu-id="d8840-116">Compiling the Code</span></span>  
 <span data-ttu-id="d8840-117">复制示例代码，并将它粘贴到 Visual Studio 项目中，或粘贴到 `CachedDownloads.cs`（对于 Visual Basic，则为 `CachedDownloads.vb`）文件中，再在 Visual Studio 命令提示符窗口中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="d8840-117">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `CachedDownloads.cs` (`CachedDownloads.vb` for Visual Basic), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 <span data-ttu-id="d8840-118">Visual C#</span><span class="sxs-lookup"><span data-stu-id="d8840-118">Visual C#</span></span>  
  
 <span data-ttu-id="d8840-119">**csc.exe CachedDownloads.cs**</span><span class="sxs-lookup"><span data-stu-id="d8840-119">**csc.exe CachedDownloads.cs**</span></span>  
  
 <span data-ttu-id="d8840-120">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d8840-120">Visual Basic</span></span>  
  
 <span data-ttu-id="d8840-121">**vbc.exe CachedDownloads.vb**</span><span class="sxs-lookup"><span data-stu-id="d8840-121">**vbc.exe CachedDownloads.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d8840-122">可靠编程</span><span class="sxs-lookup"><span data-stu-id="d8840-122">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8840-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8840-123">See Also</span></span>  
 [<span data-ttu-id="d8840-124">基于任务的异步编程</span><span class="sxs-lookup"><span data-stu-id="d8840-124">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
