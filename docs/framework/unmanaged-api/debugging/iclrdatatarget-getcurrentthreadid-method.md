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
ms.openlocfilehash: 03ce49466587d3e214c32e2a5cca89cdd7a72038
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405222"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="efd41-102">ICLRDataTarget::GetCurrentThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="efd41-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="efd41-103">获取当前线程的操作系统标识符。</span><span class="sxs-lookup"><span data-stu-id="efd41-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efd41-104">语法</span><span class="sxs-lookup"><span data-stu-id="efd41-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="efd41-105">参数</span><span class="sxs-lookup"><span data-stu-id="efd41-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="efd41-106">[out]指向目标进程的当前线程的操作系统标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="efd41-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efd41-107">备注</span><span class="sxs-lookup"><span data-stu-id="efd41-107">Remarks</span></span>  
 <span data-ttu-id="efd41-108">如果没有针对的目标进程中，当前线程`GetCurrentThreadID`方法可能会失败。</span><span class="sxs-lookup"><span data-stu-id="efd41-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efd41-109">要求</span><span class="sxs-lookup"><span data-stu-id="efd41-109">Requirements</span></span>  
 <span data-ttu-id="efd41-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="efd41-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efd41-111">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="efd41-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="efd41-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efd41-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efd41-113">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efd41-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efd41-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="efd41-114">See Also</span></span>  
 [<span data-ttu-id="efd41-115">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="efd41-115">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
