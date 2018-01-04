---
title: "INotifySink2::OnSyncCallExit 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: INotifySink2.OnSyncCallExit
api_location: diasymreader.dll
api_type: COM
f1_keywords: INotifySink2::OnSyncCallExit
helpviewer_keywords:
- INotifySink2::OnSyncCallExit method [.NET Framework debugging]
- OnSyncCallExit method [.NET Framework debugging]
ms.assetid: d9d7600e-a8f5-443a-96de-67d26e130f2d
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 43139e8be9a1f5dfb6513f2ee7768237ae882c69
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="inotifysink2onsynccallexit-method"></a><span data-ttu-id="bb2c1-102">INotifySink2::OnSyncCallExit 方法</span><span class="sxs-lookup"><span data-stu-id="bb2c1-102">INotifySink2::OnSyncCallExit Method</span></span>
<span data-ttu-id="bb2c1-103">退出调用时调用。</span><span class="sxs-lookup"><span data-stu-id="bb2c1-103">Gets invoked when exiting a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb2c1-104">语法</span><span class="sxs-lookup"><span data-stu-id="bb2c1-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallExit  
(  
    [in]  CALL_ID   in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*    out_pBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb2c1-105">参数</span><span class="sxs-lookup"><span data-stu-id="bb2c1-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="bb2c1-106">[in]正在退出的调用 ID。</span><span class="sxs-lookup"><span data-stu-id="bb2c1-106">[in] ID of the call being exited.</span></span> <span data-ttu-id="bb2c1-107">请参阅[CALL_ID 结构](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="bb2c1-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="bb2c1-108">[out]调用缓冲区。</span><span class="sxs-lookup"><span data-stu-id="bb2c1-108">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="bb2c1-109">[out]调用缓冲区，以字节为单位的大小。</span><span class="sxs-lookup"><span data-stu-id="bb2c1-109">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb2c1-110">返回值</span><span class="sxs-lookup"><span data-stu-id="bb2c1-110">Return Value</span></span>  
 <span data-ttu-id="bb2c1-111">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="bb2c1-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb2c1-112">惠?</span><span class="sxs-lookup"><span data-stu-id="bb2c1-112">Requirements</span></span>  
 <span data-ttu-id="bb2c1-113">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="bb2c1-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb2c1-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb2c1-114">See Also</span></span>  
 [<span data-ttu-id="bb2c1-115">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="bb2c1-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="bb2c1-116">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="bb2c1-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="bb2c1-117">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="bb2c1-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
