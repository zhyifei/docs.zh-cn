---
title: ICorDebugILFrame4::EnumerateLocalVariablesEx 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.EnumerateLocalVariablesEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6f60aae6-70ec-4c4c-963a-138df98c4668
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f9d20eda8684a9a5ae43c6240d0f8a9722c4d97
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076830"
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a><span data-ttu-id="c1d13-102">ICorDebugILFrame4::EnumerateLocalVariablesEx 方法</span><span class="sxs-lookup"><span data-stu-id="c1d13-102">ICorDebugILFrame4::EnumerateLocalVariablesEx Method</span></span>
<span data-ttu-id="c1d13-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="c1d13-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="c1d13-104">获取帧中局部变量的枚举，并且（可选）包括在探查器 ReJIT 检测中添加的变量。</span><span class="sxs-lookup"><span data-stu-id="c1d13-104">Gets an enumerator for the local variable in the frame, and optionally includes variables added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1d13-105">语法</span><span class="sxs-lookup"><span data-stu-id="c1d13-105">Syntax</span></span>  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1d13-106">参数</span><span class="sxs-lookup"><span data-stu-id="c1d13-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="c1d13-107">[in][ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md)枚举成员，用于指定探查器 ReJIT 检测中添加的变量包含在帧。</span><span class="sxs-lookup"><span data-stu-id="c1d13-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether variables added in profiler ReJIT instrumentation are included in the frame.</span></span>  
  
 `ppValueEnum`  
 <span data-ttu-id="c1d13-108">[out]指向一个"ICorDebugValueEnum"对象，它在此帧中局部变量的枚举器的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="c1d13-108">[out] A pointer to the address of an "ICorDebugValueEnum" object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1d13-109">备注</span><span class="sxs-lookup"><span data-stu-id="c1d13-109">Remarks</span></span>  
 <span data-ttu-id="c1d13-110">此方法是类似于[EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)方法，但它还可以访问在探查器 ReJIT 检测中添加的变量。</span><span class="sxs-lookup"><span data-stu-id="c1d13-110">This method is similar to the [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md) method, except that it optionally accesses variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="c1d13-111">设置`flags`到`ILCODE_ORIGINAL_IL`等效于调用[icordebugilframe:: Enumeratelocalvariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)。</span><span class="sxs-lookup"><span data-stu-id="c1d13-111">Setting `flags` to `ILCODE_ORIGINAL_IL` is equivalent to calling [ICorDebugILFrame::EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md).</span></span> <span data-ttu-id="c1d13-112">将 `flags` 设置为 `ILCODE_REJIT_IL` 使调试器能够访问在探查器 ReJIT 检测中添加的局部变量。</span><span class="sxs-lookup"><span data-stu-id="c1d13-112">Setting `flags` to `ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="c1d13-113">如果未检测到中间语言 (IL)，则枚举为空且该方法将返回 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="c1d13-113">If the intermediate language (IL) is not instrumented, the enumeration is empty and the method returns `S_OK`.</span></span>  
  
 <span data-ttu-id="c1d13-114">由于某些局部变量可能未处于活动状态，因此枚举器可能不包括正在运行的方法中的所有局部变量。</span><span class="sxs-lookup"><span data-stu-id="c1d13-114">The enumerator may not include all of the local variables in the running method, since some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1d13-115">要求</span><span class="sxs-lookup"><span data-stu-id="c1d13-115">Requirements</span></span>  
 <span data-ttu-id="c1d13-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c1d13-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1d13-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c1d13-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1d13-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1d13-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1d13-119">**.NET Framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1d13-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1d13-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1d13-120">See also</span></span>

- [<span data-ttu-id="c1d13-121">ICorDebugILFrame4 接口</span><span class="sxs-lookup"><span data-stu-id="c1d13-121">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="c1d13-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="c1d13-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c1d13-123">ReJIT:操作方法指南</span><span class="sxs-lookup"><span data-stu-id="c1d13-123">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
