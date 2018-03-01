---
title: "INotifyConnection2::RegisterNotifySource 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- INotifyConnection2.RegisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::RegisterNotifySource
helpviewer_keywords:
- INotifyConnection2::RegisterNotifySource method [.NET Framework debugging]
- RegisterNotifySource method [.NET Framework debugging]
ms.assetid: 2632da80-6e4b-4429-8dee-b382745a5f81
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a141872dc5699e5b317b21f03672fe0d76096392
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="inotifyconnection2registernotifysource-method"></a><span data-ttu-id="d594b-102">INotifyConnection2::RegisterNotifySource 方法</span><span class="sxs-lookup"><span data-stu-id="d594b-102">INotifyConnection2::RegisterNotifySource Method</span></span>
<span data-ttu-id="d594b-103">安装指定的通知源。</span><span class="sxs-lookup"><span data-stu-id="d594b-103">Installs a specified notification source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d594b-104">语法</span><span class="sxs-lookup"><span data-stu-id="d594b-104">Syntax</span></span>  
  
```  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d594b-105">参数</span><span class="sxs-lookup"><span data-stu-id="d594b-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="d594b-106">[in]指定要用作通知源的对象。</span><span class="sxs-lookup"><span data-stu-id="d594b-106">[in] Specifies the object to be used as the notification source.</span></span>  
  
 `out_ppNotifySink`  
 <span data-ttu-id="d594b-107">[out]接收要用作通知接收器的对象。</span><span class="sxs-lookup"><span data-stu-id="d594b-107">[out] Receives the object to be used as the notification sink.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d594b-108">返回值</span><span class="sxs-lookup"><span data-stu-id="d594b-108">Return Value</span></span>  
 <span data-ttu-id="d594b-109">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="d594b-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d594b-110">惠?</span><span class="sxs-lookup"><span data-stu-id="d594b-110">Requirements</span></span>  
 <span data-ttu-id="d594b-111">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="d594b-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d594b-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="d594b-112">See Also</span></span>  
 [<span data-ttu-id="d594b-113">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="d594b-113">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 [<span data-ttu-id="d594b-114">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="d594b-114">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="d594b-115">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="d594b-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="d594b-116">UnregisterNotifySource 方法</span><span class="sxs-lookup"><span data-stu-id="d594b-116">UnregisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-unregisternotifysource-method.md)
