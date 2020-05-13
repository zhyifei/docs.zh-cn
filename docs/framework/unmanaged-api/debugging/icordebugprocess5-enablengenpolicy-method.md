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
ms.openlocfilehash: fa3cbfee0359b8477f9efe88fe72837b86611bf7
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212797"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="f9a07-102">ICorDebugProcess5::EnableNGENPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="f9a07-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="f9a07-103">设置一个值，该值确定应用程序在托管调试器下运行时如何加载本机映像。</span><span class="sxs-lookup"><span data-stu-id="f9a07-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9a07-104">语法</span><span class="sxs-lookup"><span data-stu-id="f9a07-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9a07-105">参数</span><span class="sxs-lookup"><span data-stu-id="f9a07-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="f9a07-106">中确定应用程序在托管调试器下运行时如何加载本机映像的[CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md)常量。</span><span class="sxs-lookup"><span data-stu-id="f9a07-106">[in] A [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9a07-107">备注</span><span class="sxs-lookup"><span data-stu-id="f9a07-107">Remarks</span></span>  
 <span data-ttu-id="f9a07-108">如果策略设置成功，则该方法将返回 `S_OK` 。</span><span class="sxs-lookup"><span data-stu-id="f9a07-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="f9a07-109">如果 `ePolicy` 超出了[CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md)定义的枚举值的范围，则方法将返回 `E_INVALIDARG` ，并且方法调用不起作用。</span><span class="sxs-lookup"><span data-stu-id="f9a07-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="f9a07-110">如果无法更新本机映像生成器（Ngen.exe）的策略，该方法将返回 `E_FAIL` 。</span><span class="sxs-lookup"><span data-stu-id="f9a07-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="f9a07-111">在 `ICorDebugProcess5::EnableNGenPolicy` 进程的生存期内随时可以调用方法。</span><span class="sxs-lookup"><span data-stu-id="f9a07-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="f9a07-112">此策略对设置策略后加载的任何模块有效。</span><span class="sxs-lookup"><span data-stu-id="f9a07-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9a07-113">要求</span><span class="sxs-lookup"><span data-stu-id="f9a07-113">Requirements</span></span>  
 <span data-ttu-id="f9a07-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f9a07-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9a07-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f9a07-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9a07-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9a07-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9a07-117">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9a07-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9a07-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f9a07-118">See also</span></span>

- [<span data-ttu-id="f9a07-119">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="f9a07-119">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="f9a07-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="f9a07-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f9a07-121">调试</span><span class="sxs-lookup"><span data-stu-id="f9a07-121">Debugging</span></span>](index.md)
