---
title: "异步操作"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7d32c3c-bf78-4bfc-a357-c9e82e4a4b3c
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b616a6cf08dd47a9e46e8e887efbc88469dedfd3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="asynchronous-operations"></a><span data-ttu-id="5808b-102">异步操作</span><span class="sxs-lookup"><span data-stu-id="5808b-102">Asynchronous Operations</span></span>
<span data-ttu-id="5808b-103">某些数据库操作（例如命令执行）可能要花费很长时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="5808b-103">Some database operations, such as command executions, can take significant time to complete.</span></span> <span data-ttu-id="5808b-104">在此类情况下，单线程应用程序必须阻塞其他操作，并且等待该命令完成，然后才可以继续执行它们自己的操作。</span><span class="sxs-lookup"><span data-stu-id="5808b-104">In such a case, single-threaded applications must block other operations and wait for the command to finish before they can continue their own operations.</span></span> <span data-ttu-id="5808b-105">比较而言，如果能够将长时间运行的操作分配给某个后台线程，就可以允许前台线程在整个操作期间保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="5808b-105">In contrast, being able to assign the long-running operation to a background thread allows the foreground thread to remain active throughout the operation.</span></span> <span data-ttu-id="5808b-106">例如，在 Windows 应用程序中，通过将长时间运行的操作委托给后台线程，可允许用户界面线程在操作执行时保持响应状态。</span><span class="sxs-lookup"><span data-stu-id="5808b-106">In a Windows application, for example, delegating the long-running operation to a background thread allows the user interface thread to remain responsive while the operation is executing.</span></span>  
  
 <span data-ttu-id="5808b-107">.NET Framework 提供若干标准异步设计模式，开发人员可以通过这些模式充分利用后台线程并释放用户界面线程或高优先级的线程以完成其他操作。</span><span class="sxs-lookup"><span data-stu-id="5808b-107">The .NET Framework provides several standard asynchronous design patterns that developers can use to take advantage of background threads and free the user interface or high-priority threads to complete other operations.</span></span> <span data-ttu-id="5808b-108">ADO.NET 在其 <xref:System.Data.SqlClient.SqlCommand> 类中支持相同的设计模式。</span><span class="sxs-lookup"><span data-stu-id="5808b-108">ADO.NET supports these same design patterns in its <xref:System.Data.SqlClient.SqlCommand> class.</span></span> <span data-ttu-id="5808b-109">具体而言，<xref:System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery%2A>、<xref:System.Data.SqlClient.SqlCommand.BeginExecuteReader%2A> 和 <xref:System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader%2A> 方法（与 <xref:System.Data.SqlClient.SqlCommand.EndExecuteNonQuery%2A>、<xref:System.Data.SqlClient.SqlCommand.EndExecuteReader%2A> 和 <xref:System.Data.SqlClient.SqlCommand.EndExecuteXmlReader%2A> 方法搭配）提供异步支持。</span><span class="sxs-lookup"><span data-stu-id="5808b-109">Specifically, the <xref:System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery%2A>, <xref:System.Data.SqlClient.SqlCommand.BeginExecuteReader%2A>, and <xref:System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader%2A> methods, paired with the <xref:System.Data.SqlClient.SqlCommand.EndExecuteNonQuery%2A>, <xref:System.Data.SqlClient.SqlCommand.EndExecuteReader%2A>, and <xref:System.Data.SqlClient.SqlCommand.EndExecuteXmlReader%2A> methods, provide the asynchronous support.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5808b-110">异步编程是 .NET Framework 的核心功能，并且 ADO.NET 充分利用了标准设计模式。</span><span class="sxs-lookup"><span data-stu-id="5808b-110">Asynchronous programming is a core feature of the .NET Framework, and ADO.NET takes full advantage of the standard design patterns.</span></span> <span data-ttu-id="5808b-111">有关不同的异步技术可供开发人员的详细信息，请参阅[异步调用同步方法](../../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)。</span><span class="sxs-lookup"><span data-stu-id="5808b-111">For more information about the different asynchronous techniques available to developers, see [Calling Synchronous Methods Asynchronously](../../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
 <span data-ttu-id="5808b-112">尽管将异步技术与 ADO.NET 功能一起使用没有什么新增的需特别注意的事项，但与 .NET Framework 的其他领域相比，很可能更多的开发人员将在 ADO.NET 中使用异步功能。</span><span class="sxs-lookup"><span data-stu-id="5808b-112">Although using asynchronous techniques with ADO.NET features does not add any special considerations, it is likely that more developers will use asynchronous features in ADO.NET than in other areas of the .NET Framework.</span></span> <span data-ttu-id="5808b-113">了解创建多线程应用程序的优缺点十分重要。</span><span class="sxs-lookup"><span data-stu-id="5808b-113">It is important to be aware of the benefits and pitfalls of creating multithreaded applications.</span></span> <span data-ttu-id="5808b-114">本节之后的那些示例指出了若干重要问题，开发人员在开发纳入了多线程功能的应用程序时将需要考虑这些问题。</span><span class="sxs-lookup"><span data-stu-id="5808b-114">The examples that follow in this section point out several important issues that developers will need to take into account when building applications that incorporate multithreaded functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5808b-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="5808b-115">In This Section</span></span>  
 [<span data-ttu-id="5808b-116">Windows 应用程序使用回调</span><span class="sxs-lookup"><span data-stu-id="5808b-116">Windows Applications Using Callbacks</span></span>](../../../../../docs/framework/data/adonet/sql/windows-applications-using-callbacks.md)  
 <span data-ttu-id="5808b-117">提供一个示例，演示如何安全地执行异步命令，并且通过单独线程正确处理与某一窗体及其内容的交互。</span><span class="sxs-lookup"><span data-stu-id="5808b-117">Provides an example demonstrating how to execute an asynchronous command safely, correctly handling interaction with a form and its contents from a separate thread.</span></span>  
  
 [<span data-ttu-id="5808b-118">使用等待句柄的 ASP.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="5808b-118">ASP.NET Applications Using Wait Handles</span></span>](../../../../../docs/framework/data/adonet/sql/aspnet-apps-using-wait-handles.md)  
 <span data-ttu-id="5808b-119">提供一个示例，演示如何从 ASP.NET 页执行多个并行命令，并且使用等待处理管理在所有命令都完成时的操作。</span><span class="sxs-lookup"><span data-stu-id="5808b-119">Provides an example demonstrating how to execute multiple concurrent commands from an ASP.NET page, using Wait handles to manage the operation at completion of all the commands.</span></span>  
  
 [<span data-ttu-id="5808b-120">在控制台应用程序中的轮询</span><span class="sxs-lookup"><span data-stu-id="5808b-120">Polling in Console Applications</span></span>](../../../../../docs/framework/data/adonet/sql/polling-in-console-applications.md)  
 <span data-ttu-id="5808b-121">提供一个示例，演示如何在控制台应用程序中使用轮询来等待异步命令执行的完成。</span><span class="sxs-lookup"><span data-stu-id="5808b-121">Provides an example demonstrating the use of polling to wait for the completion of an asynchronous command execution from a console application.</span></span> <span data-ttu-id="5808b-122">在类库或没有用户界面的其他应用程序中此技术同样有效。</span><span class="sxs-lookup"><span data-stu-id="5808b-122">This technique is also valid in a class library or other application without a user interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5808b-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5808b-123">See Also</span></span>  
 [<span data-ttu-id="5808b-124">SQL Server 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5808b-124">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="5808b-125">使用异步方式调用同步方法</span><span class="sxs-lookup"><span data-stu-id="5808b-125">Calling Synchronous Methods Asynchronously</span></span>](../../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 [<span data-ttu-id="5808b-126">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="5808b-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
