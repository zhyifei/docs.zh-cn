---
title: IDebuggerInfo::IsDebuggerAttached 方法
ms.date: 03/30/2017
api_name:
- IDebuggerInfo.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IsDebuggerAttached
helpviewer_keywords:
- IDebuggerInfo::IsDebuggerAttached method [.NET Framework hosting]
- IsDebuggerAttached method, IDebuggerInfo interface [.NET Framework hosting]
ms.assetid: 6e21872f-602f-411a-a423-bff5cdf27000
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91acfa5545f3115c9e95207f05708ff32530994f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437276"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="ff6f6-102">IDebuggerInfo::IsDebuggerAttached 方法</span><span class="sxs-lookup"><span data-stu-id="ff6f6-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="ff6f6-103">获取一个值，该值指示是否将托管的调试器附加到此过程。</span><span class="sxs-lookup"><span data-stu-id="ff6f6-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff6f6-104">语法</span><span class="sxs-lookup"><span data-stu-id="ff6f6-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff6f6-105">参数</span><span class="sxs-lookup"><span data-stu-id="ff6f6-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="ff6f6-106">[out]指向一个值，是`true`托管的调试器附加到进程; 否则为如果`false`。</span><span class="sxs-lookup"><span data-stu-id="ff6f6-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff6f6-107">要求</span><span class="sxs-lookup"><span data-stu-id="ff6f6-107">Requirements</span></span>  
 <span data-ttu-id="ff6f6-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ff6f6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff6f6-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ff6f6-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff6f6-110">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ff6f6-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff6f6-111">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff6f6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff6f6-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff6f6-112">See Also</span></span>  
 [<span data-ttu-id="ff6f6-113">IDebuggerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="ff6f6-113">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)
