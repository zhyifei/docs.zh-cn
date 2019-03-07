---
title: ICorConfiguration::SetGCHostControl 方法
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCHostControl
helpviewer_keywords:
- ICorConfiguration::SetGCHostControl method [.NET Framework hosting]
- SetGCHostControl method [.NET Framework hosting]
ms.assetid: bca6bd79-e288-475a-aa46-6bf81541d966
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a64922e1fe069d682f7ebc51040d06231a8b49c3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484350"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="e5ae0-102">ICorConfiguration::SetGCHostControl 方法</span><span class="sxs-lookup"><span data-stu-id="e5ae0-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="e5ae0-103">设置要由垃圾回收器用于请求的主机，若要更改的虚拟内存限制的回调接口。</span><span class="sxs-lookup"><span data-stu-id="e5ae0-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5ae0-104">语法</span><span class="sxs-lookup"><span data-stu-id="e5ae0-104">Syntax</span></span>  
  
```  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5ae0-105">参数</span><span class="sxs-lookup"><span data-stu-id="e5ae0-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="e5ae0-106">[in]一个指向[IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)对象，它允许垃圾回收器请求的主机，若要更改虚拟内存的限制。</span><span class="sxs-lookup"><span data-stu-id="e5ae0-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5ae0-107">要求</span><span class="sxs-lookup"><span data-stu-id="e5ae0-107">Requirements</span></span>  
 <span data-ttu-id="e5ae0-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e5ae0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5ae0-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e5ae0-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e5ae0-110">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e5ae0-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5ae0-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5ae0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5ae0-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5ae0-112">See also</span></span>
- [<span data-ttu-id="e5ae0-113">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="e5ae0-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
