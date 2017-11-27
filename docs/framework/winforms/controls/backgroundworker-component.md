---
title: "BackgroundWorker 组件"
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
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: bef7b0ab-ce57-475a-a2d6-fb8a702a9417
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cbcbc786c19ad1af74114915b0fd0689d466fcbe
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="backgroundworker-component"></a><span data-ttu-id="30ae9-102">BackgroundWorker 组件</span><span class="sxs-lookup"><span data-stu-id="30ae9-102">BackgroundWorker Component</span></span>
<span data-ttu-id="30ae9-103">`BackgroundWorker`组件使你的窗体或控件异步运行操作。</span><span class="sxs-lookup"><span data-stu-id="30ae9-103">The `BackgroundWorker` component enables your form or control to run an operation asynchronously.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="30ae9-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="30ae9-104">In This Section</span></span>  
 [<span data-ttu-id="30ae9-105">BackgroundWorker 组件概述</span><span class="sxs-lookup"><span data-stu-id="30ae9-105">BackgroundWorker Component Overview</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 <span data-ttu-id="30ae9-106">描述`BackgroundWorker`组件，这将使您能够执行耗时的操作以异步方式 （"在后台"），不同于你的应用程序的主 UI 线程的线程上。</span><span class="sxs-lookup"><span data-stu-id="30ae9-106">Describes the `BackgroundWorker` component, which gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span>  
  
 [<span data-ttu-id="30ae9-107">演练：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="30ae9-107">Walkthrough: Running an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)  
 <span data-ttu-id="30ae9-108">演示如何使用`BackgroundWorker`组件在设计器中运行单独的线程上耗时的操作。</span><span class="sxs-lookup"><span data-stu-id="30ae9-108">Demonstrates how to use the `BackgroundWorker` component in the designer to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="30ae9-109">如何：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="30ae9-109">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="30ae9-110">演示如何使用`BackgroundWorker`组件以运行在单独线程上耗时的操作。</span><span class="sxs-lookup"><span data-stu-id="30ae9-110">Demonstrates how to use the `BackgroundWorker` component to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="30ae9-111">演练：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="30ae9-111">Walkthrough: Implementing a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="30ae9-112">创建应用程序使用的设计器以异步方式执行数学运算。</span><span class="sxs-lookup"><span data-stu-id="30ae9-112">Creates an application using the designer that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="30ae9-113">如何：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="30ae9-113">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="30ae9-114">创建的应用程序以异步方式执行数学运算。</span><span class="sxs-lookup"><span data-stu-id="30ae9-114">Creates an application that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="30ae9-115">如何：在后台下载文件</span><span class="sxs-lookup"><span data-stu-id="30ae9-115">How to: Download a File in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-download-a-file-in-the-background.md)  
 <span data-ttu-id="30ae9-116">演示如何使用`BackgroundWorker`组件要下载在单独线程上的文件。</span><span class="sxs-lookup"><span data-stu-id="30ae9-116">Demonstrates how to use the `BackgroundWorker` component to download a file on a separate thread.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="30ae9-117">参考</span><span class="sxs-lookup"><span data-stu-id="30ae9-117">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="30ae9-118">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="30ae9-118">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 <span data-ttu-id="30ae9-119">描述保存数据的类型<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>事件。</span><span class="sxs-lookup"><span data-stu-id="30ae9-119">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span>  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 <span data-ttu-id="30ae9-120">描述保存数据的类型<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件。</span><span class="sxs-lookup"><span data-stu-id="30ae9-120">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="30ae9-121">相关章节</span><span class="sxs-lookup"><span data-stu-id="30ae9-121">Related Sections</span></span>  
 [<span data-ttu-id="30ae9-122">基于事件的异步模式概述</span><span class="sxs-lookup"><span data-stu-id="30ae9-122">Event-based Asynchronous Pattern Overview</span></span>](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="30ae9-123">描述如何的异步模式提供多线程应用程序的优点同时隐藏了很多线程设计中固有的复杂问题。</span><span class="sxs-lookup"><span data-stu-id="30ae9-123">Describes how the asynchronous pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>
