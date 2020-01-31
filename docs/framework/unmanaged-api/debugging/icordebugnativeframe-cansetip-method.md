---
title: ICorDebugNativeFrame::CanSetIP 方法
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type:
- apiref
ms.openlocfilehash: d266ec7f82d7d4c7c66f137aafc1c8865d6f8889
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792808"
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="db06d-102">ICorDebugNativeFrame::CanSetIP 方法</span><span class="sxs-lookup"><span data-stu-id="db06d-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="db06d-103">获取 HRESULT，它指示是否可以安全地将指令指针（IP）设置为本机代码中的指定偏移位置。</span><span class="sxs-lookup"><span data-stu-id="db06d-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db06d-104">语法</span><span class="sxs-lookup"><span data-stu-id="db06d-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db06d-105">参数</span><span class="sxs-lookup"><span data-stu-id="db06d-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="db06d-106">中指令指针所需的设置。</span><span class="sxs-lookup"><span data-stu-id="db06d-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db06d-107">备注</span><span class="sxs-lookup"><span data-stu-id="db06d-107">Remarks</span></span>  
 <span data-ttu-id="db06d-108">在调用[ICorDebugNativeFrame：： SetIP](icordebugnativeframe-setip-method.md)方法之前，请使用 `CanSetIP` 方法。</span><span class="sxs-lookup"><span data-stu-id="db06d-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="db06d-109">如果 `CanSetIP` 返回除 S_OK 以外的任何 HRESULT，则仍可调用 `ICorDebugNativeFrame::SetIP`，但不保证调试器将继续安全且正确地执行正在调试的代码。</span><span class="sxs-lookup"><span data-stu-id="db06d-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db06d-110">需求</span><span class="sxs-lookup"><span data-stu-id="db06d-110">Requirements</span></span>  
 <span data-ttu-id="db06d-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="db06d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db06d-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db06d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db06d-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db06d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db06d-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db06d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db06d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db06d-115">See also</span></span>
