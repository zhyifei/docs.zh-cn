---
title: 事务模型
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 8731b72d0657aa420dbb020e216c3af059916ce9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43474221"
---
# <a name="transaction-models"></a><span data-ttu-id="50af5-102">事务模型</span><span class="sxs-lookup"><span data-stu-id="50af5-102">Transaction Models</span></span>
<span data-ttu-id="50af5-103">本主题描述 Microsoft 提供的事务编程模型和基础结构组件之间的关系。</span><span class="sxs-lookup"><span data-stu-id="50af5-103">This topic describes the relationship between the transaction programming models and the infrastructure components Microsoft provides.</span></span>  
  
 <span data-ttu-id="50af5-104">使用事务时 Windows Communication Foundation (WCF) 中，务必了解不选择不同的事务模型之间但不同层的集成和一致的模型而不操作。</span><span class="sxs-lookup"><span data-stu-id="50af5-104">When using transactions in Windows Communication Foundation (WCF), it is important to understand that you are not selecting between different transactional models, but rather operating at different layers of an integrated and consistent model.</span></span>  
  
 <span data-ttu-id="50af5-105">以下各部分描述了三个主要事务组件。</span><span class="sxs-lookup"><span data-stu-id="50af5-105">The following sections describe the three primary transaction components.</span></span>  
  
## <a name="windows-communication-foundation-transactions"></a><span data-ttu-id="50af5-106">Windows Communication Foundation 事务</span><span class="sxs-lookup"><span data-stu-id="50af5-106">Windows Communication Foundation Transactions</span></span>  
 <span data-ttu-id="50af5-107">WCF 中的事务支持允许您编写事务性服务。</span><span class="sxs-lookup"><span data-stu-id="50af5-107">The transaction support in WCF allows you write transactional services.</span></span> <span data-ttu-id="50af5-108">此外，它对 WS-AtomicTransaction (WS-AT) 协议的支持，与应用程序可以使事务流动到使用 WCF 或第三方技术生成的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="50af5-108">In addition, with its support for the WS-AtomicTransaction (WS-AT) protocol, applications can flow transactions to Web services built using either WCF or third-party technology.</span></span>  
  
 <span data-ttu-id="50af5-109">在 WCF 服务或应用程序中，WCF 事务功能提供属性和配置用于以声明方式指定基础结构如何以及何时应创建、 流、 和同步事务。</span><span class="sxs-lookup"><span data-stu-id="50af5-109">In a WCF service or application, WCF transaction features provide attributes and configuration for declaratively specifying how and when the infrastructure should create, flow, and synchronize transactions.</span></span>  
  
## <a name="systemtransactions-transactions"></a><span data-ttu-id="50af5-110">System.Transactions 事务</span><span class="sxs-lookup"><span data-stu-id="50af5-110">System.Transactions Transactions</span></span>  
 <span data-ttu-id="50af5-111"><xref:System.Transactions> 命名空间同时提供了一个基于 <xref:System.Transactions.Transaction> 类的显式编程模型和一个使用 <xref:System.Transactions.TransactionScope> 类的隐式编程模型（在此模型中，基础结构自动管理事务）。</span><span class="sxs-lookup"><span data-stu-id="50af5-111">The <xref:System.Transactions> namespace provides both an explicit programming model based on the <xref:System.Transactions.Transaction> class, as well as an implicit programming model using the <xref:System.Transactions.TransactionScope> class, in which the infrastructure automatically manages transactions.</span></span>  
  
 <span data-ttu-id="50af5-112">有关如何创建事务应用程序使用这两种模型的详细信息，请参阅[编写事务应用程序](https://go.microsoft.com/fwlink/?LinkId=94947)。</span><span class="sxs-lookup"><span data-stu-id="50af5-112">For more information about how to create a transactional application using these two models, see [Writing a Transactional Application](https://go.microsoft.com/fwlink/?LinkId=94947).</span></span>  
  
 <span data-ttu-id="50af5-113">中的 WCF 服务或应用程序，<xref:System.Transactions>提供编程模型，用于创建客户端应用程序中的事务和显式进行交互与事务，在需要时，在服务中。</span><span class="sxs-lookup"><span data-stu-id="50af5-113">In a WCF service or application, <xref:System.Transactions> provides the programming model for creating transactions within a client application and for explicitly interacting with a transaction, when required, within a service.</span></span>  
  
## <a name="msdtc-transactions"></a><span data-ttu-id="50af5-114">MSDTC 事务</span><span class="sxs-lookup"><span data-stu-id="50af5-114">MSDTC Transactions</span></span>  
 <span data-ttu-id="50af5-115">Microsoft Distributed Transaction Coordinator (MSDTC) 是一个事务管理器，它为分布式事务提供支持。</span><span class="sxs-lookup"><span data-stu-id="50af5-115">The Microsoft Distributed Transaction Coordinator (MSDTC) is a transaction manager that provides support for distributed transactions.</span></span>  
  
 <span data-ttu-id="50af5-116">有关详细信息，请参阅[DTC 程序员参考](https://go.microsoft.com/fwlink/?LinkId=94948)。</span><span class="sxs-lookup"><span data-stu-id="50af5-116">For more information, see the [DTC Programmer's Reference](https://go.microsoft.com/fwlink/?LinkId=94948).</span></span>  
  
 <span data-ttu-id="50af5-117">在 WCF 服务或应用程序中，MSDTC 提供客户端或服务中创建的事务协调的基础结构。</span><span class="sxs-lookup"><span data-stu-id="50af5-117">In a WCF service or application, MSDTC provides the infrastructure for the coordination of transactions created within a client or service.</span></span>
