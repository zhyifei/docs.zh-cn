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
ms.openlocfilehash: f6ef7e06d94cb22d266949927cb15105b1602d3a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139525"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="79d6a-102">ICorRuntimeHost::LocksHeldByLogicalThread 方法</span><span class="sxs-lookup"><span data-stu-id="79d6a-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="79d6a-103">检索当前线程所持有的锁的数目。</span><span class="sxs-lookup"><span data-stu-id="79d6a-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="79d6a-104">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="79d6a-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79d6a-105">语法</span><span class="sxs-lookup"><span data-stu-id="79d6a-105">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79d6a-106">参数</span><span class="sxs-lookup"><span data-stu-id="79d6a-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="79d6a-107">弄一个指针，指向当前线程所持有的锁的数目。</span><span class="sxs-lookup"><span data-stu-id="79d6a-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79d6a-108">要求</span><span class="sxs-lookup"><span data-stu-id="79d6a-108">Requirements</span></span>  
 <span data-ttu-id="79d6a-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="79d6a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79d6a-110">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="79d6a-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="79d6a-111">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="79d6a-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="79d6a-112">**.NET Framework 版本：** 1.0、1。1</span><span class="sxs-lookup"><span data-stu-id="79d6a-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79d6a-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="79d6a-113">See also</span></span>

- [<span data-ttu-id="79d6a-114">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="79d6a-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
