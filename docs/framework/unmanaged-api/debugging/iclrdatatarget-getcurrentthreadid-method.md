---
title: ICLRDataTarget::GetCurrentThreadID 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb1e0aec9ce746c3082ad9cc57b572cbca0fd7e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552252"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="e9cd9-102">ICLRDataTarget::GetCurrentThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="e9cd9-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="e9cd9-103">获取当前线程的操作系统识别符。</span><span class="sxs-lookup"><span data-stu-id="e9cd9-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9cd9-104">语法</span><span class="sxs-lookup"><span data-stu-id="e9cd9-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9cd9-105">参数</span><span class="sxs-lookup"><span data-stu-id="e9cd9-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="e9cd9-106">[out]指向目标进程的当前线程的操作系统识别符的指针。</span><span class="sxs-lookup"><span data-stu-id="e9cd9-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9cd9-107">备注</span><span class="sxs-lookup"><span data-stu-id="e9cd9-107">Remarks</span></span>  
 <span data-ttu-id="e9cd9-108">如果目标进程中，没有当前线程`GetCurrentThreadID`方法可能会失败。</span><span class="sxs-lookup"><span data-stu-id="e9cd9-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9cd9-109">要求</span><span class="sxs-lookup"><span data-stu-id="e9cd9-109">Requirements</span></span>  
 <span data-ttu-id="e9cd9-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e9cd9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9cd9-111">**标头：** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="e9cd9-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e9cd9-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9cd9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9cd9-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9cd9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9cd9-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9cd9-114">See also</span></span>
- [<span data-ttu-id="e9cd9-115">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="e9cd9-115">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
