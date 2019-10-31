---
title: ICorDebugILFrame4::GetLocalVariableEx 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetCodeEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0c8676f8-ca0d-4998-b64d-fefac7e38912
topic_type:
- apiref
ms.openlocfilehash: fb2744493d89a57ffc78e194f8c1e4a6dcf9f7c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090921"
---
# <a name="icordebugilframe4getlocalvariableex-method"></a><span data-ttu-id="c0dd3-102">ICorDebugILFrame4::GetLocalVariableEx 方法</span><span class="sxs-lookup"><span data-stu-id="c0dd3-102">ICorDebugILFrame4::GetLocalVariableEx Method</span></span>
<span data-ttu-id="c0dd3-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="c0dd3-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="c0dd3-104">获取此中间语言 (IL) 堆栈帧中指定的局部变量的值，并且（可选）访问在探查器 ReJIT 检测中添加的变量。</span><span class="sxs-lookup"><span data-stu-id="c0dd3-104">Gets the value of the specified local variable in this intermediate language (IL) stack frame, and optionally accesses a variable added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0dd3-105">语法</span><span class="sxs-lookup"><span data-stu-id="c0dd3-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,   
   [in] DWORD dwIndex,   
   [out] ICorDebugValue **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0dd3-106">参数</span><span class="sxs-lookup"><span data-stu-id="c0dd3-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="c0dd3-107">中一个[ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md)枚举成员，用于指定在探查器 ReJIT 检测中添加的变量是否包含在帧中。</span><span class="sxs-lookup"><span data-stu-id="c0dd3-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether a variable added in profiler ReJIT instrumentation is included in the frame.</span></span>  
  
 `dwIndex`  
 <span data-ttu-id="c0dd3-108">[in] IL 堆栈帧中局部变量的索引。</span><span class="sxs-lookup"><span data-stu-id="c0dd3-108">[in] The index of the local variable in the IL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="c0dd3-109">弄指向表示检索到的值的 "ICorDebugValue" 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="c0dd3-109">[out] A pointer to the address of an "ICorDebugValue" object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0dd3-110">备注</span><span class="sxs-lookup"><span data-stu-id="c0dd3-110">Remarks</span></span>  
 <span data-ttu-id="c0dd3-111">此方法类似于[GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)方法，不同之处在于它还可以访问在探查器 ReJIT 检测中添加的变量。</span><span class="sxs-lookup"><span data-stu-id="c0dd3-111">This method is similar to the [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) method, except that it optionally accesses a variable added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="c0dd3-112">使用 `ILCODE_ORIGINAL_IL` 的 `flags` 值调用此方法等效于调用[GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md);如果用附加的局部变量检测方法，则不能访问这些变量。</span><span class="sxs-lookup"><span data-stu-id="c0dd3-112">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md); if the method is instrumented with additional local variables, those variables cannot be accessed.</span></span> <span data-ttu-id="c0dd3-113">`ILCODE_REJIT_IL` 使调试器能够访问在探查器 ReJIT 检测中添加的局部变量。</span><span class="sxs-lookup"><span data-stu-id="c0dd3-113">`ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="c0dd3-114">如果未检测到 IL，则此方法将返回 `E_INVALIDARG`。</span><span class="sxs-lookup"><span data-stu-id="c0dd3-114">If the IL is not instrumented, the method returns `E_INVALIDARG`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0dd3-115">要求</span><span class="sxs-lookup"><span data-stu-id="c0dd3-115">Requirements</span></span>  
 <span data-ttu-id="c0dd3-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c0dd3-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0dd3-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0dd3-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0dd3-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0dd3-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0dd3-119">**.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0dd3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0dd3-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0dd3-120">See also</span></span>

- [<span data-ttu-id="c0dd3-121">ICorDebugILFrame4 接口</span><span class="sxs-lookup"><span data-stu-id="c0dd3-121">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="c0dd3-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="c0dd3-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c0dd3-123">ReJIT：操作方法指南</span><span class="sxs-lookup"><span data-stu-id="c0dd3-123">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
