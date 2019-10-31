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
ms.openlocfilehash: b3758ac1a84092b8bf2678f9cc2c19c9d9961690
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137316"
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="86e5c-102">ICorDebugNativeFrame::CanSetIP 方法</span><span class="sxs-lookup"><span data-stu-id="86e5c-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="86e5c-103">获取 HRESULT，它指示是否可以安全地将指令指针（IP）设置为本机代码中的指定偏移位置。</span><span class="sxs-lookup"><span data-stu-id="86e5c-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86e5c-104">语法</span><span class="sxs-lookup"><span data-stu-id="86e5c-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86e5c-105">参数</span><span class="sxs-lookup"><span data-stu-id="86e5c-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="86e5c-106">中指令指针所需的设置。</span><span class="sxs-lookup"><span data-stu-id="86e5c-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86e5c-107">备注</span><span class="sxs-lookup"><span data-stu-id="86e5c-107">Remarks</span></span>  
 <span data-ttu-id="86e5c-108">在调用[ICorDebugNativeFrame：： SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)方法之前，请使用 `CanSetIP` 方法。</span><span class="sxs-lookup"><span data-stu-id="86e5c-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="86e5c-109">如果 `CanSetIP` 返回 S_OK 以外的任何 HRESULT，则仍可调用 `ICorDebugNativeFrame::SetIP`，但不保证调试器将继续安全且正确执行正在调试的代码。</span><span class="sxs-lookup"><span data-stu-id="86e5c-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86e5c-110">要求</span><span class="sxs-lookup"><span data-stu-id="86e5c-110">Requirements</span></span>  
 <span data-ttu-id="86e5c-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="86e5c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86e5c-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86e5c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86e5c-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86e5c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86e5c-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86e5c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86e5c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="86e5c-115">See also</span></span>
