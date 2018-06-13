---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted
ms.date: 03/30/2017
ms.assetid: 8193027e-9db2-4af9-a072-27300cd24330
ms.openlocfilehash: e1cb43a9336c2536a3b0372387fd956708be78a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33475915"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfaulted"></a><span data-ttu-id="0248b-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span><span class="sxs-lookup"><span data-stu-id="0248b-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span></span>
<span data-ttu-id="0248b-103">WS-AT 协议服务从其协调程序接收到错误作为对注册消息的响应。</span><span class="sxs-lookup"><span data-stu-id="0248b-103">The WS-AT protocol service received a fault from its coordinator in response to a Register message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0248b-104">描述</span><span class="sxs-lookup"><span data-stu-id="0248b-104">Description</span></span>  
 <span data-ttu-id="0248b-105">在本地 TransactionManager 由于所返回的错误而无法向其上级 TransactionManager 注册时跟踪。</span><span class="sxs-lookup"><span data-stu-id="0248b-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to a fault being returned.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="0248b-106">疑难解答</span><span class="sxs-lookup"><span data-stu-id="0248b-106">Troubleshooting</span></span>  
 <span data-ttu-id="0248b-107">检查返回的错误的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="0248b-107">Inspect the trace message for the fault returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0248b-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="0248b-108">See Also</span></span>  
 [<span data-ttu-id="0248b-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="0248b-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="0248b-110">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="0248b-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="0248b-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="0248b-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
