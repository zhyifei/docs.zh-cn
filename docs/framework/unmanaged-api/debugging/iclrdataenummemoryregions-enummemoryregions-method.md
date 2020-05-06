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
ms.openlocfilehash: e6cdc924df126e56d2e7c8c9cb8762ee88712fcc
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860698"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="807d3-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions 方法</span><span class="sxs-lookup"><span data-stu-id="807d3-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="807d3-103">枚举指定的内存区域。</span><span class="sxs-lookup"><span data-stu-id="807d3-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="807d3-104">语法</span><span class="sxs-lookup"><span data-stu-id="807d3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="807d3-105">参数</span><span class="sxs-lookup"><span data-stu-id="807d3-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="807d3-106">中指向[ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md)实例的指针，此方法为每个要枚举的内存区域调用此方法，以通知调试器结果。</span><span class="sxs-lookup"><span data-stu-id="807d3-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="807d3-107">即使回调指示失败，内存区域的枚举仍将继续。</span><span class="sxs-lookup"><span data-stu-id="807d3-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="807d3-108">中不使用。</span><span class="sxs-lookup"><span data-stu-id="807d3-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="807d3-109">中[CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md)枚举的一个值，该值指定要枚举的内存区域。</span><span class="sxs-lookup"><span data-stu-id="807d3-109">[in] A value of the [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="807d3-110">备注</span><span class="sxs-lookup"><span data-stu-id="807d3-110">Remarks</span></span>  
 <span data-ttu-id="807d3-111">此方法使用指定的[ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md)实例将结果通知给调用方。</span><span class="sxs-lookup"><span data-stu-id="807d3-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="807d3-112">要求</span><span class="sxs-lookup"><span data-stu-id="807d3-112">Requirements</span></span>  
 <span data-ttu-id="807d3-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="807d3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="807d3-114">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="807d3-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="807d3-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="807d3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="807d3-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="807d3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="807d3-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="807d3-117">See also</span></span>

- [<span data-ttu-id="807d3-118">ICLRDataEnumMemoryRegions 接口</span><span class="sxs-lookup"><span data-stu-id="807d3-118">ICLRDataEnumMemoryRegions Interface</span></span>](iclrdataenummemoryregions-interface.md)
