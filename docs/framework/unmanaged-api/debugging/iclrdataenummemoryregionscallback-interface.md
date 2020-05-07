---
title: ICLRDataEnumMemoryRegionsCallback 接口
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords:
- ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type:
- apiref
ms.openlocfilehash: ddcb8064dfb9be30c66404a8762a9ca73cd6afe4
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860660"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="65c4d-102">ICLRDataEnumMemoryRegionsCallback 接口</span><span class="sxs-lookup"><span data-stu-id="65c4d-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="65c4d-103">为[ICLRDataEnumMemoryRegions：： EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md)提供回调方法，以便向调试器报告尝试枚举指定的内存区域的结果。</span><span class="sxs-lookup"><span data-stu-id="65c4d-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="65c4d-104">方法</span><span class="sxs-lookup"><span data-stu-id="65c4d-104">Methods</span></span>  
  
|<span data-ttu-id="65c4d-105">方法</span><span class="sxs-lookup"><span data-stu-id="65c4d-105">Method</span></span>|<span data-ttu-id="65c4d-106">说明</span><span class="sxs-lookup"><span data-stu-id="65c4d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="65c4d-107">EnumMemoryRegion 方法</span><span class="sxs-lookup"><span data-stu-id="65c4d-107">EnumMemoryRegion Method</span></span>](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="65c4d-108">由`ICLRDataEnumMemoryRegions::EnumMemoryRegions`调用，以向调试器报告尝试枚举指定的内存区域的结果。</span><span class="sxs-lookup"><span data-stu-id="65c4d-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="65c4d-109">要求</span><span class="sxs-lookup"><span data-stu-id="65c4d-109">Requirements</span></span>  
 <span data-ttu-id="65c4d-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="65c4d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65c4d-111">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="65c4d-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="65c4d-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65c4d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65c4d-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65c4d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65c4d-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65c4d-114">See also</span></span>

- [<span data-ttu-id="65c4d-115">调试接口</span><span class="sxs-lookup"><span data-stu-id="65c4d-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
