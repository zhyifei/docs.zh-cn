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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 76fc5f578e6da731ffd6406344d00cda8b57f493
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772404"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="4fc13-102">EMemoryAvailable 枚举</span><span class="sxs-lookup"><span data-stu-id="4fc13-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="4fc13-103">包含指示计算机上的可用物理内存量的值。</span><span class="sxs-lookup"><span data-stu-id="4fc13-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="4fc13-104">这些值以逻辑方式映射到事件的内存从返回的上限和下限`CreateMemoryResourceNotification`Windows API 中的函数。</span><span class="sxs-lookup"><span data-stu-id="4fc13-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fc13-105">语法</span><span class="sxs-lookup"><span data-stu-id="4fc13-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="4fc13-106">成员</span><span class="sxs-lookup"><span data-stu-id="4fc13-106">Members</span></span>  
  
|<span data-ttu-id="4fc13-107">成员</span><span class="sxs-lookup"><span data-stu-id="4fc13-107">Member</span></span>|<span data-ttu-id="4fc13-108">描述</span><span class="sxs-lookup"><span data-stu-id="4fc13-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="4fc13-109">提供足够的物理内存。</span><span class="sxs-lookup"><span data-stu-id="4fc13-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="4fc13-110">很少的物理内存不可用。</span><span class="sxs-lookup"><span data-stu-id="4fc13-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="4fc13-111">可用物理内存为中性。</span><span class="sxs-lookup"><span data-stu-id="4fc13-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fc13-112">备注</span><span class="sxs-lookup"><span data-stu-id="4fc13-112">Remarks</span></span>  
 <span data-ttu-id="4fc13-113">此值传递由公共语言运行时 (CLR) 由宿主通过调用[iclrmemorynotificationcallback:: Onmemorynotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="4fc13-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fc13-114">要求</span><span class="sxs-lookup"><span data-stu-id="4fc13-114">Requirements</span></span>  
 <span data-ttu-id="4fc13-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4fc13-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fc13-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4fc13-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4fc13-117">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4fc13-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4fc13-118">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fc13-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc13-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="4fc13-119">See also</span></span>

- [<span data-ttu-id="4fc13-120">承载枚举</span><span class="sxs-lookup"><span data-stu-id="4fc13-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
