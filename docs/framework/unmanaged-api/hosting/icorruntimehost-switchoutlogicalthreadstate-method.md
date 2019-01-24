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
ms.openlocfilehash: 291fb64bd86c1670945136e5ec7f586496f77d49
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730212"
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="6822f-102">ICorRuntimeHost::SwitchOutLogicalThreadState 方法</span><span class="sxs-lookup"><span data-stu-id="6822f-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>
<span data-ttu-id="6822f-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="6822f-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6822f-104">语法</span><span class="sxs-lookup"><span data-stu-id="6822f-104">Syntax</span></span>  
  
```  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6822f-105">参数</span><span class="sxs-lookup"><span data-stu-id="6822f-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="6822f-106">[out]指示被切换出纤程 cookie。</span><span class="sxs-lookup"><span data-stu-id="6822f-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6822f-107">要求</span><span class="sxs-lookup"><span data-stu-id="6822f-107">Requirements</span></span>  
 <span data-ttu-id="6822f-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6822f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6822f-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6822f-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6822f-110">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6822f-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6822f-111">**.NET framework 版本：** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="6822f-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6822f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="6822f-112">See also</span></span>
- [<span data-ttu-id="6822f-113">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="6822f-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
