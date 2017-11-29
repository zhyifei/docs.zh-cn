---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8193027e-9db2-4af9-a072-27300cd24330
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 32db1ebd3bd760d3cdeb954854f340c06aec4c3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfaulted"></a><span data-ttu-id="45459-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span><span class="sxs-lookup"><span data-stu-id="45459-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span></span>
<span data-ttu-id="45459-103">WS-AT 协议服务从其协调程序接收到错误作为对注册消息的响应。</span><span class="sxs-lookup"><span data-stu-id="45459-103">The WS-AT protocol service received a fault from its coordinator in response to a Register message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="45459-104">描述</span><span class="sxs-lookup"><span data-stu-id="45459-104">Description</span></span>  
 <span data-ttu-id="45459-105">在本地 TransactionManager 由于所返回的错误而无法向其上级 TransactionManager 注册时跟踪。</span><span class="sxs-lookup"><span data-stu-id="45459-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to a fault being returned.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="45459-106">疑难解答</span><span class="sxs-lookup"><span data-stu-id="45459-106">Troubleshooting</span></span>  
 <span data-ttu-id="45459-107">检查返回的错误的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="45459-107">Inspect the trace message for the fault returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45459-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45459-108">See Also</span></span>  
 [<span data-ttu-id="45459-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="45459-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="45459-110">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="45459-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="45459-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="45459-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
