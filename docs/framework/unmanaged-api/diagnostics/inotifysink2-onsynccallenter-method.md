---
title: INotifySink2::OnSyncCallEnter 方法
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallEnter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallEnter
helpviewer_keywords:
- INotifySink2::OnSyncCallEnter method [.NET Framework debugging]
- OnSyncCallEnter method [.NET Framework debugging]
ms.assetid: e33265be-c25d-4145-ad02-c3e89d6f26c1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6c2c4f15b3fb1bc5b408382589a1c8213ffd246e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425947"
---
# <a name="inotifysink2onsynccallenter-method"></a><span data-ttu-id="70f5e-102">INotifySink2::OnSyncCallEnter 方法</span><span class="sxs-lookup"><span data-stu-id="70f5e-102">INotifySink2::OnSyncCallEnter Method</span></span>
<span data-ttu-id="70f5e-103">输入调用时调用。</span><span class="sxs-lookup"><span data-stu-id="70f5e-103">Gets invoked when entering a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70f5e-104">语法</span><span class="sxs-lookup"><span data-stu-id="70f5e-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallEnter  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="70f5e-105">参数</span><span class="sxs-lookup"><span data-stu-id="70f5e-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="70f5e-106">[in]输入的调用 ID。</span><span class="sxs-lookup"><span data-stu-id="70f5e-106">[in] ID of the call being entered.</span></span> <span data-ttu-id="70f5e-107">请参阅[CALL_ID 结构](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="70f5e-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="70f5e-108">[in]调用缓冲区。</span><span class="sxs-lookup"><span data-stu-id="70f5e-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="70f5e-109">[in]调用缓冲区，以字节为单位的大小。</span><span class="sxs-lookup"><span data-stu-id="70f5e-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70f5e-110">返回值</span><span class="sxs-lookup"><span data-stu-id="70f5e-110">Return Value</span></span>  
 <span data-ttu-id="70f5e-111">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="70f5e-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70f5e-112">要求</span><span class="sxs-lookup"><span data-stu-id="70f5e-112">Requirements</span></span>  
 <span data-ttu-id="70f5e-113">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="70f5e-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70f5e-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="70f5e-114">See Also</span></span>  
 [<span data-ttu-id="70f5e-115">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="70f5e-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="70f5e-116">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="70f5e-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="70f5e-117">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="70f5e-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
