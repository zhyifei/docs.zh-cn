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
ms.openlocfilehash: 78d86aff385bbff479c57d8902fbd0973a6ad1bc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59226412"
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="78248-102">ITypeName::GetModifiers 方法</span><span class="sxs-lookup"><span data-stu-id="78248-102">ITypeName::GetModifiers Method</span></span>
<span data-ttu-id="78248-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="78248-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78248-104">语法</span><span class="sxs-lookup"><span data-stu-id="78248-104">Syntax</span></span>  
  
```  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="78248-105">要求</span><span class="sxs-lookup"><span data-stu-id="78248-105">Requirements</span></span>  
 <span data-ttu-id="78248-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="78248-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78248-107">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="78248-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="78248-108">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="78248-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78248-109">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78248-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78248-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="78248-110">See also</span></span>

- [<span data-ttu-id="78248-111">承载接口</span><span class="sxs-lookup"><span data-stu-id="78248-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
