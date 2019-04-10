---
title: ICorRuntimeHost::SwitchInLogicalThreadState 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchInLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState method [.NET Framework hosting]
- SwitchInLogicalThreadState method [.NET Framework hosting]
ms.assetid: 7df1e492-8014-43ea-80d1-a4743e9b1c17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc6cd8d2d0ab4648ad20392ef0968907917677e9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209484"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="db751-102">ICorRuntimeHost::SwitchInLogicalThreadState 方法</span><span class="sxs-lookup"><span data-stu-id="db751-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="db751-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="db751-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db751-104">语法</span><span class="sxs-lookup"><span data-stu-id="db751-104">Syntax</span></span>  
  
```  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db751-105">参数</span><span class="sxs-lookup"><span data-stu-id="db751-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="db751-106">[in]指示要使用纤程 cookie。</span><span class="sxs-lookup"><span data-stu-id="db751-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db751-107">要求</span><span class="sxs-lookup"><span data-stu-id="db751-107">Requirements</span></span>  
 <span data-ttu-id="db751-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="db751-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db751-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="db751-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db751-110">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="db751-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db751-111">**.NET framework 版本：** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="db751-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db751-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="db751-112">See also</span></span>

- [<span data-ttu-id="db751-113">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="db751-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
