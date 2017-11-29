---
title: "INotifyConnection2::UnregisterNotifySource 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: INotifyConnection2.UnregisterNotifySource
api_location: diasymreader.dll
api_type: COM
f1_keywords: INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 063a146d31031f0cb14e00278819e8cd874f98c4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="bbaa4-102">INotifyConnection2::UnregisterNotifySource 方法</span><span class="sxs-lookup"><span data-stu-id="bbaa4-102">INotifyConnection2::UnregisterNotifySource Method</span></span>
<span data-ttu-id="bbaa4-103">从连接中移除指定的通知源对象。</span><span class="sxs-lookup"><span data-stu-id="bbaa4-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbaa4-104">语法</span><span class="sxs-lookup"><span data-stu-id="bbaa4-104">Syntax</span></span>  
  
```  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bbaa4-105">参数</span><span class="sxs-lookup"><span data-stu-id="bbaa4-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="bbaa4-106">[in]要取消注册的通知对象。</span><span class="sxs-lookup"><span data-stu-id="bbaa4-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bbaa4-107">返回值</span><span class="sxs-lookup"><span data-stu-id="bbaa4-107">Return Value</span></span>  
 <span data-ttu-id="bbaa4-108">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="bbaa4-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbaa4-109">要求</span><span class="sxs-lookup"><span data-stu-id="bbaa4-109">Requirements</span></span>  
 <span data-ttu-id="bbaa4-110">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="bbaa4-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbaa4-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bbaa4-111">See Also</span></span>  
 [<span data-ttu-id="bbaa4-112">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="bbaa4-112">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 [<span data-ttu-id="bbaa4-113">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="bbaa4-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="bbaa4-114">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="bbaa4-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="bbaa4-115">RegisterNotifySource 方法</span><span class="sxs-lookup"><span data-stu-id="bbaa4-115">RegisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)
