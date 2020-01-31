---
title: ICorDebugRegisterSet::SetThreadContext 方法
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetThreadContext
helpviewer_keywords:
- ICorDebugRegisterSet::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 73afa930-32cb-4c40-81f8-83e8e6fbe213
topic_type:
- apiref
ms.openlocfilehash: dc2a41524d3fafe1cb45c9494d80aabe7dae0ed8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792043"
---
# <a name="icordebugregistersetsetthreadcontext-method"></a><span data-ttu-id="1c7ae-102">ICorDebugRegisterSet::SetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="1c7ae-102">ICorDebugRegisterSet::SetThreadContext Method</span></span>
<span data-ttu-id="1c7ae-103">.NET Framework 版本2.0 中未实现 `SetThreadContext`。</span><span class="sxs-lookup"><span data-stu-id="1c7ae-103">`SetThreadContext` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="1c7ae-104">请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="1c7ae-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1c7ae-105">使用较高级别的操作[ICorDebugNativeFrame：： SetIP](icordebugnativeframe-setip-method.md)设置线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="1c7ae-105">Use the higher-level operation [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md) to set the context of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c7ae-106">语法</span><span class="sxs-lookup"><span data-stu-id="1c7ae-106">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="1c7ae-107">需求</span><span class="sxs-lookup"><span data-stu-id="1c7ae-107">Requirements</span></span>  
 <span data-ttu-id="1c7ae-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1c7ae-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c7ae-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c7ae-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c7ae-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c7ae-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c7ae-111">**.NET Framework 版本：** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="1c7ae-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c7ae-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c7ae-112">See also</span></span>

- [<span data-ttu-id="1c7ae-113">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="1c7ae-113">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="1c7ae-114">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="1c7ae-114">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
