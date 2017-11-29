---
title: "ICorDebugRegisterSet::SetThreadContext 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet.SetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet::SetThreadContext
helpviewer_keywords:
- ICorDebugRegisterSet::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 73afa930-32cb-4c40-81f8-83e8e6fbe213
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9a97706e5cf407f16b6d06efce11576fbb131d1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregistersetsetthreadcontext-method"></a><span data-ttu-id="16be3-102">ICorDebugRegisterSet::SetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="16be3-102">ICorDebugRegisterSet::SetThreadContext Method</span></span>
<span data-ttu-id="16be3-103">`SetThreadContext`在.NET Framework 2.0 版中未实现。</span><span class="sxs-lookup"><span data-stu-id="16be3-103">`SetThreadContext` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="16be3-104">请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="16be3-104">Do not call this method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16be3-105">使用更高级别的操作[icordebugnativeframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)设置线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="16be3-105">Use the higher-level operation [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) to set the context of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16be3-106">语法</span><span class="sxs-lookup"><span data-stu-id="16be3-106">Syntax</span></span>  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="16be3-107">要求</span><span class="sxs-lookup"><span data-stu-id="16be3-107">Requirements</span></span>  
 <span data-ttu-id="16be3-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="16be3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16be3-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16be3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16be3-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16be3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16be3-111">**.NET framework 版本：** 1.1、 1.0</span><span class="sxs-lookup"><span data-stu-id="16be3-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16be3-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16be3-112">See Also</span></span>  
 [<span data-ttu-id="16be3-113">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="16be3-113">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="16be3-114">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="16be3-114">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
