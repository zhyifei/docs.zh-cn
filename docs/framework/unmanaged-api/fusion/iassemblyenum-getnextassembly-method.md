---
title: "IAssemblyEnum::GetNextAssembly 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2666970e220334e9e8c2470622026442db0c2f95
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="d8a42-102">IAssemblyEnum::GetNextAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="d8a42-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="d8a42-103">获取一个指针指向下一步[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)包含在此[IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="d8a42-103">Gets a pointer to the next [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) contained in this [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8a42-104">语法</span><span class="sxs-lookup"><span data-stu-id="d8a42-104">Syntax</span></span>  
  
```  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d8a42-105">参数</span><span class="sxs-lookup"><span data-stu-id="d8a42-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="d8a42-106">[in]留待将来扩展。</span><span class="sxs-lookup"><span data-stu-id="d8a42-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="d8a42-107">`pvReserved`必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="d8a42-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="d8a42-108">[out]返回`IAssemblyName`指针。</span><span class="sxs-lookup"><span data-stu-id="d8a42-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d8a42-109">[in]留待将来扩展。</span><span class="sxs-lookup"><span data-stu-id="d8a42-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="d8a42-110">`dwFlags`必须为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="d8a42-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8a42-111">惠?</span><span class="sxs-lookup"><span data-stu-id="d8a42-111">Requirements</span></span>  
 <span data-ttu-id="d8a42-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d8a42-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8a42-113">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="d8a42-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d8a42-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8a42-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8a42-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8a42-115">See Also</span></span>  
 [<span data-ttu-id="d8a42-116">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="d8a42-116">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="d8a42-117">IAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="d8a42-117">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
