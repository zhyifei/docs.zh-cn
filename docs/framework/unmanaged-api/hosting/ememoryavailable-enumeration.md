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
ms.openlocfilehash: 0073a532f680d8764ec9e76ea22326a630457043
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176430"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="672e6-102">EMemoryAvailable 枚举</span><span class="sxs-lookup"><span data-stu-id="672e6-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="672e6-103">包含指示计算机上可用物理内存量的值。</span><span class="sxs-lookup"><span data-stu-id="672e6-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="672e6-104">这些值以逻辑方式映射到 Windows API 中`CreateMemoryResourceNotification`函数返回的高内存和低内存的事件。</span><span class="sxs-lookup"><span data-stu-id="672e6-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="672e6-105">语法</span><span class="sxs-lookup"><span data-stu-id="672e6-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="672e6-106">成员</span><span class="sxs-lookup"><span data-stu-id="672e6-106">Members</span></span>  
  
|<span data-ttu-id="672e6-107">成员</span><span class="sxs-lookup"><span data-stu-id="672e6-107">Member</span></span>|<span data-ttu-id="672e6-108">说明</span><span class="sxs-lookup"><span data-stu-id="672e6-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="672e6-109">大量的物理内存可用。</span><span class="sxs-lookup"><span data-stu-id="672e6-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="672e6-110">几乎没有可用的物理内存。</span><span class="sxs-lookup"><span data-stu-id="672e6-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="672e6-111">可用的物理内存是中性的。</span><span class="sxs-lookup"><span data-stu-id="672e6-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="672e6-112">备注</span><span class="sxs-lookup"><span data-stu-id="672e6-112">Remarks</span></span>  
 <span data-ttu-id="672e6-113">此值由主机传递到通用语言运行时 （CLR），方法是使用对[ICLR 内存通知回调的调用：：在内存通知方法上](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)。</span><span class="sxs-lookup"><span data-stu-id="672e6-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="672e6-114">要求</span><span class="sxs-lookup"><span data-stu-id="672e6-114">Requirements</span></span>  
 <span data-ttu-id="672e6-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="672e6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="672e6-116">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="672e6-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="672e6-117">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="672e6-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="672e6-118">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="672e6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="672e6-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="672e6-119">See also</span></span>

- [<span data-ttu-id="672e6-120">承载枚举</span><span class="sxs-lookup"><span data-stu-id="672e6-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
