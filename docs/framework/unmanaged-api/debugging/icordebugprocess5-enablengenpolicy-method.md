---
title: "ICorDebugProcess5::EnableNGENPolicy 方法"
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
- ICorDebugProcess5::EnableNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dca0df7b0be643d53bb5b9a03bd3abbb186d69dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="71ed7-102">ICorDebugProcess5::EnableNGENPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="71ed7-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="71ed7-103">设置一个值，确定如何应用程序加载托管调试器下运行时的本机映像。</span><span class="sxs-lookup"><span data-stu-id="71ed7-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71ed7-104">语法</span><span class="sxs-lookup"><span data-stu-id="71ed7-104">Syntax</span></span>  
  
```  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71ed7-105">参数</span><span class="sxs-lookup"><span data-stu-id="71ed7-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="71ed7-106">[in]A [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)常数，确定如何应用程序加载托管调试器下运行时的本机映像。</span><span class="sxs-lookup"><span data-stu-id="71ed7-106">[in] A [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71ed7-107">备注</span><span class="sxs-lookup"><span data-stu-id="71ed7-107">Remarks</span></span>  
 <span data-ttu-id="71ed7-108">如果已成功设置了策略，该方法返回`S_OK`。</span><span class="sxs-lookup"><span data-stu-id="71ed7-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="71ed7-109">如果`ePolicy`超出定义的枚举值的范围[CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)，该方法返回`E_INVALIDARG`和方法调用不起作用。</span><span class="sxs-lookup"><span data-stu-id="71ed7-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="71ed7-110">如果无法更新的本机映像生成器 (Ngen.exe) 策略，该方法返回`E_FAIL`。</span><span class="sxs-lookup"><span data-stu-id="71ed7-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="71ed7-111">`ICorDebugProcess5::EnableNGenPolicy`可以在进程的生存期内随时调用方法。</span><span class="sxs-lookup"><span data-stu-id="71ed7-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="71ed7-112">策略实际上是任何策略设置后加载的模块。</span><span class="sxs-lookup"><span data-stu-id="71ed7-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71ed7-113">惠?</span><span class="sxs-lookup"><span data-stu-id="71ed7-113">Requirements</span></span>  
 <span data-ttu-id="71ed7-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="71ed7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71ed7-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71ed7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71ed7-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71ed7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71ed7-117">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71ed7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71ed7-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="71ed7-118">See Also</span></span>  
 [<span data-ttu-id="71ed7-119">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="71ed7-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="71ed7-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="71ed7-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="71ed7-121">调试</span><span class="sxs-lookup"><span data-stu-id="71ed7-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
