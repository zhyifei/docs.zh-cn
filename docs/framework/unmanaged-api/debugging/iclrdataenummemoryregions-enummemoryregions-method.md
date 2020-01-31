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
ms.openlocfilehash: f2b2bbe8bcecf71f6d3016fb35dfbf5ba1353aea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785637"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="61cd5-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions 方法</span><span class="sxs-lookup"><span data-stu-id="61cd5-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="61cd5-103">枚举指定的内存区域。</span><span class="sxs-lookup"><span data-stu-id="61cd5-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61cd5-104">语法</span><span class="sxs-lookup"><span data-stu-id="61cd5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61cd5-105">参数</span><span class="sxs-lookup"><span data-stu-id="61cd5-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="61cd5-106">中指向[ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md)实例的指针，此方法为每个要枚举的内存区域调用此方法，以通知调试器结果。</span><span class="sxs-lookup"><span data-stu-id="61cd5-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="61cd5-107">即使回调指示失败，内存区域的枚举仍将继续。</span><span class="sxs-lookup"><span data-stu-id="61cd5-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="61cd5-108">中不使用。</span><span class="sxs-lookup"><span data-stu-id="61cd5-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="61cd5-109">中[CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md)枚举的一个值，该值指定要枚举的内存区域。</span><span class="sxs-lookup"><span data-stu-id="61cd5-109">[in] A value of the [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61cd5-110">备注</span><span class="sxs-lookup"><span data-stu-id="61cd5-110">Remarks</span></span>  
 <span data-ttu-id="61cd5-111">此方法使用指定的[ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md)实例将结果通知给调用方。</span><span class="sxs-lookup"><span data-stu-id="61cd5-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61cd5-112">需求</span><span class="sxs-lookup"><span data-stu-id="61cd5-112">Requirements</span></span>  
 <span data-ttu-id="61cd5-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="61cd5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61cd5-114">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="61cd5-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="61cd5-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61cd5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61cd5-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61cd5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61cd5-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61cd5-117">See also</span></span>

- [<span data-ttu-id="61cd5-118">ICLRDataEnumMemoryRegions 接口</span><span class="sxs-lookup"><span data-stu-id="61cd5-118">ICLRDataEnumMemoryRegions Interface</span></span>](iclrdataenummemoryregions-interface.md)
