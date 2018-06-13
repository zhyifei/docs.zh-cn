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
ms.openlocfilehash: 0d9a8f9aa910054a4541e4ff8c1f7cad63077ba8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439945"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="098b4-102">IObjectHandle::Unwrap 方法</span><span class="sxs-lookup"><span data-stu-id="098b4-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="098b4-103">解包中间接寻址的封送按值对象。</span><span class="sxs-lookup"><span data-stu-id="098b4-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="098b4-104">语法</span><span class="sxs-lookup"><span data-stu-id="098b4-104">Syntax</span></span>  
  
```  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="098b4-105">参数</span><span class="sxs-lookup"><span data-stu-id="098b4-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="098b4-106">[out]指向要为解包的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="098b4-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="098b4-107">要求</span><span class="sxs-lookup"><span data-stu-id="098b4-107">Requirements</span></span>  
 <span data-ttu-id="098b4-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="098b4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="098b4-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="098b4-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="098b4-110">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="098b4-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="098b4-111">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="098b4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="098b4-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="098b4-112">See Also</span></span>  
 
