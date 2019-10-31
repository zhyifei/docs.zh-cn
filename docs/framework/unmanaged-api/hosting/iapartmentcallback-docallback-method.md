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
ms.openlocfilehash: 9bb257a3d84d5022b9ae13c89a34572485d3033b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126948"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="91f31-102">IApartmentCallback::DoCallback 方法</span><span class="sxs-lookup"><span data-stu-id="91f31-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="91f31-103">在单元内执行指定的函数。</span><span class="sxs-lookup"><span data-stu-id="91f31-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91f31-104">语法</span><span class="sxs-lookup"><span data-stu-id="91f31-104">Syntax</span></span>  
  
```cpp  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91f31-105">参数</span><span class="sxs-lookup"><span data-stu-id="91f31-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="91f31-106">中指向要在单元中执行的函数的指针。</span><span class="sxs-lookup"><span data-stu-id="91f31-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="91f31-107">中指向函数的自变量的指针。</span><span class="sxs-lookup"><span data-stu-id="91f31-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91f31-108">要求</span><span class="sxs-lookup"><span data-stu-id="91f31-108">Requirements</span></span>  
 <span data-ttu-id="91f31-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="91f31-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91f31-110">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="91f31-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="91f31-111">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="91f31-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91f31-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91f31-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91f31-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="91f31-113">See also</span></span>

- [<span data-ttu-id="91f31-114">IApartmentCallback 接口</span><span class="sxs-lookup"><span data-stu-id="91f31-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
