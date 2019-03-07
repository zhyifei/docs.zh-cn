---
title: IAssemblyName::GetVersion 方法
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetVersion
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetVersion
helpviewer_keywords:
- IAssemblyName::GetVersion method [.NET Framework fusion]
- GetVersion method, IAssemblyName interface [.NET Framework fusion]
ms.assetid: 42230928-2c33-41fd-9519-d96efef6c7af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7479e8d1eee0c44544b5923d4de66153cb2c3a19
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490328"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="5496f-102">IAssemblyName::GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="5496f-102">IAssemblyName::GetVersion Method</span></span>
<span data-ttu-id="5496f-103">获取此引用的程序集的版本信息[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="5496f-103">Gets the version information for the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5496f-104">语法</span><span class="sxs-lookup"><span data-stu-id="5496f-104">Syntax</span></span>  
  
```  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5496f-105">参数</span><span class="sxs-lookup"><span data-stu-id="5496f-105">Parameters</span></span>  
 `pdwVersionHi`  
 <span data-ttu-id="5496f-106">[out]高 32 位版本。</span><span class="sxs-lookup"><span data-stu-id="5496f-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="5496f-107">[out]版本的低 32 位。</span><span class="sxs-lookup"><span data-stu-id="5496f-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5496f-108">要求</span><span class="sxs-lookup"><span data-stu-id="5496f-108">Requirements</span></span>  
 <span data-ttu-id="5496f-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5496f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5496f-110">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="5496f-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5496f-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5496f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5496f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="5496f-112">See also</span></span>
- [<span data-ttu-id="5496f-113">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="5496f-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
