---
title: 编写事务应用程序
ms.date: 03/30/2017
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
ms.openlocfilehash: 318771c83a5b7ebc0f3fb2bb8c59240269a2dea9
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205824"
---
# <a name="writing-a-transactional-application"></a><span data-ttu-id="9d27a-102">编写事务应用程序</span><span class="sxs-lookup"><span data-stu-id="9d27a-102">Writing a Transactional Application</span></span>
<span data-ttu-id="9d27a-103">作为事务应用程序程序员，您可以利用 <xref:System.Transactions> 命名空间所提供的两种编程模型来创建事务。</span><span class="sxs-lookup"><span data-stu-id="9d27a-103">As a transactional application programmer, you can take advantage of the two programming models provided by the <xref:System.Transactions> namespace to create a transaction.</span></span> <span data-ttu-id="9d27a-104">通过使用类, 可以使用显式编程模型<xref:System.Transactions.Transaction> , 或者通过<xref:System.Transactions.TransactionScope>使用类, 通过基础结构自动管理事务。</span><span class="sxs-lookup"><span data-stu-id="9d27a-104">You can utilize the explicit programming model by using the <xref:System.Transactions.Transaction> class, or the implicit programming model in which transactions are automatically managed by the infrastructure, by using the <xref:System.Transactions.TransactionScope> class.</span></span> <span data-ttu-id="9d27a-105">建议使用隐式事务模型进行开发。</span><span class="sxs-lookup"><span data-stu-id="9d27a-105">We recommend that you use the implicit transaction model for development.</span></span> <span data-ttu-id="9d27a-106">可以在[使用事务范围实现隐式事务](implementing-an-implicit-transaction-using-transaction-scope.md)主题中找到有关如何使用事务范围的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9d27a-106">You can find more information on how to use a transaction scope in the [Implementing an Implicit Transaction using Transaction Scope](implementing-an-implicit-transaction-using-transaction-scope.md) topic.</span></span>  
  
 <span data-ttu-id="9d27a-107">这两种模型都支持在程序达到一致状态时提交事务。</span><span class="sxs-lookup"><span data-stu-id="9d27a-107">Both models support committing a transaction when the program reaches a consistent state.</span></span> <span data-ttu-id="9d27a-108">如果提交成功，就会永久提交事务。</span><span class="sxs-lookup"><span data-stu-id="9d27a-108">If the commit succeeds, the transaction is durably committed.</span></span> <span data-ttu-id="9d27a-109">如果提交失败，事务就会中止。</span><span class="sxs-lookup"><span data-stu-id="9d27a-109">If the commit fails, the transaction aborts.</span></span> <span data-ttu-id="9d27a-110">如果应用程序无法成功完成事务，则会尝试中止并撤消事务的效果。</span><span class="sxs-lookup"><span data-stu-id="9d27a-110">If the application program cannot successfully complete the transaction, it attempts to abort and undo the transaction's effects.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9d27a-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="9d27a-111">In This Section</span></span>  
  
### <a name="creating-a-transaction"></a><span data-ttu-id="9d27a-112">创建事务</span><span class="sxs-lookup"><span data-stu-id="9d27a-112">Creating a Transaction</span></span>  
 <span data-ttu-id="9d27a-113"><xref:System.Transactions> 命名空间提供了两种用于创建事务的模型。</span><span class="sxs-lookup"><span data-stu-id="9d27a-113">The <xref:System.Transactions> namespace provides two models for creating a transaction.</span></span> <span data-ttu-id="9d27a-114">下列主题对这两种模型进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="9d27a-114">These models are covered in the following topics.</span></span>  
  
 [<span data-ttu-id="9d27a-115">使用事务范围实现隐式事务</span><span class="sxs-lookup"><span data-stu-id="9d27a-115">Implementing an Implicit Transaction using Transaction Scope</span></span>](implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 <span data-ttu-id="9d27a-116">描述 <xref:System.Transactions> 命名空间如何支持使用 <xref:System.Transactions.TransactionScope> 类创建隐式事务。</span><span class="sxs-lookup"><span data-stu-id="9d27a-116">Describes how the <xref:System.Transactions> namespace supports creating implicit transactions using the <xref:System.Transactions.TransactionScope> class.</span></span>  
  
 [<span data-ttu-id="9d27a-117">使用 CommittableTransaction 实现显式事务</span><span class="sxs-lookup"><span data-stu-id="9d27a-117">Implementing an Explicit Transaction using CommittableTransaction</span></span>](implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 <span data-ttu-id="9d27a-118">描述 <xref:System.Transactions> 命名空间如何支持使用 <xref:System.Transactions.CommittableTransaction> 类创建显式事务。</span><span class="sxs-lookup"><span data-stu-id="9d27a-118">Describes how the <xref:System.Transactions> namespace supports creating explicit transactions using the <xref:System.Transactions.CommittableTransaction> class.</span></span>  
  
### <a name="escalating-transaction-management"></a><span data-ttu-id="9d27a-119">升级事务管理</span><span class="sxs-lookup"><span data-stu-id="9d27a-119">Escalating Transaction Management</span></span>  
 <span data-ttu-id="9d27a-120">当事务需要访问其他应用程序域中的资源时，或者要登记到其他持久资源管理器时，事务会自动升级为由 MSDTC 管理。</span><span class="sxs-lookup"><span data-stu-id="9d27a-120">When a transaction needs to access a resource in another application domain, or if you want to enlist in another durable resource manager, the transaction is automatically escalated to be managed by the MSDTC.</span></span> <span data-ttu-id="9d27a-121">事务升级在[事务管理升级](transaction-management-escalation.md)主题中介绍。</span><span class="sxs-lookup"><span data-stu-id="9d27a-121">Transaction escalation is covered in the [Transaction Management Escalation](transaction-management-escalation.md) topic.</span></span>  
  
### <a name="concurrency"></a><span data-ttu-id="9d27a-122">并发</span><span class="sxs-lookup"><span data-stu-id="9d27a-122">Concurrency</span></span>  
 <span data-ttu-id="9d27a-123">使用[DependentTransaction 管理并发](managing-concurrency-with-dependenttransaction.md)的主题演示了如何使用<xref:System.Transactions.DependentTransaction>类在异步任务之间实现并发。</span><span class="sxs-lookup"><span data-stu-id="9d27a-123">The topic [Managing Concurrency with DependentTransaction](managing-concurrency-with-dependenttransaction.md) demonstrates how concurrency can be achieved between asynchronous tasks by using the <xref:System.Transactions.DependentTransaction> class.</span></span>  
  
### <a name="com-interop"></a><span data-ttu-id="9d27a-124">COM+ 互操作</span><span class="sxs-lookup"><span data-stu-id="9d27a-124">COM+ Interop</span></span>  
 <span data-ttu-id="9d27a-125">主题[与企业服务和 COM + 事务的互操作性](interoperability-with-enterprise-services-and-com-transactions.md)说明了如何使分布式事务与 com + 事务交互。</span><span class="sxs-lookup"><span data-stu-id="9d27a-125">The topic [Interoperability with Enterprise Services and COM+ Transactions](interoperability-with-enterprise-services-and-com-transactions.md) illustrates how you can make your distributed transactions interact with COM+ transactions.</span></span>  
  
### <a name="diagnostics"></a><span data-ttu-id="9d27a-126">诊断</span><span class="sxs-lookup"><span data-stu-id="9d27a-126">Diagnostics</span></span>  
 <span data-ttu-id="9d27a-127">[诊断跟踪](diagnostic-traces.md)介绍了如何使用<xref:System.Transactions>基础结构所生成的跟踪代码对应用程序中的错误进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="9d27a-127">[Diagnostic Traces](diagnostic-traces.md) describes how you can use the trace codes that are generated by the <xref:System.Transactions> infrastructure to troubleshoot errors in your applications.</span></span>  
  
### <a name="working-within-aspnet"></a><span data-ttu-id="9d27a-128">使用 ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9d27a-128">Working within ASP.NET</span></span>  
 <span data-ttu-id="9d27a-129">[ASP.NET 主题中的 Using system.object](using-system-transactions-in-aspnet.md)介绍了如何在 ASP.NET 应用程序中<xref:System.Transactions>成功使用。</span><span class="sxs-lookup"><span data-stu-id="9d27a-129">The [Using System.Transactions in ASP.NET](using-system-transactions-in-aspnet.md) topic describes how you can successfully use <xref:System.Transactions> inside an ASP.NET application.</span></span>
