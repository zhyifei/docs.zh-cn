---
title: EMemoryAvailable 枚举
ms.date: 03/30/2017
api_name:
- EMemoryAvailable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryAvailable
helpviewer_keywords:
- EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type:
- apiref
ms.openlocfilehash: aec3c5f140df7eab10ea2bfa33634a4d853adcb0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134292"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="bec92-102">EMemoryAvailable 枚举</span><span class="sxs-lookup"><span data-stu-id="bec92-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="bec92-103">包含指示计算机上的可用物理内存量的值。</span><span class="sxs-lookup"><span data-stu-id="bec92-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="bec92-104">这些值从逻辑上映射到 Windows API 中 `CreateMemoryResourceNotification` 函数返回的高和低内存的事件。</span><span class="sxs-lookup"><span data-stu-id="bec92-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bec92-105">语法</span><span class="sxs-lookup"><span data-stu-id="bec92-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="bec92-106">Members</span><span class="sxs-lookup"><span data-stu-id="bec92-106">Members</span></span>  
  
|<span data-ttu-id="bec92-107">成员</span><span class="sxs-lookup"><span data-stu-id="bec92-107">Member</span></span>|<span data-ttu-id="bec92-108">描述</span><span class="sxs-lookup"><span data-stu-id="bec92-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="bec92-109">有大量物理内存可用。</span><span class="sxs-lookup"><span data-stu-id="bec92-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="bec92-110">物理内存非常少。</span><span class="sxs-lookup"><span data-stu-id="bec92-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="bec92-111">可用物理内存为中性。</span><span class="sxs-lookup"><span data-stu-id="bec92-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bec92-112">备注</span><span class="sxs-lookup"><span data-stu-id="bec92-112">Remarks</span></span>  
 <span data-ttu-id="bec92-113">使用对[ICLRMemoryNotificationCallback：： OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)方法的调用，此值由主机传递到公共语言运行时（CLR）。</span><span class="sxs-lookup"><span data-stu-id="bec92-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bec92-114">要求</span><span class="sxs-lookup"><span data-stu-id="bec92-114">Requirements</span></span>  
 <span data-ttu-id="bec92-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bec92-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bec92-116">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bec92-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bec92-117">**库：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bec92-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bec92-118">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bec92-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bec92-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="bec92-119">See also</span></span>

- [<span data-ttu-id="bec92-120">承载枚举</span><span class="sxs-lookup"><span data-stu-id="bec92-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
