---
title: "IDebuggerInfo::IsDebuggerAttached 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDebuggerInfo.IsDebuggerAttached
api_location: mscoree.dll
api_type: COM
f1_keywords: IsDebuggerAttached
helpviewer_keywords:
- IDebuggerInfo::IsDebuggerAttached method [.NET Framework hosting]
- IsDebuggerAttached method, IDebuggerInfo interface [.NET Framework hosting]
ms.assetid: 6e21872f-602f-411a-a423-bff5cdf27000
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c241af6b71591374d8ce8cc8d1610a8dce91b2e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="d1c0d-102">IDebuggerInfo::IsDebuggerAttached 方法</span><span class="sxs-lookup"><span data-stu-id="d1c0d-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="d1c0d-103">获取一个值，该值指示是否将托管的调试器附加到此过程。</span><span class="sxs-lookup"><span data-stu-id="d1c0d-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1c0d-104">语法</span><span class="sxs-lookup"><span data-stu-id="d1c0d-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d1c0d-105">参数</span><span class="sxs-lookup"><span data-stu-id="d1c0d-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="d1c0d-106">[out]指向一个值，是`true`托管的调试器附加到进程; 否则为如果`false`。</span><span class="sxs-lookup"><span data-stu-id="d1c0d-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1c0d-107">惠?</span><span class="sxs-lookup"><span data-stu-id="d1c0d-107">Requirements</span></span>  
 <span data-ttu-id="d1c0d-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d1c0d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1c0d-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d1c0d-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d1c0d-110">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d1c0d-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d1c0d-111">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1c0d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1c0d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1c0d-112">See Also</span></span>  
 [<span data-ttu-id="d1c0d-113">IDebuggerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="d1c0d-113">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)
