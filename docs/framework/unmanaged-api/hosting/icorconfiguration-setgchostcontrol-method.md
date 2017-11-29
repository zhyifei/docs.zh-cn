---
title: "ICorConfiguration::SetGCHostControl 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration.SetGCHostControl
api_location: mscoree.dll
api_type: COM
f1_keywords: SetGCHostControl
helpviewer_keywords:
- ICorConfiguration::SetGCHostControl method [.NET Framework hosting]
- SetGCHostControl method [.NET Framework hosting]
ms.assetid: bca6bd79-e288-475a-aa46-6bf81541d966
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 33d01ff208e9814e73c7a658e41819348da6831a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="2042d-102">ICorConfiguration::SetGCHostControl 方法</span><span class="sxs-lookup"><span data-stu-id="2042d-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="2042d-103">设置要用于通过垃圾回收器请求主机后，若要更改的虚拟内存限制的回调接口。</span><span class="sxs-lookup"><span data-stu-id="2042d-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2042d-104">语法</span><span class="sxs-lookup"><span data-stu-id="2042d-104">Syntax</span></span>  
  
```  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2042d-105">参数</span><span class="sxs-lookup"><span data-stu-id="2042d-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="2042d-106">[in]指向的指针[IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)对象，它允许垃圾回收器请求主机后，若要更改的虚拟内存限制。</span><span class="sxs-lookup"><span data-stu-id="2042d-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2042d-107">要求</span><span class="sxs-lookup"><span data-stu-id="2042d-107">Requirements</span></span>  
 <span data-ttu-id="2042d-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2042d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2042d-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2042d-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2042d-110">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2042d-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2042d-111">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2042d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2042d-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2042d-112">See Also</span></span>  
 [<span data-ttu-id="2042d-113">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="2042d-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
