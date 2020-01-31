---
title: 控件中的多线程处理
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: 79832e12a10f02c909d2a28270594bcb4ea68656
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742142"
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="b2fcc-102">Windows Forms 컨트롤의 다중 스레딩</span><span class="sxs-lookup"><span data-stu-id="b2fcc-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="b2fcc-103">在许多应用程序中，你可以通过在另一个线程上执行耗时的操作，使你的用户界面（UI）更快地响应。</span><span class="sxs-lookup"><span data-stu-id="b2fcc-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="b2fcc-104">许多工具可用于多线程处理 Windows 窗体控件，包括 <xref:System.Threading> 命名空间、<xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> 方法和 `BackgroundWorker` 组件。</span><span class="sxs-lookup"><span data-stu-id="b2fcc-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2fcc-105">`BackgroundWorker` 组件将替换功能并将其添加到 <xref:System.Threading> 命名空间和 <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> 方法;但是，如果您选择，这些将保留以实现向后兼容性和将来使用。</span><span class="sxs-lookup"><span data-stu-id="b2fcc-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="b2fcc-106">有关详细信息，请参阅[BackgroundWorker 组件概述](backgroundworker-component-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b2fcc-106">For more information, see [BackgroundWorker Component Overview](backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b2fcc-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="b2fcc-107">In This Section</span></span>  
 [<span data-ttu-id="b2fcc-108">방법: 스레드로부터 안전한 방식으로 Windows Forms 컨트롤 호출</span><span class="sxs-lookup"><span data-stu-id="b2fcc-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="b2fcc-109">演示如何对 Windows 窗体控件进行线程安全的调用。</span><span class="sxs-lookup"><span data-stu-id="b2fcc-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="b2fcc-110">방법: 백그라운드 스레드를 사용하여 파일 검색</span><span class="sxs-lookup"><span data-stu-id="b2fcc-110">How to: Use a Background Thread to Search for Files</span></span>](how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="b2fcc-111">演示如何使用 <xref:System.Threading> 命名空间和 <xref:System.Windows.Forms.Control.BeginInvoke%2A> 方法以异步方式搜索文件。</span><span class="sxs-lookup"><span data-stu-id="b2fcc-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b2fcc-112">참조</span><span class="sxs-lookup"><span data-stu-id="b2fcc-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="b2fcc-113">记录一个组件，该组件封装用于异步操作的工作线程。</span><span class="sxs-lookup"><span data-stu-id="b2fcc-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="b2fcc-114">记录如何以异步方式加载声音。</span><span class="sxs-lookup"><span data-stu-id="b2fcc-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="b2fcc-115">记录如何以异步方式加载图像。</span><span class="sxs-lookup"><span data-stu-id="b2fcc-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b2fcc-116">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="b2fcc-116">Related Sections</span></span>  
 [<span data-ttu-id="b2fcc-117">방법: 백그라운드에서 작업 실행</span><span class="sxs-lookup"><span data-stu-id="b2fcc-117">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="b2fcc-118">演示如何使用 <xref:System.ComponentModel.BackgroundWorker> 组件执行耗时的操作。</span><span class="sxs-lookup"><span data-stu-id="b2fcc-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="b2fcc-119">BackgroundWorker 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="b2fcc-119">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="b2fcc-120">提供一些主题，这些主题介绍如何使用 <xref:System.ComponentModel.BackgroundWorker> 组件进行异步操作。</span><span class="sxs-lookup"><span data-stu-id="b2fcc-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
