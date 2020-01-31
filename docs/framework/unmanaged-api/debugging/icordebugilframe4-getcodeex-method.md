---
title: ICorDebugILFrame4::GetCodeEx 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetLocalVariableEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type:
- apiref
ms.openlocfilehash: e77344a99189ec8e234129262d45698c794dc249
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788518"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="041b8-102">ICorDebugILFrame4::GetCodeEx 方法</span><span class="sxs-lookup"><span data-stu-id="041b8-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="041b8-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="041b8-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="041b8-104">获取指向此堆栈帧正在执行的代码的指针。</span><span class="sxs-lookup"><span data-stu-id="041b8-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="041b8-105">语法</span><span class="sxs-lookup"><span data-stu-id="041b8-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="041b8-106">参数</span><span class="sxs-lookup"><span data-stu-id="041b8-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="041b8-107">中一个[ILCodeKind](ilcodekind-enumeration.md)枚举成员，该成员指定由探查器的 ReJIT 请求定义的中间语言（IL）是否包含在帧中。</span><span class="sxs-lookup"><span data-stu-id="041b8-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="041b8-108">弄一个指向 "ICorDebugCode" 对象地址的指针，该对象表示此堆栈帧正在执行的代码。</span><span class="sxs-lookup"><span data-stu-id="041b8-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="041b8-109">备注</span><span class="sxs-lookup"><span data-stu-id="041b8-109">Remarks</span></span>  
 <span data-ttu-id="041b8-110">此方法类似于[ICorDebugFrame：： GetCode](icordebugframe-getcode-method.md)方法，不同之处在于它可以访问由探查器的 ReJIT 请求定义的代码。</span><span class="sxs-lookup"><span data-stu-id="041b8-110">This method is similar to the [ICorDebugFrame::GetCode](icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="041b8-111">使用 `ILCODE_ORIGINAL_IL` 的 `flags` 值调用此方法等效于调用[GetCode](icordebugframe-getcode-method.md);如果检测到此方法，则将无法访问其 IL。</span><span class="sxs-lookup"><span data-stu-id="041b8-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="041b8-112">`ILCODE_REJIT_IL` 允许调试器访问由探查器的 ReJIT 请求定义的 IL。</span><span class="sxs-lookup"><span data-stu-id="041b8-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="041b8-113">如果未检测到 IL，则 `ppCode` 为**null**，并且该方法返回 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="041b8-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="041b8-114">需求</span><span class="sxs-lookup"><span data-stu-id="041b8-114">Requirements</span></span>  
 <span data-ttu-id="041b8-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="041b8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="041b8-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="041b8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="041b8-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="041b8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="041b8-118">**.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="041b8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="041b8-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="041b8-119">See also</span></span>

- [<span data-ttu-id="041b8-120">ICorDebugILFrame4 接口</span><span class="sxs-lookup"><span data-stu-id="041b8-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="041b8-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="041b8-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="041b8-122">ReJIT：操作方法指南</span><span class="sxs-lookup"><span data-stu-id="041b8-122">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
