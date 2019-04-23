---
title: 使用 WS-AtomicTransaction
ms.date: 03/30/2017
helpviewer_keywords:
- WS-AT protocol [WCF]
ms.assetid: 04a4c200-0af0-4c5d-a3d9-87cb7339e054
ms.openlocfilehash: 8a8265873e4287e1455659aa4d9fae7e1d570a00
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165455"
---
# <a name="using-ws-atomictransaction"></a><span data-ttu-id="1c008-102">使用 WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="1c008-102">Using WS-AtomicTransaction</span></span>
<span data-ttu-id="1c008-103">WS-AtomicTransaction (WS-AT) 是一种可互操作的事务协议。</span><span class="sxs-lookup"><span data-stu-id="1c008-103">WS-AtomicTransaction (WS-AT) is an interoperable transaction protocol.</span></span> <span data-ttu-id="1c008-104">它使您能够使用 Web 服务消息对分布式事务进行流处理并以可互操作的方式在异类事务基础结构之间进行协调。</span><span class="sxs-lookup"><span data-stu-id="1c008-104">It enables you to flow distributed transactions by using Web service messages, and coordinate in an interoperable manner between heterogeneous transaction infrastructures.</span></span> <span data-ttu-id="1c008-105">WS-AT 使用两阶段提交协议在分布式应用程序、事务管理器和资源管理器之间驱动原子结果的生成。</span><span class="sxs-lookup"><span data-stu-id="1c008-105">WS-AT uses the two-phase commit protocol to drive an atomic outcome between distributed applications, transaction managers, and resource managers.</span></span>  
  
 <span data-ttu-id="1c008-106">Windows Communication Foundation (WCF) 提供的 WS-AT 实现包括 Microsoft 分布式事务处理协调器 (MSDTC) 事务管理器中内置的协议服务。</span><span class="sxs-lookup"><span data-stu-id="1c008-106">The WS-AT implementation Windows Communication Foundation (WCF) provides includes a protocol service built into the Microsoft Distributed Transaction Coordinator (MSDTC) transaction manager.</span></span> <span data-ttu-id="1c008-107">使用 WS-AT，WCF 应用程序可以使事务流动到其他应用程序，包括使用第三方技术生成的可互操作 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="1c008-107">Using WS-AT, WCF applications can flow transactions to other applications, including interoperable Web services built using third-party technology.</span></span>  
  
 <span data-ttu-id="1c008-108">在客户端应用程序和服务器应用程序之间流动事务时，使用的事务协议由服务器在终结点上公开的绑定确定，而该终结点由客户端选择。</span><span class="sxs-lookup"><span data-stu-id="1c008-108">When flowing a transaction between a client application and a server application, the transaction protocol used is determined by the binding that the server exposes on the endpoint the client selected.</span></span> <span data-ttu-id="1c008-109">指定到一些 WCF 系统提供的绑定默认`OleTransactions`协议作为事务传播格式，而其他默认为指定 WS-AT。</span><span class="sxs-lookup"><span data-stu-id="1c008-109">Some WCF system-provided bindings default to specifying the `OleTransactions` protocol as the transaction propagation format, while others default to specifying WS-AT.</span></span> <span data-ttu-id="1c008-110">您也可以以编程方式修改给定绑定内所选的事务协议。</span><span class="sxs-lookup"><span data-stu-id="1c008-110">You can also programmatically modify the choice of transaction protocol inside a given binding.</span></span>  
  
 <span data-ttu-id="1c008-111">协议的选择可影响以下内容：</span><span class="sxs-lookup"><span data-stu-id="1c008-111">The choice of protocol influences:</span></span>  
  
-   <span data-ttu-id="1c008-112">使事务从客户端流动到服务器所使用的消息头的格式。</span><span class="sxs-lookup"><span data-stu-id="1c008-112">The format of the message headers used to flow the transaction from client to server.</span></span>  
  
-   <span data-ttu-id="1c008-113">用于在客户端的事务管理器和服务器的事务之间运行两阶段提交协议以便解析事务结果的网络协议。</span><span class="sxs-lookup"><span data-stu-id="1c008-113">The network protocol used to run the two-phase commit protocol between the client's transaction manager and the server's transaction, in order to resolve the outcome of the transaction.</span></span>  
  
 <span data-ttu-id="1c008-114">如果使用 WCF 编写服务器和客户端，您不需要使用 WS-AT。</span><span class="sxs-lookup"><span data-stu-id="1c008-114">If the server and client are written using WCF, you do not need to use WS-AT.</span></span> <span data-ttu-id="1c008-115">可以改为使用 `NetTcpBinding` 的默认设置并启用 `TransactionFlow` 属性，此设置将使用 `OleTransactions` 协议。</span><span class="sxs-lookup"><span data-stu-id="1c008-115">Instead, you can use the default settings of `NetTcpBinding` with the `TransactionFlow` attribute enabled, which will use the `OleTransactions` protocol instead.</span></span> <span data-ttu-id="1c008-116">有关详细信息，请参阅[ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="1c008-116">For more information, see [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span> <span data-ttu-id="1c008-117">否则，如果你要使事务流动到使用第三方技术生成的 Web 服务，则必须使用 WS-AT。</span><span class="sxs-lookup"><span data-stu-id="1c008-117">Otherwise, if you are flowing transactions to Web services built on third-party technologies, you must use WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c008-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c008-118">See also</span></span>

- [<span data-ttu-id="1c008-119">配置 WS-Atomic 事务支持</span><span class="sxs-lookup"><span data-stu-id="1c008-119">Configuring WS-Atomic Transaction Support</span></span>](../../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)
