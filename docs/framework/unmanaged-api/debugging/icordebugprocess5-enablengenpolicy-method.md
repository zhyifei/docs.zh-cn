---
title: ICorDebugProcess5::EnableNGENPolicy 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d8e848a7664e3573bd369addce2b2f5a8c91821
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481490"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="44d4d-102">ICorDebugProcess5::EnableNGENPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="44d4d-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="44d4d-103">设置一个值，确定如何将应用程序加载托管调试器下运行时的本机映像。</span><span class="sxs-lookup"><span data-stu-id="44d4d-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44d4d-104">语法</span><span class="sxs-lookup"><span data-stu-id="44d4d-104">Syntax</span></span>  
  
```  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44d4d-105">参数</span><span class="sxs-lookup"><span data-stu-id="44d4d-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="44d4d-106">[in]一个[CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)常量，它确定如何将应用程序加载托管调试器下运行时的本机映像。</span><span class="sxs-lookup"><span data-stu-id="44d4d-106">[in] A [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44d4d-107">备注</span><span class="sxs-lookup"><span data-stu-id="44d4d-107">Remarks</span></span>  
 <span data-ttu-id="44d4d-108">如果已成功设置了策略，该方法返回`S_OK`。</span><span class="sxs-lookup"><span data-stu-id="44d4d-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="44d4d-109">如果`ePolicy`超出定义的枚举值的范围[CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)，该方法将返回`E_INVALIDARG`和方法调用不起作用。</span><span class="sxs-lookup"><span data-stu-id="44d4d-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="44d4d-110">如果无法更新的本机映像生成器 (Ngen.exe) 策略，该方法返回`E_FAIL`。</span><span class="sxs-lookup"><span data-stu-id="44d4d-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="44d4d-111">`ICorDebugProcess5::EnableNGenPolicy`进程的生存期内随时可以调用方法。</span><span class="sxs-lookup"><span data-stu-id="44d4d-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="44d4d-112">该策略将生效后的策略设置加载的任何模块。</span><span class="sxs-lookup"><span data-stu-id="44d4d-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44d4d-113">要求</span><span class="sxs-lookup"><span data-stu-id="44d4d-113">Requirements</span></span>  
 <span data-ttu-id="44d4d-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="44d4d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44d4d-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44d4d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44d4d-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44d4d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44d4d-117">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44d4d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44d4d-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="44d4d-118">See also</span></span>
- [<span data-ttu-id="44d4d-119">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="44d4d-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="44d4d-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="44d4d-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="44d4d-121">调试</span><span class="sxs-lookup"><span data-stu-id="44d4d-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
