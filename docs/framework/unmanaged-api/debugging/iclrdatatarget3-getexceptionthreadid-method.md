---
title: "ICLRDataTarget3::GetExceptionThreadID 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICLRDataTarget3.GetExceptionThreadID
api_location: mscordbi.dll
api_type: COM
ms.assetid: 307d6ac7-4a86-45f3-999d-6b47004a68f2
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f05d264d4bf55de930a07eda6bf369570c8b7fa8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="4ce56-102">ICLRDataTarget3::GetExceptionThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="4ce56-102">ICLRDataTarget3::GetExceptionThreadID Method</span></span>
<span data-ttu-id="4ce56-103">由公共语言运行时 (CLR) 数据访问服务调用，从而获取引发异常的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="4ce56-103">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ce56-104">语法</span><span class="sxs-lookup"><span data-stu-id="4ce56-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4ce56-105">参数</span><span class="sxs-lookup"><span data-stu-id="4ce56-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="4ce56-106">[out] 引发异常的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="4ce56-106">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ce56-107">返回值</span><span class="sxs-lookup"><span data-stu-id="4ce56-107">Return Value</span></span>  
 <span data-ttu-id="4ce56-108">如果成功，则返回值是 `S_OK`；如果失败，则返回失败 `HRESULT` 代码。</span><span class="sxs-lookup"><span data-stu-id="4ce56-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="4ce56-109">`HRESULT` 代码可以包括但不限于以下代码：</span><span class="sxs-lookup"><span data-stu-id="4ce56-109">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="4ce56-110">返回代码</span><span class="sxs-lookup"><span data-stu-id="4ce56-110">Return code</span></span>|<span data-ttu-id="4ce56-111">描述</span><span class="sxs-lookup"><span data-stu-id="4ce56-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="4ce56-112">方法成功。</span><span class="sxs-lookup"><span data-stu-id="4ce56-112">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="4ce56-113">找不到该异常的有效线程 ID。</span><span class="sxs-lookup"><span data-stu-id="4ce56-113">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ce56-114">备注</span><span class="sxs-lookup"><span data-stu-id="4ce56-114">Remarks</span></span>  
 <span data-ttu-id="4ce56-115">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="4ce56-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ce56-116">要求</span><span class="sxs-lookup"><span data-stu-id="4ce56-116">Requirements</span></span>  
 <span data-ttu-id="4ce56-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4ce56-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ce56-118">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="4ce56-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="4ce56-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ce56-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ce56-120">**.NET framework 版本：**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ce56-120">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ce56-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ce56-121">See Also</span></span>  
 [<span data-ttu-id="4ce56-122">ICLRDataTarget3 接口</span><span class="sxs-lookup"><span data-stu-id="4ce56-122">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [<span data-ttu-id="4ce56-123">GetExceptionContextRecord 方法</span><span class="sxs-lookup"><span data-stu-id="4ce56-123">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)  
 [<span data-ttu-id="4ce56-124">GetExceptionRecord 方法</span><span class="sxs-lookup"><span data-stu-id="4ce56-124">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
