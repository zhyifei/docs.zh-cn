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
ms.openlocfilehash: e5b5f7ce6a4ce8f542b3c49fe4749bfde23ecf84
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744489"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="e1e4d-102">IAssemblyName::GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="e1e4d-102">IAssemblyName::GetVersion Method</span></span>
<span data-ttu-id="e1e4d-103">获取此引用的程序集的版本信息[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="e1e4d-103">Gets the version information for the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1e4d-104">语法</span><span class="sxs-lookup"><span data-stu-id="e1e4d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1e4d-105">参数</span><span class="sxs-lookup"><span data-stu-id="e1e4d-105">Parameters</span></span>  
 `pdwVersionHi`  
 <span data-ttu-id="e1e4d-106">[out]高 32 位版本。</span><span class="sxs-lookup"><span data-stu-id="e1e4d-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="e1e4d-107">[out]版本的低 32 位。</span><span class="sxs-lookup"><span data-stu-id="e1e4d-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1e4d-108">要求</span><span class="sxs-lookup"><span data-stu-id="e1e4d-108">Requirements</span></span>  
 <span data-ttu-id="e1e4d-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e1e4d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1e4d-110">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="e1e4d-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e1e4d-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1e4d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e4d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1e4d-112">See also</span></span>

- [<span data-ttu-id="e1e4d-113">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="e1e4d-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
