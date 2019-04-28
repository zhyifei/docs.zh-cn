---
title: ICLRDataEnumMemoryRegions::EnumMemoryRegions 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 886f78a0561ebbd5470b7932123f67975d650693
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698260"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="ba353-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions 方法</span><span class="sxs-lookup"><span data-stu-id="ba353-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="ba353-103">枚举指定的内存区域。</span><span class="sxs-lookup"><span data-stu-id="ba353-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba353-104">语法</span><span class="sxs-lookup"><span data-stu-id="ba353-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba353-105">参数</span><span class="sxs-lookup"><span data-stu-id="ba353-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="ba353-106">[in]一个指向[ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)调用此方法对于枚举通知调试器结果的每个内存区域的实例。</span><span class="sxs-lookup"><span data-stu-id="ba353-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="ba353-107">即使该回调指示失败，将继续内存区域的枚举。</span><span class="sxs-lookup"><span data-stu-id="ba353-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="ba353-108">[in]不使用。</span><span class="sxs-lookup"><span data-stu-id="ba353-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="ba353-109">[in]值为[CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md)枚举，用于指定要枚举的内存区域。</span><span class="sxs-lookup"><span data-stu-id="ba353-109">[in] A value of the [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba353-110">备注</span><span class="sxs-lookup"><span data-stu-id="ba353-110">Remarks</span></span>  
 <span data-ttu-id="ba353-111">此方法使用指定[ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)实例，以通知调用方的结果。</span><span class="sxs-lookup"><span data-stu-id="ba353-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba353-112">要求</span><span class="sxs-lookup"><span data-stu-id="ba353-112">Requirements</span></span>  
 <span data-ttu-id="ba353-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ba353-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba353-114">**标头：** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="ba353-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="ba353-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba353-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba353-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba353-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba353-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba353-117">See also</span></span>

- [<span data-ttu-id="ba353-118">ICLRDataEnumMemoryRegions 接口</span><span class="sxs-lookup"><span data-stu-id="ba353-118">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)
