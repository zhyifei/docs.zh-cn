---
title: "ICLRDataTarget::GetCurrentThreadID 方法"
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
- ICLRDataTarget.GetCurrentThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::GetCurrentThreadID method [.NET Framework debugging]
ms.assetid: dc9a0a6c-d592-4fb7-86ed-62684da3b0e1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2fd2c39b20b823e18232081d1655a6770bafccc5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="2f8e2-102">ICLRDataTarget::GetCurrentThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="2f8e2-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="2f8e2-103">获取当前线程的操作系统标识符。</span><span class="sxs-lookup"><span data-stu-id="2f8e2-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f8e2-104">语法</span><span class="sxs-lookup"><span data-stu-id="2f8e2-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f8e2-105">参数</span><span class="sxs-lookup"><span data-stu-id="2f8e2-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="2f8e2-106">[out]指向目标进程的当前线程的操作系统标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="2f8e2-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f8e2-107">备注</span><span class="sxs-lookup"><span data-stu-id="2f8e2-107">Remarks</span></span>  
 <span data-ttu-id="2f8e2-108">如果没有针对的目标进程中，当前线程`GetCurrentThreadID`方法可能会失败。</span><span class="sxs-lookup"><span data-stu-id="2f8e2-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f8e2-109">惠?</span><span class="sxs-lookup"><span data-stu-id="2f8e2-109">Requirements</span></span>  
 <span data-ttu-id="2f8e2-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2f8e2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f8e2-111">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="2f8e2-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="2f8e2-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f8e2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f8e2-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f8e2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f8e2-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f8e2-114">See Also</span></span>  
 [<span data-ttu-id="2f8e2-115">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="2f8e2-115">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
