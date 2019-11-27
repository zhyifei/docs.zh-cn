---
title: NOTIFY_FILTER 枚举
ms.date: 03/30/2017
api_name:
- NOTIFY_FILTER
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- NOTIFY_FILTER
helpviewer_keywords:
- NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type:
- apiref
ms.openlocfilehash: 92e40dbe8892d48dba1c54d9cd16faa409440b24
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438117"
---
# <a name="notify_filter-enumeration"></a><span data-ttu-id="c53e9-102">NOTIFY_FILTER 枚举</span><span class="sxs-lookup"><span data-stu-id="c53e9-102">NOTIFY_FILTER Enumeration</span></span>
<span data-ttu-id="c53e9-103">标识调试器函数的回调。</span><span class="sxs-lookup"><span data-stu-id="c53e9-103">Identifies callbacks for debugger functions.</span></span> <span data-ttu-id="c53e9-104">有关详细信息，请参阅[INotifySource2：： SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="c53e9-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c53e9-105">语法</span><span class="sxs-lookup"><span data-stu-id="c53e9-105">Syntax</span></span>  
  
```cpp  
enum tagNOTIFY_FILTER  
{  
    NOTIFY_FILTER_ONSYNCCALLOUT    = 0x1,  
    NOTIFY_FILTER_ONSYNCCALLENTER  = 0x2,  
    NOTIFY_FILTER_ONSYNCCALLEXIT   = 0x4,  
    NOTIFY_FILTER_ONSYNCCALLRETURN = 0x8,  
    NOTIFY_FILTER_ALLSYNC = NOTIFY_FILTER_ONSYNCCALLOUT | NOTIFY_FILTER_ONSYNCCALLENTER | NOTIFY_FILTER_ONSYNCCALLEXIT | NOTIFY_FILTER_ONSYNCCALLRETURN,  
    NOTIFY_FILTER_ALL              = 0xffffffff,  
    NOTIFY_FILTER_NONE             = 0  
};  
```  
  
## <a name="members"></a><span data-ttu-id="c53e9-106">Members</span><span class="sxs-lookup"><span data-stu-id="c53e9-106">Members</span></span>  
  
|<span data-ttu-id="c53e9-107">成员</span><span class="sxs-lookup"><span data-stu-id="c53e9-107">Member</span></span>|<span data-ttu-id="c53e9-108">说明</span><span class="sxs-lookup"><span data-stu-id="c53e9-108">Description</span></span>|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|<span data-ttu-id="c53e9-109">指示应调用[INotifySink2：： OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="c53e9-109">Indicates that the [INotifySink2::OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|<span data-ttu-id="c53e9-110">指示应调用[INotifySink2：： OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="c53e9-110">Indicates that the [INotifySink2::OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|<span data-ttu-id="c53e9-111">指示应调用[INotifySink2：： OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="c53e9-111">Indicates that the [INotifySink2::OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|<span data-ttu-id="c53e9-112">指示应调用[INotifySink2：： OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="c53e9-112">Indicates that the [INotifySink2::OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALLSYNC`|<span data-ttu-id="c53e9-113">指示应调用所有[INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)方法。</span><span class="sxs-lookup"><span data-stu-id="c53e9-113">Indicates that all of the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) methods should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALL`|<span data-ttu-id="c53e9-114">激活所有现有和未来的通知。</span><span class="sxs-lookup"><span data-stu-id="c53e9-114">Activates all existing and future notifications.</span></span>|  
|`NOTIFY_FILTER_NONE`|<span data-ttu-id="c53e9-115">指示不应调用任何通知方法。</span><span class="sxs-lookup"><span data-stu-id="c53e9-115">Indicates that no notification methods should be invoked.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c53e9-116">要求</span><span class="sxs-lookup"><span data-stu-id="c53e9-116">Requirements</span></span>  
 <span data-ttu-id="c53e9-117">**标头：** ProtocolNotify2 .idl</span><span class="sxs-lookup"><span data-stu-id="c53e9-117">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c53e9-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c53e9-118">See also</span></span>

- [<span data-ttu-id="c53e9-119">诊断符号存储区枚举</span><span class="sxs-lookup"><span data-stu-id="c53e9-119">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
