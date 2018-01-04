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
ms.workload: dotnet
ms.openlocfilehash: 8cf9f8a9fba43a915fd71e397c4aed54c8d95197
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfaulted"></a><span data-ttu-id="2df4a-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span><span class="sxs-lookup"><span data-stu-id="2df4a-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span></span>
<span data-ttu-id="2df4a-103">WS-AT 协议服务从其协调程序接收到错误作为对注册消息的响应。</span><span class="sxs-lookup"><span data-stu-id="2df4a-103">The WS-AT protocol service received a fault from its coordinator in response to a Register message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2df4a-104">描述</span><span class="sxs-lookup"><span data-stu-id="2df4a-104">Description</span></span>  
 <span data-ttu-id="2df4a-105">在本地 TransactionManager 由于所返回的错误而无法向其上级 TransactionManager 注册时跟踪。</span><span class="sxs-lookup"><span data-stu-id="2df4a-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to a fault being returned.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="2df4a-106">疑难解答</span><span class="sxs-lookup"><span data-stu-id="2df4a-106">Troubleshooting</span></span>  
 <span data-ttu-id="2df4a-107">检查返回的错误的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="2df4a-107">Inspect the trace message for the fault returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2df4a-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="2df4a-108">See Also</span></span>  
 [<span data-ttu-id="2df4a-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="2df4a-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="2df4a-110">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="2df4a-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="2df4a-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="2df4a-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
