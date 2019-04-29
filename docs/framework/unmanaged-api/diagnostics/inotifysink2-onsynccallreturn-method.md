---
title: INotifySink2::OnSyncCallReturn 方法
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallReturn
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallReturn
helpviewer_keywords:
- OnSyncCallReturn method [.NET Framework debugging]
- INotifySink2::OnSyncCallReturn method [.NET Framework debugging]
ms.assetid: c1bda761-6292-4750-a14b-7d5db8f33456
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0adc6ec1db3f12d1850bb6ff9a01d5b6cc5f90c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940343"
---
# <a name="inotifysink2onsynccallreturn-method"></a><span data-ttu-id="72825-102">INotifySink2::OnSyncCallReturn 方法</span><span class="sxs-lookup"><span data-stu-id="72825-102">INotifySink2::OnSyncCallReturn Method</span></span>
<span data-ttu-id="72825-103">当调用返回时调用。</span><span class="sxs-lookup"><span data-stu-id="72825-103">Gets invoked when a call returns.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72825-104">语法</span><span class="sxs-lookup"><span data-stu-id="72825-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72825-105">参数</span><span class="sxs-lookup"><span data-stu-id="72825-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="72825-106">[in]从返回的调用 ID。</span><span class="sxs-lookup"><span data-stu-id="72825-106">[in] ID of the call being returned from.</span></span> <span data-ttu-id="72825-107">请参阅[CALL_ID 结构](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="72825-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="72825-108">[in]调用缓冲区。</span><span class="sxs-lookup"><span data-stu-id="72825-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="72825-109">[in]调用缓冲区，以字节为单位的大小。</span><span class="sxs-lookup"><span data-stu-id="72825-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72825-110">返回值</span><span class="sxs-lookup"><span data-stu-id="72825-110">Return Value</span></span>  
 <span data-ttu-id="72825-111">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="72825-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72825-112">要求</span><span class="sxs-lookup"><span data-stu-id="72825-112">Requirements</span></span>  
 <span data-ttu-id="72825-113">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="72825-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72825-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="72825-114">See also</span></span>

- [<span data-ttu-id="72825-115">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="72825-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="72825-116">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="72825-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="72825-117">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="72825-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
