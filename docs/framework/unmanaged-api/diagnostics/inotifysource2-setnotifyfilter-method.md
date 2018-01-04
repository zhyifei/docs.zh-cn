---
title: "INotifySource2::SetNotifyFilter 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: INotifySource2.SetNotifyFilter
api_location: diasymreader.dll
api_type: COM
f1_keywords: INotifySource2::SetNotifyFilter
helpviewer_keywords:
- INotifySource2::SetNotifyFilter method [.NET Framework debugging]
- SetNotifyFilter method [.NET Framework debugging]
ms.assetid: 6351fc92-b126-4af6-9bf3-0a8ce92845fc
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bba34a9e28d1995ca04c7108ce33adc6e676b357
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="inotifysource2setnotifyfilter-method"></a><span data-ttu-id="48b04-102">INotifySource2::SetNotifyFilter 方法</span><span class="sxs-lookup"><span data-stu-id="48b04-102">INotifySource2::SetNotifyFilter Method</span></span>
<span data-ttu-id="48b04-103">将分配与此源使用通知筛选器。</span><span class="sxs-lookup"><span data-stu-id="48b04-103">Assigns a notification filter for use with this source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48b04-104">语法</span><span class="sxs-lookup"><span data-stu-id="48b04-104">Syntax</span></span>  
  
```  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="48b04-105">参数</span><span class="sxs-lookup"><span data-stu-id="48b04-105">Parameters</span></span>  
 `in_NotifyFilter`  
 <span data-ttu-id="48b04-106">[in]按位组合[NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md)标识调试器 API 回调的枚举值。</span><span class="sxs-lookup"><span data-stu-id="48b04-106">[in] A bitwise combination of the [NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md) enumeration values that identify callbacks for the debugger API.</span></span>  
  
 `in_pUserThreadFilter`  
 <span data-ttu-id="48b04-107">[in]指向的指针[USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md)标识调试器 API 的线程的结构。</span><span class="sxs-lookup"><span data-stu-id="48b04-107">[in] A pointer to a [USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md) structure that identifies threads for the debugger API.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48b04-108">返回值</span><span class="sxs-lookup"><span data-stu-id="48b04-108">Return Value</span></span>  
 <span data-ttu-id="48b04-109">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="48b04-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48b04-110">惠?</span><span class="sxs-lookup"><span data-stu-id="48b04-110">Requirements</span></span>  
 <span data-ttu-id="48b04-111">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="48b04-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48b04-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="48b04-112">See Also</span></span>  
 [<span data-ttu-id="48b04-113">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="48b04-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="48b04-114">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="48b04-114">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 [<span data-ttu-id="48b04-115">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="48b04-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
