---
title: "INotifySink2::OnSyncCallReturn 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: INotifySink2.OnSyncCallReturn
api_location: diasymreader.dll
api_type: COM
f1_keywords: INotifySink2::OnSyncCallReturn
helpviewer_keywords:
- OnSyncCallReturn method [.NET Framework debugging]
- INotifySink2::OnSyncCallReturn method [.NET Framework debugging]
ms.assetid: c1bda761-6292-4750-a14b-7d5db8f33456
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 311f54b5287b648e1c81e4db457e8f3c6945d959
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="inotifysink2onsynccallreturn-method"></a><span data-ttu-id="0efaa-102">INotifySink2::OnSyncCallReturn 方法</span><span class="sxs-lookup"><span data-stu-id="0efaa-102">INotifySink2::OnSyncCallReturn Method</span></span>
<span data-ttu-id="0efaa-103">当调用返回时调用。</span><span class="sxs-lookup"><span data-stu-id="0efaa-103">Gets invoked when a call returns.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0efaa-104">语法</span><span class="sxs-lookup"><span data-stu-id="0efaa-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0efaa-105">参数</span><span class="sxs-lookup"><span data-stu-id="0efaa-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="0efaa-106">[in]正在从返回的调用 ID。</span><span class="sxs-lookup"><span data-stu-id="0efaa-106">[in] ID of the call being returned from.</span></span> <span data-ttu-id="0efaa-107">请参阅[CALL_ID 结构](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="0efaa-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="0efaa-108">[in]调用缓冲区。</span><span class="sxs-lookup"><span data-stu-id="0efaa-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="0efaa-109">[in]调用缓冲区，以字节为单位的大小。</span><span class="sxs-lookup"><span data-stu-id="0efaa-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0efaa-110">返回值</span><span class="sxs-lookup"><span data-stu-id="0efaa-110">Return Value</span></span>  
 <span data-ttu-id="0efaa-111">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="0efaa-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0efaa-112">惠?</span><span class="sxs-lookup"><span data-stu-id="0efaa-112">Requirements</span></span>  
 <span data-ttu-id="0efaa-113">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="0efaa-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0efaa-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="0efaa-114">See Also</span></span>  
 [<span data-ttu-id="0efaa-115">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="0efaa-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="0efaa-116">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="0efaa-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="0efaa-117">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="0efaa-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
