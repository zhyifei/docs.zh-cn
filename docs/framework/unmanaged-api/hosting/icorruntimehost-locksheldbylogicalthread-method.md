---
title: "ICorRuntimeHost::LocksHeldByLogicalThread 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.LocksHeldByLogicalThread
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::LocksHeldByLogicalThread
helpviewer_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread method [.NET Framework hosting]
- LocksHeldByLogicalThread method [.NET Framework hosting]
ms.assetid: c3601255-d894-4d7c-b1df-c31334551700
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 82fa031e4842d81f7ddec3e7eeb64c9d7b02e566
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="58835-102">ICorRuntimeHost::LocksHeldByLogicalThread 方法</span><span class="sxs-lookup"><span data-stu-id="58835-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="58835-103">检索当前线程持有的锁的数目。</span><span class="sxs-lookup"><span data-stu-id="58835-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="58835-104">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="58835-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58835-105">语法</span><span class="sxs-lookup"><span data-stu-id="58835-105">Syntax</span></span>  
  
```  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58835-106">参数</span><span class="sxs-lookup"><span data-stu-id="58835-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="58835-107">[out]指向当前线程持有的锁的数目的指针。</span><span class="sxs-lookup"><span data-stu-id="58835-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58835-108">要求</span><span class="sxs-lookup"><span data-stu-id="58835-108">Requirements</span></span>  
 <span data-ttu-id="58835-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="58835-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58835-110">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="58835-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="58835-111">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="58835-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58835-112">**.NET framework 版本：** 1.0、 1.1</span><span class="sxs-lookup"><span data-stu-id="58835-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58835-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58835-113">See Also</span></span>  
 [<span data-ttu-id="58835-114">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="58835-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
