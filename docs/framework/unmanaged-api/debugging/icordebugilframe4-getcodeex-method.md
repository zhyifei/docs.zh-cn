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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24be4507e8ad6cde1e9c50582e352f0fc9b12ed3
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45741923"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="380da-102">ICorDebugILFrame4::GetCodeEx 方法</span><span class="sxs-lookup"><span data-stu-id="380da-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="380da-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="380da-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="380da-104">获取指向此堆栈帧正在执行的代码的指针。</span><span class="sxs-lookup"><span data-stu-id="380da-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="380da-105">语法</span><span class="sxs-lookup"><span data-stu-id="380da-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="380da-106">参数</span><span class="sxs-lookup"><span data-stu-id="380da-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="380da-107">[in][ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md)枚举成员，指定是否由探查器的 ReJIT 请求定义的中间语言 (IL) 包含在帧。</span><span class="sxs-lookup"><span data-stu-id="380da-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="380da-108">[out]指向表示此堆栈帧正在执行的代码"ICorDebugCode"对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="380da-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="380da-109">备注</span><span class="sxs-lookup"><span data-stu-id="380da-109">Remarks</span></span>  
 <span data-ttu-id="380da-110">此方法是类似于[icordebugframe:: Getcode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)方法，但它还可以访问由探查器的 ReJIT 请求定义的代码。</span><span class="sxs-lookup"><span data-stu-id="380da-110">This method is similar to the [ICorDebugFrame::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="380da-111">调用此方法与`flags`的值`ILCODE_ORIGINAL_IL`等效于调用[GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); 如果检测到该方法，则将无法访问其 IL。</span><span class="sxs-lookup"><span data-stu-id="380da-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="380da-112">`ILCODE_REJIT_IL` 允许调试器访问由探查器的 ReJIT 请求定义的 IL。</span><span class="sxs-lookup"><span data-stu-id="380da-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="380da-113">如果未检测到 IL，`ppCode`是**null**，并且该方法返回`S_OK`。</span><span class="sxs-lookup"><span data-stu-id="380da-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="380da-114">要求</span><span class="sxs-lookup"><span data-stu-id="380da-114">Requirements</span></span>  
 <span data-ttu-id="380da-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="380da-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="380da-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="380da-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="380da-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="380da-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="380da-118">**.NET Framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="380da-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="380da-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="380da-119">See Also</span></span>  
 [<span data-ttu-id="380da-120">ICorDebugILFrame4 接口</span><span class="sxs-lookup"><span data-stu-id="380da-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [<span data-ttu-id="380da-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="380da-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="380da-122">ReJIT： 操作指南</span><span class="sxs-lookup"><span data-stu-id="380da-122">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
