---
title: INotifySource2::SetNotifyFilter 方法
ms.date: 03/30/2017
api_name:
- INotifySource2.SetNotifyFilter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySource2::SetNotifyFilter
helpviewer_keywords:
- INotifySource2::SetNotifyFilter method [.NET Framework debugging]
- SetNotifyFilter method [.NET Framework debugging]
ms.assetid: 6351fc92-b126-4af6-9bf3-0a8ce92845fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 37e4abeebce155a4c332e864b4dfb6cf5a1141ec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151744"
---
# <a name="inotifysource2setnotifyfilter-method"></a><span data-ttu-id="99d86-102">INotifySource2::SetNotifyFilter 方法</span><span class="sxs-lookup"><span data-stu-id="99d86-102">INotifySource2::SetNotifyFilter Method</span></span>
<span data-ttu-id="99d86-103">将分配与此源使用通知筛选器。</span><span class="sxs-lookup"><span data-stu-id="99d86-103">Assigns a notification filter for use with this source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99d86-104">语法</span><span class="sxs-lookup"><span data-stu-id="99d86-104">Syntax</span></span>  
  
```  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99d86-105">参数</span><span class="sxs-lookup"><span data-stu-id="99d86-105">Parameters</span></span>  
 `in_NotifyFilter`  
 <span data-ttu-id="99d86-106">[in]按位组合[NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md)标识回叫，以便调试器 API 的枚举值。</span><span class="sxs-lookup"><span data-stu-id="99d86-106">[in] A bitwise combination of the [NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md) enumeration values that identify callbacks for the debugger API.</span></span>  
  
 `in_pUserThreadFilter`  
 <span data-ttu-id="99d86-107">[in]一个指向[USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md)标识调试器 API 的线程的结构。</span><span class="sxs-lookup"><span data-stu-id="99d86-107">[in] A pointer to a [USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md) structure that identifies threads for the debugger API.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99d86-108">返回值</span><span class="sxs-lookup"><span data-stu-id="99d86-108">Return Value</span></span>  
 <span data-ttu-id="99d86-109">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="99d86-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99d86-110">要求</span><span class="sxs-lookup"><span data-stu-id="99d86-110">Requirements</span></span>  
 <span data-ttu-id="99d86-111">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="99d86-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99d86-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="99d86-112">See also</span></span>

- [<span data-ttu-id="99d86-113">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="99d86-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="99d86-114">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="99d86-114">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="99d86-115">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="99d86-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
