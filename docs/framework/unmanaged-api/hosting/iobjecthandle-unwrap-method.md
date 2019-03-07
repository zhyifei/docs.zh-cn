---
title: IObjectHandle::Unwrap 方法
ms.date: 03/30/2017
api_name:
- IObjectHandle.Unwrap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Unwrap
helpviewer_keywords:
- Unwrap method [.NET Framework hosting]
- IObjectHandle::Unwrap method [.NET Framework hosting]
ms.assetid: 794c6f8e-ed58-416b-b756-e864f2c958f7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5539d77b93be1f56102970e9febe6f63599d78e7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502964"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="81ff3-102">IObjectHandle::Unwrap 方法</span><span class="sxs-lookup"><span data-stu-id="81ff3-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="81ff3-103">解包从间接寻址的按值封送的对象。</span><span class="sxs-lookup"><span data-stu-id="81ff3-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81ff3-104">语法</span><span class="sxs-lookup"><span data-stu-id="81ff3-104">Syntax</span></span>  
  
```  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81ff3-105">参数</span><span class="sxs-lookup"><span data-stu-id="81ff3-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="81ff3-106">[out]指向要解包的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="81ff3-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81ff3-107">要求</span><span class="sxs-lookup"><span data-stu-id="81ff3-107">Requirements</span></span>  
 <span data-ttu-id="81ff3-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="81ff3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81ff3-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="81ff3-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81ff3-110">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="81ff3-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81ff3-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81ff3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81ff3-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="81ff3-112">See also</span></span>

