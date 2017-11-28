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
ms.openlocfilehash: a6e1f11939bc4f11b1fb49dc44f129176143fbca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="7d965-102">IDebuggerInfo::IsDebuggerAttached 方法</span><span class="sxs-lookup"><span data-stu-id="7d965-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="7d965-103">获取一个值，该值指示是否将托管的调试器附加到此过程。</span><span class="sxs-lookup"><span data-stu-id="7d965-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d965-104">语法</span><span class="sxs-lookup"><span data-stu-id="7d965-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7d965-105">参数</span><span class="sxs-lookup"><span data-stu-id="7d965-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="7d965-106">[out]指向一个值，是`true`托管的调试器附加到进程; 否则为如果`false`。</span><span class="sxs-lookup"><span data-stu-id="7d965-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d965-107">要求</span><span class="sxs-lookup"><span data-stu-id="7d965-107">Requirements</span></span>  
 <span data-ttu-id="7d965-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7d965-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d965-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7d965-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d965-110">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7d965-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d965-111">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d965-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d965-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d965-112">See Also</span></span>  
 [<span data-ttu-id="7d965-113">IDebuggerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="7d965-113">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)
