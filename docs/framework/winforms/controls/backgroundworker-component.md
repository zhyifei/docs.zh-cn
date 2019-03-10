---
title: BackgroundWorker 组件
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: bef7b0ab-ce57-475a-a2d6-fb8a702a9417
ms.openlocfilehash: 0baf54d27cf33eef7e4df7019ee98b42eba40205
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710662"
---
# <a name="backgroundworker-component"></a><span data-ttu-id="aad20-102">BackgroundWorker 组件</span><span class="sxs-lookup"><span data-stu-id="aad20-102">BackgroundWorker Component</span></span>
<span data-ttu-id="aad20-103">`BackgroundWorker`组件使您的窗体或控件以异步方式运行操作。</span><span class="sxs-lookup"><span data-stu-id="aad20-103">The `BackgroundWorker` component enables your form or control to run an operation asynchronously.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aad20-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="aad20-104">In This Section</span></span>  
 [<span data-ttu-id="aad20-105">BackgroundWorker 组件概述</span><span class="sxs-lookup"><span data-stu-id="aad20-105">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="aad20-106">介绍`BackgroundWorker`组件，使您能够执行耗时的操作以异步方式 （"在后台"），在不同于应用程序的主 UI 线程的线程。</span><span class="sxs-lookup"><span data-stu-id="aad20-106">Describes the `BackgroundWorker` component, which gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span>  
  
 [<span data-ttu-id="aad20-107">演练：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="aad20-107">Walkthrough: Running an Operation in the Background</span></span>](walkthrough-running-an-operation-in-the-background.md)  
 <span data-ttu-id="aad20-108">演示如何使用`BackgroundWorker`组件在设计器中运行单独的线程上一个耗时的操作。</span><span class="sxs-lookup"><span data-stu-id="aad20-108">Demonstrates how to use the `BackgroundWorker` component in the designer to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="aad20-109">如何：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="aad20-109">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="aad20-110">演示如何使用`BackgroundWorker`组件来运行单独的线程上一个耗时的操作。</span><span class="sxs-lookup"><span data-stu-id="aad20-110">Demonstrates how to use the `BackgroundWorker` component to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="aad20-111">演练：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="aad20-111">Walkthrough: Implementing a Form That Uses a Background Operation</span></span>](walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="aad20-112">创建使用异步执行数学运算的设计器的应用程序。</span><span class="sxs-lookup"><span data-stu-id="aad20-112">Creates an application using the designer that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="aad20-113">如何：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="aad20-113">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="aad20-114">创建以异步方式执行数学计算的应用程序。</span><span class="sxs-lookup"><span data-stu-id="aad20-114">Creates an application that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="aad20-115">如何：下载在后台中的文件</span><span class="sxs-lookup"><span data-stu-id="aad20-115">How to: Download a File in the Background</span></span>](how-to-download-a-file-in-the-background.md)  
 <span data-ttu-id="aad20-116">演示如何使用`BackgroundWorker`组件下载单独的线程上的文件。</span><span class="sxs-lookup"><span data-stu-id="aad20-116">Demonstrates how to use the `BackgroundWorker` component to download a file on a separate thread.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="aad20-117">参考</span><span class="sxs-lookup"><span data-stu-id="aad20-117">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="aad20-118">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="aad20-118">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 <span data-ttu-id="aad20-119">介绍了保存的数据的类型<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>事件。</span><span class="sxs-lookup"><span data-stu-id="aad20-119">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span>  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 <span data-ttu-id="aad20-120">介绍了保存的数据的类型<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件。</span><span class="sxs-lookup"><span data-stu-id="aad20-120">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="aad20-121">相关章节</span><span class="sxs-lookup"><span data-stu-id="aad20-121">Related Sections</span></span>  
 [<span data-ttu-id="aad20-122">基于事件的异步模式概述</span><span class="sxs-lookup"><span data-stu-id="aad20-122">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="aad20-123">介绍如何异步模式提供多线程应用程序的优点而隐藏的许多复杂多线程设计中固有的问题。</span><span class="sxs-lookup"><span data-stu-id="aad20-123">Describes how the asynchronous pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>
