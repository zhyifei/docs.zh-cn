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
ms.openlocfilehash: 5a32fb0480e76f47495590a29c329f54722e2dee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127779"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="867d7-102">ICorConfiguration::SetGCHostControl 方法</span><span class="sxs-lookup"><span data-stu-id="867d7-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="867d7-103">设置垃圾回收器用于请求主机更改虚拟内存限制的回调接口。</span><span class="sxs-lookup"><span data-stu-id="867d7-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="867d7-104">语法</span><span class="sxs-lookup"><span data-stu-id="867d7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="867d7-105">参数</span><span class="sxs-lookup"><span data-stu-id="867d7-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="867d7-106">中指向[IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)对象的指针，该对象允许垃圾回收器请求主机更改虚拟内存的限制。</span><span class="sxs-lookup"><span data-stu-id="867d7-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="867d7-107">要求</span><span class="sxs-lookup"><span data-stu-id="867d7-107">Requirements</span></span>  
 <span data-ttu-id="867d7-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="867d7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="867d7-109">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="867d7-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="867d7-110">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="867d7-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="867d7-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="867d7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="867d7-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="867d7-112">See also</span></span>

- [<span data-ttu-id="867d7-113">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="867d7-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
