---
title: "ICLRDataEnumMemoryRegions::EnumMemoryRegions 方法"
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
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1685b1f739519485e5e68928b29a874587e6f9c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="5fd09-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions 方法</span><span class="sxs-lookup"><span data-stu-id="5fd09-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="5fd09-103">枚举指定的内存区域。</span><span class="sxs-lookup"><span data-stu-id="5fd09-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fd09-104">语法</span><span class="sxs-lookup"><span data-stu-id="5fd09-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5fd09-105">参数</span><span class="sxs-lookup"><span data-stu-id="5fd09-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="5fd09-106">[in]指向的指针[ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)称为通过此方法用于通知的结果的调试器正在枚举每个内存区域的实例。</span><span class="sxs-lookup"><span data-stu-id="5fd09-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="5fd09-107">即使回调指示失败，将继续的内存区域的枚举。</span><span class="sxs-lookup"><span data-stu-id="5fd09-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="5fd09-108">[in]未使用。</span><span class="sxs-lookup"><span data-stu-id="5fd09-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="5fd09-109">[in]值为[CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md)指定要枚举的内存区域的枚举。</span><span class="sxs-lookup"><span data-stu-id="5fd09-109">[in] A value of the [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fd09-110">备注</span><span class="sxs-lookup"><span data-stu-id="5fd09-110">Remarks</span></span>  
 <span data-ttu-id="5fd09-111">此方法使用指定[ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)实例以通知结果的调用方。</span><span class="sxs-lookup"><span data-stu-id="5fd09-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fd09-112">惠?</span><span class="sxs-lookup"><span data-stu-id="5fd09-112">Requirements</span></span>  
 <span data-ttu-id="5fd09-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5fd09-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fd09-114">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="5fd09-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5fd09-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fd09-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fd09-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fd09-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fd09-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="5fd09-117">See Also</span></span>  
 [<span data-ttu-id="5fd09-118">ICLRDataEnumMemoryRegions 接口</span><span class="sxs-lookup"><span data-stu-id="5fd09-118">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)
