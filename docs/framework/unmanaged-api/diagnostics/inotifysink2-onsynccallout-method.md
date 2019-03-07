---
title: INotifySink2::OnSyncCallOut 方法
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallOut
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallOut
helpviewer_keywords:
- INotifySink2::OnSyncCallOut method [.NET Framework debugging]
- OnSyncCallOut method [.NET Framework debugging]
ms.assetid: 97f15656-8677-4079-8553-a1d8603355d6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 49cfa25aaf3c49c1258eb01a29b83e7eb358838a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474938"
---
# <a name="inotifysink2onsynccallout-method"></a><span data-ttu-id="2eea4-102">INotifySink2::OnSyncCallOut 方法</span><span class="sxs-lookup"><span data-stu-id="2eea4-102">INotifySink2::OnSyncCallOut Method</span></span>
<span data-ttu-id="2eea4-103">调用超时时被调用。</span><span class="sxs-lookup"><span data-stu-id="2eea4-103">Gets invoked when a call is out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2eea4-104">语法</span><span class="sxs-lookup"><span data-stu-id="2eea4-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallOut  
(  
    [in]  CALL_ID  in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*   out_pBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2eea4-105">参数</span><span class="sxs-lookup"><span data-stu-id="2eea4-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="2eea4-106">[in]为向外调用的 ID。请参阅[CALL_ID 结构](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="2eea4-106">[in] ID of the call that is out. See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="2eea4-107">[out]调用缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2eea4-107">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="2eea4-108">[out]调用缓冲区，以字节为单位的大小。</span><span class="sxs-lookup"><span data-stu-id="2eea4-108">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2eea4-109">返回值</span><span class="sxs-lookup"><span data-stu-id="2eea4-109">Return Value</span></span>  
 <span data-ttu-id="2eea4-110">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="2eea4-110">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2eea4-111">要求</span><span class="sxs-lookup"><span data-stu-id="2eea4-111">Requirements</span></span>  
 <span data-ttu-id="2eea4-112">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="2eea4-112">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eea4-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="2eea4-113">See also</span></span>
- [<span data-ttu-id="2eea4-114">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="2eea4-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="2eea4-115">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="2eea4-115">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="2eea4-116">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="2eea4-116">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
