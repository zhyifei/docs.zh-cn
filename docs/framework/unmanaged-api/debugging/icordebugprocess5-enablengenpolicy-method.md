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
ms.openlocfilehash: 9497bea9b7cc5eb98876c923858dbcbc6adf9d07
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792452"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="8a1b9-102">ICorDebugProcess5::EnableNGENPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="8a1b9-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="8a1b9-103">设置一个值，该值确定应用程序在托管调试器下运行时如何加载本机映像。</span><span class="sxs-lookup"><span data-stu-id="8a1b9-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a1b9-104">语法</span><span class="sxs-lookup"><span data-stu-id="8a1b9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a1b9-105">参数</span><span class="sxs-lookup"><span data-stu-id="8a1b9-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="8a1b9-106">中确定应用程序在托管调试器下运行时如何加载本机映像的[CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md)常量。</span><span class="sxs-lookup"><span data-stu-id="8a1b9-106">[in] A [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a1b9-107">备注</span><span class="sxs-lookup"><span data-stu-id="8a1b9-107">Remarks</span></span>  
 <span data-ttu-id="8a1b9-108">如果策略设置成功，则该方法将返回 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="8a1b9-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="8a1b9-109">如果 `ePolicy` 超出[CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md)定义的枚举值的范围，则该方法将返回 `E_INVALIDARG` 并且方法调用不起作用。</span><span class="sxs-lookup"><span data-stu-id="8a1b9-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="8a1b9-110">如果无法更新本机映像生成器（Ngen.exe）的策略，该方法将返回 `E_FAIL`。</span><span class="sxs-lookup"><span data-stu-id="8a1b9-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="8a1b9-111">在进程的生存期内，可以随时调用 `ICorDebugProcess5::EnableNGenPolicy` 方法。</span><span class="sxs-lookup"><span data-stu-id="8a1b9-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="8a1b9-112">此策略对设置策略后加载的任何模块有效。</span><span class="sxs-lookup"><span data-stu-id="8a1b9-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a1b9-113">需求</span><span class="sxs-lookup"><span data-stu-id="8a1b9-113">Requirements</span></span>  
 <span data-ttu-id="8a1b9-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8a1b9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a1b9-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a1b9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a1b9-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a1b9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a1b9-117">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a1b9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a1b9-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a1b9-118">See also</span></span>

- [<span data-ttu-id="8a1b9-119">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="8a1b9-119">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="8a1b9-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="8a1b9-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8a1b9-121">调试</span><span class="sxs-lookup"><span data-stu-id="8a1b9-121">Debugging</span></span>](index.md)
