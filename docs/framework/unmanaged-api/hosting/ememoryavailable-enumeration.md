---
title: "EMemoryAvailable 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EMemoryAvailable
api_location: mscoree.dll
api_type: COM
f1_keywords: EMemoryAvailable
helpviewer_keywords: EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c378f2cd9b033e578ff15472a10a6dc295ad6539
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="c21b0-102">EMemoryAvailable 枚举</span><span class="sxs-lookup"><span data-stu-id="c21b0-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="c21b0-103">包含表示在计算机上的可用物理内存量的值。</span><span class="sxs-lookup"><span data-stu-id="c21b0-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="c21b0-104">这些值以逻辑方式映射的事件的内存从返回的上限和下限`CreateMemoryResourceNotification`Win32 API 中的函数。</span><span class="sxs-lookup"><span data-stu-id="c21b0-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Win32 API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c21b0-105">语法</span><span class="sxs-lookup"><span data-stu-id="c21b0-105">Syntax</span></span>  
  
```  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="c21b0-106">成员</span><span class="sxs-lookup"><span data-stu-id="c21b0-106">Members</span></span>  
  
|<span data-ttu-id="c21b0-107">成员</span><span class="sxs-lookup"><span data-stu-id="c21b0-107">Member</span></span>|<span data-ttu-id="c21b0-108">描述</span><span class="sxs-lookup"><span data-stu-id="c21b0-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="c21b0-109">很多物理内存才可用。</span><span class="sxs-lookup"><span data-stu-id="c21b0-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="c21b0-110">很少的物理内存不可用。</span><span class="sxs-lookup"><span data-stu-id="c21b0-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="c21b0-111">可用的物理内存为中性。</span><span class="sxs-lookup"><span data-stu-id="c21b0-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c21b0-112">备注</span><span class="sxs-lookup"><span data-stu-id="c21b0-112">Remarks</span></span>  
 <span data-ttu-id="c21b0-113">此值由传递到公共语言运行时 (CLR) 由主机调用[iclrmemorynotificationcallback:: Onmemorynotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="c21b0-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c21b0-114">要求</span><span class="sxs-lookup"><span data-stu-id="c21b0-114">Requirements</span></span>  
 <span data-ttu-id="c21b0-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c21b0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c21b0-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c21b0-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c21b0-117">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c21b0-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c21b0-118">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c21b0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c21b0-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c21b0-119">See Also</span></span>  
 [<span data-ttu-id="c21b0-120">承载枚举</span><span class="sxs-lookup"><span data-stu-id="c21b0-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
