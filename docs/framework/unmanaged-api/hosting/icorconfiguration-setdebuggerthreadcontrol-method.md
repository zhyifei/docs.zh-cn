---
title: ICorConfiguration::SetDebuggerThreadControl 方法
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetDebuggerThreadControl
helpviewer_keywords:
- SetDebuggerThreadControl method [.NET Framework hosting]
- ICorConfiguration::SetDebuggerThreadControl method [.NET Framework hosting]
ms.assetid: 1ded7639-dacb-4db1-961c-d1ceaec01959
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6fc141cbebe08f8d0974788409d5aef0f68d2878
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763251"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="2b4c5-102">ICorConfiguration::SetDebuggerThreadControl 方法</span><span class="sxs-lookup"><span data-stu-id="2b4c5-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>
<span data-ttu-id="2b4c5-103">设置调试服务将调用公共语言运行时 (CLR) 线程阻止和解除阻止以进行调试的回调接口。</span><span class="sxs-lookup"><span data-stu-id="2b4c5-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b4c5-104">语法</span><span class="sxs-lookup"><span data-stu-id="2b4c5-104">Syntax</span></span>  
  
```  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b4c5-105">参数</span><span class="sxs-lookup"><span data-stu-id="2b4c5-105">Parameters</span></span>  
 `pDebuggerThreadControl`  
 <span data-ttu-id="2b4c5-106">[in]一个指向[IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)通知主机有关阻止和解除阻止的线程的调试服务的对象。</span><span class="sxs-lookup"><span data-stu-id="2b4c5-106">[in] A pointer to an [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b4c5-107">要求</span><span class="sxs-lookup"><span data-stu-id="2b4c5-107">Requirements</span></span>  
 <span data-ttu-id="2b4c5-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2b4c5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b4c5-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2b4c5-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2b4c5-110">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2b4c5-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2b4c5-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b4c5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b4c5-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b4c5-112">See also</span></span>

- [<span data-ttu-id="2b4c5-113">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="2b4c5-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
