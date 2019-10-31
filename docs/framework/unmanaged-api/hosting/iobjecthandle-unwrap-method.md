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
ms.openlocfilehash: be488ebe663169cabc5b569335dfc784fdf30556
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102691"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="b1408-102">IObjectHandle::Unwrap 方法</span><span class="sxs-lookup"><span data-stu-id="b1408-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="b1408-103">从间接寻址将按值封送对象解包。</span><span class="sxs-lookup"><span data-stu-id="b1408-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1408-104">语法</span><span class="sxs-lookup"><span data-stu-id="b1408-104">Syntax</span></span>  
  
```cpp  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1408-105">参数</span><span class="sxs-lookup"><span data-stu-id="b1408-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="b1408-106">弄指向要解包的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="b1408-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1408-107">要求</span><span class="sxs-lookup"><span data-stu-id="b1408-107">Requirements</span></span>  
 <span data-ttu-id="b1408-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b1408-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1408-109">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b1408-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b1408-110">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b1408-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b1408-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1408-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
