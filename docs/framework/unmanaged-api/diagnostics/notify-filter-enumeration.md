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
ms.openlocfilehash: fcd1d7fb1fdcd8b1ad1abf159a7828e51be392a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735761"
---
# <a name="notifyfilter-enumeration"></a><span data-ttu-id="6e003-102">NOTIFY_FILTER 枚举</span><span class="sxs-lookup"><span data-stu-id="6e003-102">NOTIFY_FILTER Enumeration</span></span>
<span data-ttu-id="6e003-103">标识调试器函数的回调。</span><span class="sxs-lookup"><span data-stu-id="6e003-103">Identifies callbacks for debugger functions.</span></span> <span data-ttu-id="6e003-104">有关详细信息，请参阅[INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6e003-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e003-105">语法</span><span class="sxs-lookup"><span data-stu-id="6e003-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="6e003-106">成员</span><span class="sxs-lookup"><span data-stu-id="6e003-106">Members</span></span>  
  
|<span data-ttu-id="6e003-107">成员</span><span class="sxs-lookup"><span data-stu-id="6e003-107">Member</span></span>|<span data-ttu-id="6e003-108">描述</span><span class="sxs-lookup"><span data-stu-id="6e003-108">Description</span></span>|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|<span data-ttu-id="6e003-109">指示[INotifySink2::OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md)方法调用。</span><span class="sxs-lookup"><span data-stu-id="6e003-109">Indicates that the [INotifySink2::OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|<span data-ttu-id="6e003-110">指示[INotifySink2::OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md)方法调用。</span><span class="sxs-lookup"><span data-stu-id="6e003-110">Indicates that the [INotifySink2::OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|<span data-ttu-id="6e003-111">指示[INotifySink2::OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md)方法调用。</span><span class="sxs-lookup"><span data-stu-id="6e003-111">Indicates that the [INotifySink2::OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|<span data-ttu-id="6e003-112">指示[INotifySink2::OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md)方法调用。</span><span class="sxs-lookup"><span data-stu-id="6e003-112">Indicates that the [INotifySink2::OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALLSYNC`|<span data-ttu-id="6e003-113">表示将所有[INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)不应调用方法。</span><span class="sxs-lookup"><span data-stu-id="6e003-113">Indicates that all of the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) methods should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALL`|<span data-ttu-id="6e003-114">激活现有和将来的所有通知。</span><span class="sxs-lookup"><span data-stu-id="6e003-114">Activates all existing and future notifications.</span></span>|  
|`NOTIFY_FILTER_NONE`|<span data-ttu-id="6e003-115">指示应调用没有通知方法。</span><span class="sxs-lookup"><span data-stu-id="6e003-115">Indicates that no notification methods should be invoked.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6e003-116">要求</span><span class="sxs-lookup"><span data-stu-id="6e003-116">Requirements</span></span>  
 <span data-ttu-id="6e003-117">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="6e003-117">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e003-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e003-118">See also</span></span>
- [<span data-ttu-id="6e003-119">诊断符号存储区枚举</span><span class="sxs-lookup"><span data-stu-id="6e003-119">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
