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
ms.openlocfilehash: dc5bed553ac54eb708beae23f5c29cbedcb2b4e0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749062"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="1b54e-102">IObjectHandle::Unwrap 方法</span><span class="sxs-lookup"><span data-stu-id="1b54e-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="1b54e-103">解包从间接寻址的按值封送的对象。</span><span class="sxs-lookup"><span data-stu-id="1b54e-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b54e-104">语法</span><span class="sxs-lookup"><span data-stu-id="1b54e-104">Syntax</span></span>  
  
```cpp  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b54e-105">参数</span><span class="sxs-lookup"><span data-stu-id="1b54e-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="1b54e-106">[out]指向要解包的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="1b54e-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b54e-107">要求</span><span class="sxs-lookup"><span data-stu-id="1b54e-107">Requirements</span></span>  
 <span data-ttu-id="1b54e-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1b54e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b54e-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1b54e-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b54e-110">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1b54e-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b54e-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b54e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
