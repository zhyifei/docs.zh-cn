---
title: 事务模型
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3c68a23e9ee86050a9db4c63c8c97d017794bce8
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="transaction-models"></a><span data-ttu-id="f5db6-102">事务模型</span><span class="sxs-lookup"><span data-stu-id="f5db6-102">Transaction Models</span></span>
<span data-ttu-id="f5db6-103">本主题描述 Microsoft 提供的事务编程模型和基础结构组件之间的关系。</span><span class="sxs-lookup"><span data-stu-id="f5db6-103">This topic describes the relationship between the transaction programming models and the infrastructure components Microsoft provides.</span></span>  
  
 <span data-ttu-id="f5db6-104">在 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中使用事务时，需要了解的一点是，您并不是在不同事务模型之间进行选择，而是在一个集成化且一致的模型的不同层上进行操作。</span><span class="sxs-lookup"><span data-stu-id="f5db6-104">When using transactions in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], it is important to understand that you are not selecting between different transactional models, but rather operating at different layers of an integrated and consistent model.</span></span>  
  
 <span data-ttu-id="f5db6-105">以下各部分描述了三个主要事务组件。</span><span class="sxs-lookup"><span data-stu-id="f5db6-105">The following sections describe the three primary transaction components.</span></span>  
  
## <a name="windows-communication-foundation-transactions"></a><span data-ttu-id="f5db6-106">Windows Communication Foundation 事务</span><span class="sxs-lookup"><span data-stu-id="f5db6-106">Windows Communication Foundation Transactions</span></span>  
 <span data-ttu-id="f5db6-107">使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中的事务支持可以编写事务性服务。</span><span class="sxs-lookup"><span data-stu-id="f5db6-107">The transaction support in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] allows you write transactional services.</span></span> <span data-ttu-id="f5db6-108">此外，借助于它对 WS-AtomicTransaction (WS-AT) 协议的支持，应用程序可以将事务流式传输到使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 或第三方技术生成的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="f5db6-108">In addition, with its support for the WS-AtomicTransaction (WS-AT) protocol, applications can flow transactions to Web services built using either [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] or third-party technology.</span></span>  
  
 <span data-ttu-id="f5db6-109">在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务或应用程序中，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 事务功能提供了一些属性和配置，用于以声明方式指定基础结构应当创建、流式传输和同步事务的方式和时间。</span><span class="sxs-lookup"><span data-stu-id="f5db6-109">In a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service or application, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transaction features provide attributes and configuration for declaratively specifying how and when the infrastructure should create, flow, and synchronize transactions.</span></span>  
  
## <a name="systemtransactions-transactions"></a><span data-ttu-id="f5db6-110">System.Transactions 事务</span><span class="sxs-lookup"><span data-stu-id="f5db6-110">System.Transactions Transactions</span></span>  
 <span data-ttu-id="f5db6-111"><xref:System.Transactions> 命名空间同时提供了一个基于 <xref:System.Transactions.Transaction> 类的显式编程模型和一个使用 <xref:System.Transactions.TransactionScope> 类的隐式编程模型（在此模型中，基础结构自动管理事务）。</span><span class="sxs-lookup"><span data-stu-id="f5db6-111">The <xref:System.Transactions> namespace provides both an explicit programming model based on the <xref:System.Transactions.Transaction> class, as well as an implicit programming model using the <xref:System.Transactions.TransactionScope> class, in which the infrastructure automatically manages transactions.</span></span>  
  
 <span data-ttu-id="f5db6-112">有关如何创建使用这两种模型的事务应用程序的详细信息，请参阅[编写事务应用程序](http://go.microsoft.com/fwlink/?LinkId=94947)。</span><span class="sxs-lookup"><span data-stu-id="f5db6-112">For more information about how to create a transactional application using these two models, see [Writing a Transactional Application](http://go.microsoft.com/fwlink/?LinkId=94947).</span></span>  
  
 <span data-ttu-id="f5db6-113">在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务或应用程序中，可使用 <xref:System.Transactions> 提供的编程模型在客户端应用程序中创建事务，以及在需要时与服务内的事务显式进行交互。</span><span class="sxs-lookup"><span data-stu-id="f5db6-113">In a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service or application, <xref:System.Transactions> provides the programming model for creating transactions within a client application and for explicitly interacting with a transaction, when required, within a service.</span></span>  
  
## <a name="msdtc-transactions"></a><span data-ttu-id="f5db6-114">MSDTC 事务</span><span class="sxs-lookup"><span data-stu-id="f5db6-114">MSDTC Transactions</span></span>  
 <span data-ttu-id="f5db6-115">Microsoft Distributed Transaction Coordinator (MSDTC) 是一个事务管理器，它为分布式事务提供支持。</span><span class="sxs-lookup"><span data-stu-id="f5db6-115">The Microsoft Distributed Transaction Coordinator (MSDTC) is a transaction manager that provides support for distributed transactions.</span></span>  
  
 <span data-ttu-id="f5db6-116">有关详细信息，请参阅[DTC 程序员参考](http://go.microsoft.com/fwlink/?LinkId=94948)。</span><span class="sxs-lookup"><span data-stu-id="f5db6-116">For more information, see the [DTC Programmer's Reference](http://go.microsoft.com/fwlink/?LinkId=94948).</span></span>  
  
 <span data-ttu-id="f5db6-117">在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务或应用程序中，MSDTC 提供了用于对客户端或服务中创建的事务进行协调的基础结构。</span><span class="sxs-lookup"><span data-stu-id="f5db6-117">In a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service or application, MSDTC provides the infrastructure for the coordination of transactions created within a client or service.</span></span>
