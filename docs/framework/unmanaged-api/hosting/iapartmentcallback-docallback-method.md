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
ms.openlocfilehash: 77a2ccaf6f972fadd8396378dc7777ec4c85120d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110222"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="30ff7-102">IApartmentCallback::DoCallback 方法</span><span class="sxs-lookup"><span data-stu-id="30ff7-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="30ff7-103">执行单元内的指定的函数。</span><span class="sxs-lookup"><span data-stu-id="30ff7-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30ff7-104">语法</span><span class="sxs-lookup"><span data-stu-id="30ff7-104">Syntax</span></span>  
  
```  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30ff7-105">参数</span><span class="sxs-lookup"><span data-stu-id="30ff7-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="30ff7-106">[in]指向要在单元内执行的函数的指针。</span><span class="sxs-lookup"><span data-stu-id="30ff7-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="30ff7-107">[in]指向函数的参数的指针。</span><span class="sxs-lookup"><span data-stu-id="30ff7-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30ff7-108">要求</span><span class="sxs-lookup"><span data-stu-id="30ff7-108">Requirements</span></span>  
 <span data-ttu-id="30ff7-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="30ff7-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30ff7-110">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="30ff7-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30ff7-111">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="30ff7-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="30ff7-112">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="30ff7-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="30ff7-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="30ff7-113">See also</span></span>

- [<span data-ttu-id="30ff7-114">IApartmentCallback 接口</span><span class="sxs-lookup"><span data-stu-id="30ff7-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
