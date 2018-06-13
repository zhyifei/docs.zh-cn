---
title: ITypeName::GetModifiers 方法
ms.date: 03/30/2017
api_name:
- ITypeName.GetModifiers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetModifiers
helpviewer_keywords:
- ITypeName::GetModifiers method [.NET Framework hosting]
- GetModifiers method [.NET Framework hosting]
ms.assetid: 75508c55-3e09-4135-80da-cc811003fa82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66976b99b5686c62ad31c8a0365ce14f1bf33f85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439900"
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="8f7ac-102">ITypeName::GetModifiers 方法</span><span class="sxs-lookup"><span data-stu-id="8f7ac-102">ITypeName::GetModifiers Method</span></span>
<span data-ttu-id="8f7ac-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="8f7ac-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f7ac-104">语法</span><span class="sxs-lookup"><span data-stu-id="8f7ac-104">Syntax</span></span>  
  
```  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="8f7ac-105">要求</span><span class="sxs-lookup"><span data-stu-id="8f7ac-105">Requirements</span></span>  
 <span data-ttu-id="8f7ac-106">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8f7ac-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f7ac-107">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8f7ac-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f7ac-108">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8f7ac-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f7ac-109">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f7ac-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f7ac-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f7ac-110">See Also</span></span>  
 [<span data-ttu-id="8f7ac-111">承载接口</span><span class="sxs-lookup"><span data-stu-id="8f7ac-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
