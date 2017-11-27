---
title: "Windows 窗体控件中的多线程处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c4651ca9707dcf0fac2edea0f004275cfcf18cf2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="5d6e2-102">Windows 窗体控件中的多线程处理</span><span class="sxs-lookup"><span data-stu-id="5d6e2-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="5d6e2-103">在许多应用程序，你可以进行用户界面 (UI) 更快地响应执行耗时的操作在另一个线程上。</span><span class="sxs-lookup"><span data-stu-id="5d6e2-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="5d6e2-104">有多种工具都是可用于多线程处理你的 Windows 窗体控件，包括<xref:System.Threading>命名空间，<xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType>方法，与`BackgroundWorker`组件。</span><span class="sxs-lookup"><span data-stu-id="5d6e2-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d6e2-105">`BackgroundWorker`组件替换，并添加了功能<xref:System.Threading>命名空间和<xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType>方法; 但是，这些会保留向后兼容性和将来使用，如果你选择。</span><span class="sxs-lookup"><span data-stu-id="5d6e2-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="5d6e2-106">有关详细信息，请参阅[BackgroundWorker 组件概述](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5d6e2-106">For more information, see [BackgroundWorker Component Overview](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5d6e2-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="5d6e2-107">In This Section</span></span>  
 [<span data-ttu-id="5d6e2-108">如何：对 Windows 窗体控件执行线程安全调用</span><span class="sxs-lookup"><span data-stu-id="5d6e2-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="5d6e2-109">演示如何使 Windows 窗体控件的线程安全调用。</span><span class="sxs-lookup"><span data-stu-id="5d6e2-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="5d6e2-110">如何：使用后台线程搜索文件</span><span class="sxs-lookup"><span data-stu-id="5d6e2-110">How to: Use a Background Thread to Search for Files</span></span>](../../../../docs/framework/winforms/controls/how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="5d6e2-111">演示如何使用<xref:System.Threading>命名空间和<xref:System.Windows.Forms.Control.BeginInvoke%2A>方法来以异步方式搜索文件。</span><span class="sxs-lookup"><span data-stu-id="5d6e2-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5d6e2-112">参考</span><span class="sxs-lookup"><span data-stu-id="5d6e2-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="5d6e2-113">记录封装工作线程为异步操作的组件。</span><span class="sxs-lookup"><span data-stu-id="5d6e2-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="5d6e2-114">介绍如何异步加载声音。</span><span class="sxs-lookup"><span data-stu-id="5d6e2-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="5d6e2-115">介绍如何以异步方式加载映像。</span><span class="sxs-lookup"><span data-stu-id="5d6e2-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5d6e2-116">相关章节</span><span class="sxs-lookup"><span data-stu-id="5d6e2-116">Related Sections</span></span>  
 [<span data-ttu-id="5d6e2-117">如何：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="5d6e2-117">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="5d6e2-118">演示如何执行耗时的操作与<xref:System.ComponentModel.BackgroundWorker>组件。</span><span class="sxs-lookup"><span data-stu-id="5d6e2-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="5d6e2-119">BackgroundWorker 组件概述</span><span class="sxs-lookup"><span data-stu-id="5d6e2-119">BackgroundWorker Component Overview</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 <span data-ttu-id="5d6e2-120">提供一些主题，介绍如何使用<xref:System.ComponentModel.BackgroundWorker>组件为异步操作。</span><span class="sxs-lookup"><span data-stu-id="5d6e2-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
