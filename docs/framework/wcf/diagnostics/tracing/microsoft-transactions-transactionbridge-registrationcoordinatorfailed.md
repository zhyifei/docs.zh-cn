---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed
ms.date: 03/30/2017
ms.assetid: 96474056-0418-41e4-8c75-bbc0a853eaba
ms.openlocfilehash: 3745c542986d405312a308fcf50ba6d7b6f93a1c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074178"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfailed"></a><span data-ttu-id="d13fd-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span><span class="sxs-lookup"><span data-stu-id="d13fd-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span></span>
<span data-ttu-id="d13fd-103">WS-AT 协议服务无法向其协调程序发送注册消息</span><span class="sxs-lookup"><span data-stu-id="d13fd-103">The WS-AT protocol service failed to send a Register message to its coordinator</span></span>  
  
## <a name="description"></a><span data-ttu-id="d13fd-104">描述</span><span class="sxs-lookup"><span data-stu-id="d13fd-104">Description</span></span>  
 <span data-ttu-id="d13fd-105">在本地 TransactionManager 由于不能发送消息而无法向其上级 TransactionManager 注册时跟踪。</span><span class="sxs-lookup"><span data-stu-id="d13fd-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to the inability to send a message.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="d13fd-106">疑难解答</span><span class="sxs-lookup"><span data-stu-id="d13fd-106">Troubleshooting</span></span>  
 <span data-ttu-id="d13fd-107">检查跟踪消息以查找导致消息发送失败的异常</span><span class="sxs-lookup"><span data-stu-id="d13fd-107">Inspect the trace message for the exception causing the message send failure</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d13fd-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="d13fd-108">See also</span></span>

- [<span data-ttu-id="d13fd-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="d13fd-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="d13fd-110">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="d13fd-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d13fd-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="d13fd-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
