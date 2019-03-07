---
title: CreateAssemblyEnum 函数
ms.date: 03/30/2017
api_name:
- CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyEnum
helpviewer_keywords:
- CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d9671354edfeb4a320a451f355c2125dc8e9dc5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470022"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="1f284-102">CreateAssemblyEnum 函数</span><span class="sxs-lookup"><span data-stu-id="1f284-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="1f284-103">获取一个指向[IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)可以枚举中具有指定的程序集的对象的实例[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="1f284-103">Gets a pointer to an [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f284-104">语法</span><span class="sxs-lookup"><span data-stu-id="1f284-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f284-105">参数</span><span class="sxs-lookup"><span data-stu-id="1f284-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="1f284-106">[out]指向包含所请求的内存位置`IAssemblyEnum`指针。</span><span class="sxs-lookup"><span data-stu-id="1f284-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="1f284-107">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="1f284-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="1f284-108">`pUnkReserved` 必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="1f284-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="1f284-109">[in]`IAssemblyName`的请求的程序集。</span><span class="sxs-lookup"><span data-stu-id="1f284-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="1f284-110">此名称用于筛选枚举。</span><span class="sxs-lookup"><span data-stu-id="1f284-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="1f284-111">它可以为 null 以枚举在全局程序集缓存中的所有程序集。</span><span class="sxs-lookup"><span data-stu-id="1f284-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="1f284-112">[in]用于修改枚举器的行为的标志。</span><span class="sxs-lookup"><span data-stu-id="1f284-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="1f284-113">此参数包含中的一位完全[ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="1f284-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="1f284-114">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="1f284-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="1f284-115">`pvReserved` 必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="1f284-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f284-116">备注</span><span class="sxs-lookup"><span data-stu-id="1f284-116">Remarks</span></span>  
 <span data-ttu-id="1f284-117">`dwFlags`参数包含一位完全从`ASM_CACHE_FLAGS`枚举。</span><span class="sxs-lookup"><span data-stu-id="1f284-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f284-118">要求</span><span class="sxs-lookup"><span data-stu-id="1f284-118">Requirements</span></span>  
 <span data-ttu-id="1f284-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1f284-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f284-120">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="1f284-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1f284-121">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1f284-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1f284-122">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f284-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f284-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f284-123">See also</span></span>
- [<span data-ttu-id="1f284-124">IAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="1f284-124">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
- [<span data-ttu-id="1f284-125">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="1f284-125">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="1f284-126">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="1f284-126">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
