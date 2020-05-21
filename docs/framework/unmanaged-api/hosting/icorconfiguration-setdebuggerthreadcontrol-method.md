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
ms.openlocfilehash: d02b834b22ba7897e4939de88bc3c61c62ac2b0e
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762404"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="835c9-102">ICorConfiguration::SetDebuggerThreadControl 方法</span><span class="sxs-lookup"><span data-stu-id="835c9-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>
<span data-ttu-id="835c9-103">设置作为公共语言运行时（CLR）线程被阻止和取消阻止以进行调试的回调接口。</span><span class="sxs-lookup"><span data-stu-id="835c9-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="835c9-104">语法</span><span class="sxs-lookup"><span data-stu-id="835c9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="835c9-105">参数</span><span class="sxs-lookup"><span data-stu-id="835c9-105">Parameters</span></span>  
 `pDebuggerThreadControl`  
 <span data-ttu-id="835c9-106">中指向[IDebuggerThreadControl](idebuggerthreadcontrol-interface.md)对象的指针，该对象通知宿主调试服务阻止和取消阻止线程。</span><span class="sxs-lookup"><span data-stu-id="835c9-106">[in] A pointer to an [IDebuggerThreadControl](idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="835c9-107">要求</span><span class="sxs-lookup"><span data-stu-id="835c9-107">Requirements</span></span>  
 <span data-ttu-id="835c9-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="835c9-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="835c9-109">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="835c9-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="835c9-110">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="835c9-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="835c9-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="835c9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="835c9-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="835c9-112">See also</span></span>

- [<span data-ttu-id="835c9-113">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="835c9-113">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
