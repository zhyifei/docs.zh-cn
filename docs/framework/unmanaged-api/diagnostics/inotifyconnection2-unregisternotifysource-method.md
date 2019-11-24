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
ms.openlocfilehash: cf399d0c7dec7528f02988ddfe6ca5c0b1f0c4c3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440983"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="685d8-102">INotifyConnection2::UnregisterNotifySource 方法</span><span class="sxs-lookup"><span data-stu-id="685d8-102">INotifyConnection2::UnregisterNotifySource Method</span></span>
<span data-ttu-id="685d8-103">Removes a specified notification source object from the connection.</span><span class="sxs-lookup"><span data-stu-id="685d8-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="685d8-104">语法</span><span class="sxs-lookup"><span data-stu-id="685d8-104">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="685d8-105">参数</span><span class="sxs-lookup"><span data-stu-id="685d8-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="685d8-106">[in] Notification object to be unregistered.</span><span class="sxs-lookup"><span data-stu-id="685d8-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="685d8-107">返回值</span><span class="sxs-lookup"><span data-stu-id="685d8-107">Return Value</span></span>  
 <span data-ttu-id="685d8-108">S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="685d8-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="685d8-109">要求</span><span class="sxs-lookup"><span data-stu-id="685d8-109">Requirements</span></span>  
 <span data-ttu-id="685d8-110">**Header:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="685d8-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="685d8-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="685d8-111">See also</span></span>

- [<span data-ttu-id="685d8-112">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="685d8-112">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="685d8-113">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="685d8-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="685d8-114">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="685d8-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="685d8-115">RegisterNotifySource 方法</span><span class="sxs-lookup"><span data-stu-id="685d8-115">RegisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)
