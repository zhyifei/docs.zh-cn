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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1dd58fdbdbdcf2f7bf8f69b86276a24c17df79e3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfaulted"></a><span data-ttu-id="8ba74-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span><span class="sxs-lookup"><span data-stu-id="8ba74-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span></span>
<span data-ttu-id="8ba74-103">WS-AT 协议服务从其协调程序接收到错误作为对注册消息的响应。</span><span class="sxs-lookup"><span data-stu-id="8ba74-103">The WS-AT protocol service received a fault from its coordinator in response to a Register message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8ba74-104">描述</span><span class="sxs-lookup"><span data-stu-id="8ba74-104">Description</span></span>  
 <span data-ttu-id="8ba74-105">在本地 TransactionManager 由于所返回的错误而无法向其上级 TransactionManager 注册时跟踪。</span><span class="sxs-lookup"><span data-stu-id="8ba74-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to a fault being returned.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="8ba74-106">疑难解答</span><span class="sxs-lookup"><span data-stu-id="8ba74-106">Troubleshooting</span></span>  
 <span data-ttu-id="8ba74-107">检查返回的错误的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="8ba74-107">Inspect the trace message for the fault returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ba74-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ba74-108">See Also</span></span>  
 [<span data-ttu-id="8ba74-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="8ba74-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="8ba74-110">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="8ba74-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="8ba74-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="8ba74-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
