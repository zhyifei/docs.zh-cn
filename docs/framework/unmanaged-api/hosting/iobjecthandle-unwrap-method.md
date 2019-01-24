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
ms.openlocfilehash: da25055917743481f5a8314023ed94d552fe49ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526413"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="fb845-102">IObjectHandle::Unwrap 方法</span><span class="sxs-lookup"><span data-stu-id="fb845-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="fb845-103">解包从间接寻址的按值封送的对象。</span><span class="sxs-lookup"><span data-stu-id="fb845-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb845-104">语法</span><span class="sxs-lookup"><span data-stu-id="fb845-104">Syntax</span></span>  
  
```  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb845-105">参数</span><span class="sxs-lookup"><span data-stu-id="fb845-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="fb845-106">[out]指向要解包的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="fb845-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb845-107">要求</span><span class="sxs-lookup"><span data-stu-id="fb845-107">Requirements</span></span>  
 <span data-ttu-id="fb845-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fb845-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb845-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fb845-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb845-110">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fb845-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb845-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb845-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb845-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb845-112">See also</span></span>

