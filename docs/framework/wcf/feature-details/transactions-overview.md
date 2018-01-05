---
title: "Windows Communication Foundation 事务概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transactions [WCF]
- WCF, transactions
- Windows Communication Foundation, transactions
ms.assetid: c7757854-1207-4019-8b31-552578b7d570
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6fb90d0f93e9bdf7dd9779ffd5d4b1288ba56e7a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="windows-communication-foundation-transactions-overview"></a><span data-ttu-id="04c9c-102">Windows Communication Foundation 事务概述</span><span class="sxs-lookup"><span data-stu-id="04c9c-102">Windows Communication Foundation Transactions Overview</span></span>
<span data-ttu-id="04c9c-103">事务可提供一种分组方法，将一组操作分为单个不可分的执行单元。</span><span class="sxs-lookup"><span data-stu-id="04c9c-103">Transactions provide a way to group a set of actions or operations into a single indivisible unit of execution.</span></span> <span data-ttu-id="04c9c-104">事务是指具有下列属性的操作集合：</span><span class="sxs-lookup"><span data-stu-id="04c9c-104">A transaction is a collection of operations with the following properties:</span></span>  
  
-   <span data-ttu-id="04c9c-105">原子性。</span><span class="sxs-lookup"><span data-stu-id="04c9c-105">Atomicity.</span></span> <span data-ttu-id="04c9c-106">此属性可确保特定事务下完成的所有更新都已提交并保持持久，或所有这些更新都已中止并回滚到其先前状态。</span><span class="sxs-lookup"><span data-stu-id="04c9c-106">This ensures that either all of the updates completed under a specific transaction are committed and made durable or they are all aborted and rolled back to their previous state.</span></span>  
  
-   <span data-ttu-id="04c9c-107">一致性。</span><span class="sxs-lookup"><span data-stu-id="04c9c-107">Consistency.</span></span> <span data-ttu-id="04c9c-108">此属性可保证某一事务下所做的更改表示从一种一致状态转换到另一种一致状态。</span><span class="sxs-lookup"><span data-stu-id="04c9c-108">This guarantees that the changes made under a transaction represent a transformation from one consistent state to another.</span></span> <span data-ttu-id="04c9c-109">例如，将钱从支票帐户转移到存款帐户的事务并不改变整个银行帐户中的钱的总额。</span><span class="sxs-lookup"><span data-stu-id="04c9c-109">For example, a transaction that transfers money from a checking account to a savings account does not change the amount of money in the overall bank account.</span></span>  
  
-   <span data-ttu-id="04c9c-110">隔离。</span><span class="sxs-lookup"><span data-stu-id="04c9c-110">Isolation.</span></span> <span data-ttu-id="04c9c-111">此属性可防止事务遵循属于其他并发事务的未提交的更改。</span><span class="sxs-lookup"><span data-stu-id="04c9c-111">This prevents a transaction from observing uncommitted changes belonging to other concurrent transactions.</span></span> <span data-ttu-id="04c9c-112">隔离在确保一种事务不能对另一事务的执行产生意外的影响的同时，还提供一个抽象的并发。</span><span class="sxs-lookup"><span data-stu-id="04c9c-112">Isolation provides an abstraction of concurrency while ensuring one transaction cannot have an unexpected impact on the execution of another transaction.</span></span>  
  
-   <span data-ttu-id="04c9c-113">持续性。</span><span class="sxs-lookup"><span data-stu-id="04c9c-113">Durability.</span></span> <span data-ttu-id="04c9c-114">这意味着一旦提交对托管资源（如数据库记录）的更新，即使出现失败这些更新也会保持持久。</span><span class="sxs-lookup"><span data-stu-id="04c9c-114">This means that once committed, updates to managed resources (such as a database record) will be persistent in the face of failures.</span></span>  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="04c9c-115"> 提供一组丰富的功能，使您能够在 Web 服务应用程序中创建分布式事务。</span><span class="sxs-lookup"><span data-stu-id="04c9c-115"> provides a rich set of features that enable you to create distributed transactions in your Web service application.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="04c9c-116"> 实现对 WS-AtomicTransaction (WS-AT) 协议的支持，该协议使 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 应用程序能够将事务传输到可互操作应用程序中，例如使用第三方技术生成的可互操作 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="04c9c-116"> implements support for the WS-AtomicTransaction (WS-AT) protocol that enables [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications to flow transactions to interoperable applications, such as interoperable Web services built using third-party technology.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="04c9c-117"> 还实现对 OLE 事务协议的支持，可以在无需互操作功能以便实现事务流式处理的情况下使用该协议。</span><span class="sxs-lookup"><span data-stu-id="04c9c-117"> also implements support for the OLE Transactions protocol, which can be used in scenarios where you do not need interop functionality to enable transaction flow.</span></span>  
  
 <span data-ttu-id="04c9c-118">您可以使用应用程序配置文件来配置绑定以启用或禁用事务流，以及设置有关绑定的所需事务协定。</span><span class="sxs-lookup"><span data-stu-id="04c9c-118">You can use an application configuration file to configure bindings to enable or disable transaction flow, as well as set the desired transaction protocol on a binding.</span></span> <span data-ttu-id="04c9c-119">此外，你可以使用配置文件在服务级别设置事务超时值。</span><span class="sxs-lookup"><span data-stu-id="04c9c-119">In addition, you can set transaction time-outs at the service level using the configuration file.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="04c9c-120">[启用事务流](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)。</span><span class="sxs-lookup"><span data-stu-id="04c9c-120"> [Enabling Transaction Flow](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
 <span data-ttu-id="04c9c-121"><xref:System.ServiceModel> 命名空间中的事务属性允许您进行以下操作：</span><span class="sxs-lookup"><span data-stu-id="04c9c-121">Transaction attributes in the <xref:System.ServiceModel> namespace allow you to do the following:</span></span>  
  
-   <span data-ttu-id="04c9c-122">使用 <xref:System.ServiceModel.ServiceBehaviorAttribute> 属性配置事务超时值以及隔离级别的筛选。</span><span class="sxs-lookup"><span data-stu-id="04c9c-122">Configure transaction time-outs and isolation-level filtering using the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute.</span></span>  
  
-   <span data-ttu-id="04c9c-123">启用事务功能并使用 <xref:System.ServiceModel.OperationBehaviorAttribute> 属性配置事务完成行为。</span><span class="sxs-lookup"><span data-stu-id="04c9c-123">Enable transactions functionality and configure transaction completion behavior using the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute.</span></span>  
  
-   <span data-ttu-id="04c9c-124">使用协定方法上的 <xref:System.ServiceModel.ServiceContractAttribute> 和 <xref:System.ServiceModel.OperationContractAttribute> 属性来要求、允许或拒绝事务流。</span><span class="sxs-lookup"><span data-stu-id="04c9c-124">Use the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes on a contract method to require, allow or deny transaction flow.</span></span>  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="04c9c-125">[ServiceModel 事务属性](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="04c9c-125"> [ServiceModel Transaction Attributes](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04c9c-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="04c9c-126">See Also</span></span>  
 [<span data-ttu-id="04c9c-127">ServiceModel 事务特性</span><span class="sxs-lookup"><span data-stu-id="04c9c-127">ServiceModel Transaction Attributes</span></span>](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md)  
 [<span data-ttu-id="04c9c-128">启用事务流</span><span class="sxs-lookup"><span data-stu-id="04c9c-128">Enabling Transaction Flow</span></span>](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)
