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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 63c3ecd0ae0d9e1df62d73eb05b759093583f652
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142878"
---
# <a name="notifyfilter-enumeration"></a><span data-ttu-id="84ddc-102">NOTIFY_FILTER 枚举</span><span class="sxs-lookup"><span data-stu-id="84ddc-102">NOTIFY_FILTER Enumeration</span></span>
<span data-ttu-id="84ddc-103">标识调试器函数的回调。</span><span class="sxs-lookup"><span data-stu-id="84ddc-103">Identifies callbacks for debugger functions.</span></span> <span data-ttu-id="84ddc-104">有关详细信息，请参阅[INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="84ddc-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84ddc-105">语法</span><span class="sxs-lookup"><span data-stu-id="84ddc-105">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="84ddc-106">成员</span><span class="sxs-lookup"><span data-stu-id="84ddc-106">Members</span></span>  
  
|<span data-ttu-id="84ddc-107">成员</span><span class="sxs-lookup"><span data-stu-id="84ddc-107">Member</span></span>|<span data-ttu-id="84ddc-108">描述</span><span class="sxs-lookup"><span data-stu-id="84ddc-108">Description</span></span>|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|<span data-ttu-id="84ddc-109">指示[INotifySink2::OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md)方法调用。</span><span class="sxs-lookup"><span data-stu-id="84ddc-109">Indicates that the [INotifySink2::OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|<span data-ttu-id="84ddc-110">指示[INotifySink2::OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md)方法调用。</span><span class="sxs-lookup"><span data-stu-id="84ddc-110">Indicates that the [INotifySink2::OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|<span data-ttu-id="84ddc-111">指示[INotifySink2::OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md)方法调用。</span><span class="sxs-lookup"><span data-stu-id="84ddc-111">Indicates that the [INotifySink2::OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|<span data-ttu-id="84ddc-112">指示[INotifySink2::OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md)方法调用。</span><span class="sxs-lookup"><span data-stu-id="84ddc-112">Indicates that the [INotifySink2::OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALLSYNC`|<span data-ttu-id="84ddc-113">表示将所有[INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)不应调用方法。</span><span class="sxs-lookup"><span data-stu-id="84ddc-113">Indicates that all of the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) methods should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALL`|<span data-ttu-id="84ddc-114">激活现有和将来的所有通知。</span><span class="sxs-lookup"><span data-stu-id="84ddc-114">Activates all existing and future notifications.</span></span>|  
|`NOTIFY_FILTER_NONE`|<span data-ttu-id="84ddc-115">指示应调用没有通知方法。</span><span class="sxs-lookup"><span data-stu-id="84ddc-115">Indicates that no notification methods should be invoked.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="84ddc-116">要求</span><span class="sxs-lookup"><span data-stu-id="84ddc-116">Requirements</span></span>  
 <span data-ttu-id="84ddc-117">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="84ddc-117">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84ddc-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="84ddc-118">See also</span></span>

- [<span data-ttu-id="84ddc-119">诊断符号存储区枚举</span><span class="sxs-lookup"><span data-stu-id="84ddc-119">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
