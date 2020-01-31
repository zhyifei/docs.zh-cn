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
ms.openlocfilehash: 35515d7c2b82ec2c42461406363964e0b60eb243
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785472"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="7044e-102">ICLRDataTarget::GetCurrentThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="7044e-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="7044e-103">获取当前线程的操作系统标识符。</span><span class="sxs-lookup"><span data-stu-id="7044e-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7044e-104">语法</span><span class="sxs-lookup"><span data-stu-id="7044e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7044e-105">参数</span><span class="sxs-lookup"><span data-stu-id="7044e-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="7044e-106">弄指向目标进程的当前线程的操作系统标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="7044e-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7044e-107">备注</span><span class="sxs-lookup"><span data-stu-id="7044e-107">Remarks</span></span>  
 <span data-ttu-id="7044e-108">如果目标进程没有当前线程，`GetCurrentThreadID` 方法可能会失败。</span><span class="sxs-lookup"><span data-stu-id="7044e-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7044e-109">需求</span><span class="sxs-lookup"><span data-stu-id="7044e-109">Requirements</span></span>  
 <span data-ttu-id="7044e-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7044e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7044e-111">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="7044e-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="7044e-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7044e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7044e-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7044e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7044e-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7044e-114">See also</span></span>

- [<span data-ttu-id="7044e-115">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="7044e-115">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
