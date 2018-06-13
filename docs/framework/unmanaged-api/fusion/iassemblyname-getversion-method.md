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
ms.openlocfilehash: 71b9eb6cc5640913c5723f088034d9bcd86c4a43
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428868"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="89c1c-102">IAssemblyName::GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="89c1c-102">IAssemblyName::GetVersion Method</span></span>
<span data-ttu-id="89c1c-103">获取此引用的程序集的版本信息[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="89c1c-103">Gets the version information for the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89c1c-104">语法</span><span class="sxs-lookup"><span data-stu-id="89c1c-104">Syntax</span></span>  
  
```  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="89c1c-105">参数</span><span class="sxs-lookup"><span data-stu-id="89c1c-105">Parameters</span></span>  
 `pdwVersionHi`  
 <span data-ttu-id="89c1c-106">[out]版本的高 32 位。</span><span class="sxs-lookup"><span data-stu-id="89c1c-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="89c1c-107">[out]版本的低 32 位。</span><span class="sxs-lookup"><span data-stu-id="89c1c-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89c1c-108">要求</span><span class="sxs-lookup"><span data-stu-id="89c1c-108">Requirements</span></span>  
 <span data-ttu-id="89c1c-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="89c1c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89c1c-110">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="89c1c-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="89c1c-111">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89c1c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89c1c-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="89c1c-112">See Also</span></span>  
 [<span data-ttu-id="89c1c-113">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="89c1c-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
