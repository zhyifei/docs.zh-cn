---
title: ICorRuntimeHost::SwitchOutLogicalThreadState 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchOutLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState method [.NET Framework hosting]
- SwitchOutLogicalThreadState method [.NET Framework hosting]
ms.assetid: e1968f0b-2675-4dc2-8507-46164e1df154
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 33729e9efa999eb276140ddd2571a4844e15dd6d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770829"
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="dba40-102">ICorRuntimeHost::SwitchOutLogicalThreadState 方法</span><span class="sxs-lookup"><span data-stu-id="dba40-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>
<span data-ttu-id="dba40-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="dba40-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dba40-104">语法</span><span class="sxs-lookup"><span data-stu-id="dba40-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dba40-105">参数</span><span class="sxs-lookup"><span data-stu-id="dba40-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="dba40-106">[out]指示被切换出纤程 cookie。</span><span class="sxs-lookup"><span data-stu-id="dba40-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dba40-107">要求</span><span class="sxs-lookup"><span data-stu-id="dba40-107">Requirements</span></span>  
 <span data-ttu-id="dba40-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dba40-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dba40-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dba40-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dba40-110">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="dba40-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dba40-111">**.NET framework 版本：** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="dba40-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dba40-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="dba40-112">See also</span></span>

- [<span data-ttu-id="dba40-113">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="dba40-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
