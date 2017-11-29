---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0ea98388efe14ac0d18a94ec056a441096a4d7c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="092af-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="092af-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>
<span data-ttu-id="092af-103">关闭此连接池中的连接时发生异常。</span><span class="sxs-lookup"><span data-stu-id="092af-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="092af-104">描述</span><span class="sxs-lookup"><span data-stu-id="092af-104">Description</span></span>  
 <span data-ttu-id="092af-105">此错误级别跟踪指示当关闭由 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 的连接池功能使用的连接池时发生了错误。</span><span class="sxs-lookup"><span data-stu-id="092af-105">This error level trace indicates that an error has occurred while closing the connection pools used by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]’s connection pooling feature.</span></span> <span data-ttu-id="092af-106">一种可能的原因是一个池连接或一组池连接在 CloseTimeout 内未成功关闭。</span><span class="sxs-lookup"><span data-stu-id="092af-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="092af-107">当引发此异常时，将中止该池内所有剩余的未关闭连接，并放弃其他池内的未关闭连接。</span><span class="sxs-lookup"><span data-stu-id="092af-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="092af-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="092af-108">See Also</span></span>  
 [<span data-ttu-id="092af-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="092af-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="092af-110">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="092af-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="092af-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="092af-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
