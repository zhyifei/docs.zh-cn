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
ms.openlocfilehash: 4c18607d5373b415228846350a3dd0637ade1b45
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150795"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="54866-102">IObjectHandle::Unwrap 方法</span><span class="sxs-lookup"><span data-stu-id="54866-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="54866-103">解包从间接寻址的按值封送的对象。</span><span class="sxs-lookup"><span data-stu-id="54866-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54866-104">语法</span><span class="sxs-lookup"><span data-stu-id="54866-104">Syntax</span></span>  
  
```  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54866-105">参数</span><span class="sxs-lookup"><span data-stu-id="54866-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="54866-106">[out]指向要解包的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="54866-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54866-107">要求</span><span class="sxs-lookup"><span data-stu-id="54866-107">Requirements</span></span>  
 <span data-ttu-id="54866-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="54866-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54866-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="54866-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="54866-110">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="54866-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="54866-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54866-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
