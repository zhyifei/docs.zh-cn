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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93a8c8650822c5d986e21a456d58b2dc0327f05b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479514"
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="573d1-102">ICorDebugNativeFrame::CanSetIP 方法</span><span class="sxs-lookup"><span data-stu-id="573d1-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="573d1-103">获取一个 HRESULT，指示它是否可以安全地在本机代码中设置为指定的偏移量位置的指令指针 (IP)。</span><span class="sxs-lookup"><span data-stu-id="573d1-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="573d1-104">语法</span><span class="sxs-lookup"><span data-stu-id="573d1-104">Syntax</span></span>  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="573d1-105">参数</span><span class="sxs-lookup"><span data-stu-id="573d1-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="573d1-106">[in]指令指针所需的设置。</span><span class="sxs-lookup"><span data-stu-id="573d1-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="573d1-107">备注</span><span class="sxs-lookup"><span data-stu-id="573d1-107">Remarks</span></span>  
 <span data-ttu-id="573d1-108">使用`CanSetIP`方法之前调用[icordebugnativeframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="573d1-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="573d1-109">如果`CanSetIP`返回任何 HRESULT，则为 S_OK，以外还可调用`ICorDebugNativeFrame::SetIP`，但不能保证，调试器将继续被调试代码的安全和正确执行。</span><span class="sxs-lookup"><span data-stu-id="573d1-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="573d1-110">要求</span><span class="sxs-lookup"><span data-stu-id="573d1-110">Requirements</span></span>  
 <span data-ttu-id="573d1-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="573d1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="573d1-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="573d1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="573d1-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="573d1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="573d1-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="573d1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="573d1-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="573d1-115">See also</span></span>

