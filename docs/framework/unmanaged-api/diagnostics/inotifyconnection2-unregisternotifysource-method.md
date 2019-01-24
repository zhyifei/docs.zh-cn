---
title: INotifyConnection2::UnregisterNotifySource 方法
ms.date: 03/30/2017
api_name:
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e5380ed63a362b73b0684ef07b638117751ca80
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712007"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="7a3de-102">INotifyConnection2::UnregisterNotifySource 方法</span><span class="sxs-lookup"><span data-stu-id="7a3de-102">INotifyConnection2::UnregisterNotifySource Method</span></span>
<span data-ttu-id="7a3de-103">从连接中移除指定的通知源对象。</span><span class="sxs-lookup"><span data-stu-id="7a3de-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a3de-104">语法</span><span class="sxs-lookup"><span data-stu-id="7a3de-104">Syntax</span></span>  
  
```  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7a3de-105">参数</span><span class="sxs-lookup"><span data-stu-id="7a3de-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="7a3de-106">[in]要注销的通知对象。</span><span class="sxs-lookup"><span data-stu-id="7a3de-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a3de-107">返回值</span><span class="sxs-lookup"><span data-stu-id="7a3de-107">Return Value</span></span>  
 <span data-ttu-id="7a3de-108">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="7a3de-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a3de-109">要求</span><span class="sxs-lookup"><span data-stu-id="7a3de-109">Requirements</span></span>  
 <span data-ttu-id="7a3de-110">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="7a3de-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a3de-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a3de-111">See also</span></span>
- [<span data-ttu-id="7a3de-112">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="7a3de-112">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="7a3de-113">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="7a3de-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="7a3de-114">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="7a3de-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="7a3de-115">RegisterNotifySource 方法</span><span class="sxs-lookup"><span data-stu-id="7a3de-115">RegisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)
