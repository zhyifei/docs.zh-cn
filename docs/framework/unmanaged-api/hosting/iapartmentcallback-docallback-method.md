---
title: IApartmentCallback::DoCallback 方法
ms.date: 03/30/2017
api_name:
- IApartmentCallback.DoCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- DoCallback
helpviewer_keywords:
- IApartmentCallback::DoCallback method [.NET Framework hosting]
- DoCallback method [.NET Framework hosting]
ms.assetid: 8edad30c-30ff-4bee-813c-75525a82fc93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f64d554ee0bcd93d30dd617177c4e1e33e57aa3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648857"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="76d93-102">IApartmentCallback::DoCallback 方法</span><span class="sxs-lookup"><span data-stu-id="76d93-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="76d93-103">执行单元内的指定的函数。</span><span class="sxs-lookup"><span data-stu-id="76d93-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76d93-104">语法</span><span class="sxs-lookup"><span data-stu-id="76d93-104">Syntax</span></span>  
  
```  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76d93-105">参数</span><span class="sxs-lookup"><span data-stu-id="76d93-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="76d93-106">[in]指向要在单元内执行的函数的指针。</span><span class="sxs-lookup"><span data-stu-id="76d93-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="76d93-107">[in]指向函数的参数的指针。</span><span class="sxs-lookup"><span data-stu-id="76d93-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76d93-108">要求</span><span class="sxs-lookup"><span data-stu-id="76d93-108">Requirements</span></span>  
 <span data-ttu-id="76d93-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="76d93-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76d93-110">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="76d93-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="76d93-111">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="76d93-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76d93-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76d93-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76d93-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="76d93-113">See also</span></span>
- [<span data-ttu-id="76d93-114">IApartmentCallback 接口</span><span class="sxs-lookup"><span data-stu-id="76d93-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
