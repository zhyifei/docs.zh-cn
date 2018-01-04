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
ms.workload: dotnet
ms.openlocfilehash: 596b174fa4ebac7e54e2f6b5f3ed044686fa515f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="9ff38-102">EMemoryAvailable 枚举</span><span class="sxs-lookup"><span data-stu-id="9ff38-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="9ff38-103">包含表示在计算机上的可用物理内存量的值。</span><span class="sxs-lookup"><span data-stu-id="9ff38-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="9ff38-104">这些值以逻辑方式映射的事件的内存从返回的上限和下限`CreateMemoryResourceNotification`Win32 API 中的函数。</span><span class="sxs-lookup"><span data-stu-id="9ff38-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Win32 API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ff38-105">语法</span><span class="sxs-lookup"><span data-stu-id="9ff38-105">Syntax</span></span>  
  
```  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="9ff38-106">成员</span><span class="sxs-lookup"><span data-stu-id="9ff38-106">Members</span></span>  
  
|<span data-ttu-id="9ff38-107">成员</span><span class="sxs-lookup"><span data-stu-id="9ff38-107">Member</span></span>|<span data-ttu-id="9ff38-108">描述</span><span class="sxs-lookup"><span data-stu-id="9ff38-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="9ff38-109">很多物理内存才可用。</span><span class="sxs-lookup"><span data-stu-id="9ff38-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="9ff38-110">很少的物理内存不可用。</span><span class="sxs-lookup"><span data-stu-id="9ff38-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="9ff38-111">可用的物理内存为中性。</span><span class="sxs-lookup"><span data-stu-id="9ff38-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ff38-112">备注</span><span class="sxs-lookup"><span data-stu-id="9ff38-112">Remarks</span></span>  
 <span data-ttu-id="9ff38-113">此值由传递到公共语言运行时 (CLR) 由主机调用[iclrmemorynotificationcallback:: Onmemorynotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="9ff38-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ff38-114">惠?</span><span class="sxs-lookup"><span data-stu-id="9ff38-114">Requirements</span></span>  
 <span data-ttu-id="9ff38-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9ff38-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ff38-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9ff38-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ff38-117">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9ff38-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ff38-118">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ff38-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ff38-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ff38-119">See Also</span></span>  
 [<span data-ttu-id="9ff38-120">承载枚举</span><span class="sxs-lookup"><span data-stu-id="9ff38-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
