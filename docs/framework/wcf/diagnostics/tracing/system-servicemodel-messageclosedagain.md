---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: a18355d55359df665d0e936ce95da34bf07aec6a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181323"
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="b07e0-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="b07e0-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="b07e0-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="b07e0-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="b07e0-104">描述</span><span class="sxs-lookup"><span data-stu-id="b07e0-104">Description</span></span>  
 <span data-ttu-id="b07e0-105">已再次关闭消息。</span><span class="sxs-lookup"><span data-stu-id="b07e0-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="b07e0-106">消息只应关闭一次。</span><span class="sxs-lookup"><span data-stu-id="b07e0-106">A message should be closed only once.</span></span> <span data-ttu-id="b07e0-107">如果用户扩展代码发出此跟踪，则指示用户扩展代码正在关闭一个已经关闭的消息。</span><span class="sxs-lookup"><span data-stu-id="b07e0-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="b07e0-108">如果通过产品代码发出此跟踪，则指示用户扩展代码可能正在过早地关闭消息。</span><span class="sxs-lookup"><span data-stu-id="b07e0-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b07e0-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="b07e0-109">See also</span></span>

- [<span data-ttu-id="b07e0-110">跟踪</span><span class="sxs-lookup"><span data-stu-id="b07e0-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="b07e0-111">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="b07e0-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="b07e0-112">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="b07e0-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
