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
ms.openlocfilehash: 1291d4e69843db7bd90af07291da415220d98807
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131347"
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="61899-102">ICorRuntimeHost::SwitchOutLogicalThreadState 方法</span><span class="sxs-lookup"><span data-stu-id="61899-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>
<span data-ttu-id="61899-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="61899-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61899-104">语法</span><span class="sxs-lookup"><span data-stu-id="61899-104">Syntax</span></span>  
  
```  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61899-105">参数</span><span class="sxs-lookup"><span data-stu-id="61899-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="61899-106">[out]指示被切换出纤程 cookie。</span><span class="sxs-lookup"><span data-stu-id="61899-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61899-107">要求</span><span class="sxs-lookup"><span data-stu-id="61899-107">Requirements</span></span>  
 <span data-ttu-id="61899-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="61899-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61899-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="61899-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="61899-110">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="61899-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61899-111">**.NET framework 版本：** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="61899-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61899-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="61899-112">See also</span></span>

- [<span data-ttu-id="61899-113">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="61899-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
