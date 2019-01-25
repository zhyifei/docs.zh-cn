---
title: ICorRuntimeHost::LocksHeldByLogicalThread 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.LocksHeldByLogicalThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread
helpviewer_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread method [.NET Framework hosting]
- LocksHeldByLogicalThread method [.NET Framework hosting]
ms.assetid: c3601255-d894-4d7c-b1df-c31334551700
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8897eda39a0ff5f1a11a95aeea4e2887912592ec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519250"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="b9ba3-102">ICorRuntimeHost::LocksHeldByLogicalThread 方法</span><span class="sxs-lookup"><span data-stu-id="b9ba3-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="b9ba3-103">检索当前线程持有的锁的数目。</span><span class="sxs-lookup"><span data-stu-id="b9ba3-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="b9ba3-104">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="b9ba3-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9ba3-105">语法</span><span class="sxs-lookup"><span data-stu-id="b9ba3-105">Syntax</span></span>  
  
```  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9ba3-106">参数</span><span class="sxs-lookup"><span data-stu-id="b9ba3-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="b9ba3-107">[out]一个指向当前线程持有的锁的数目。</span><span class="sxs-lookup"><span data-stu-id="b9ba3-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9ba3-108">要求</span><span class="sxs-lookup"><span data-stu-id="b9ba3-108">Requirements</span></span>  
 <span data-ttu-id="b9ba3-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b9ba3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9ba3-110">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b9ba3-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b9ba3-111">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b9ba3-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9ba3-112">**.NET framework 版本：** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="b9ba3-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9ba3-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9ba3-113">See also</span></span>
- [<span data-ttu-id="b9ba3-114">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="b9ba3-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
