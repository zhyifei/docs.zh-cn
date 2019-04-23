---
title: ICorDebugFunction 接口
ms.date: 03/30/2017
api_name:
- ICorDebugFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction
helpviewer_keywords:
- ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca21911f3d16b79887b9d6d8185f8fab17651321
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093210"
---
# <a name="icordebugfunction-interface"></a><span data-ttu-id="db817-102">ICorDebugFunction 接口</span><span class="sxs-lookup"><span data-stu-id="db817-102">ICorDebugFunction Interface</span></span>

<span data-ttu-id="db817-103">表示一个托管函数或方法。</span><span class="sxs-lookup"><span data-stu-id="db817-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="db817-104">方法</span><span class="sxs-lookup"><span data-stu-id="db817-104">Methods</span></span>  
  
|<span data-ttu-id="db817-105">方法</span><span class="sxs-lookup"><span data-stu-id="db817-105">Method</span></span>|<span data-ttu-id="db817-106">描述</span><span class="sxs-lookup"><span data-stu-id="db817-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="db817-107">CreateBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="db817-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="db817-108">此函数的开始处创建断点。</span><span class="sxs-lookup"><span data-stu-id="db817-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="db817-109">GetClass 方法</span><span class="sxs-lookup"><span data-stu-id="db817-109">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|<span data-ttu-id="db817-110">获取一个 ICorDebugClass 对象，表示此函数的类。</span><span class="sxs-lookup"><span data-stu-id="db817-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="db817-111">GetCurrentVersionNumber 方法</span><span class="sxs-lookup"><span data-stu-id="db817-111">GetCurrentVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="db817-112">获取对此函数所做的最新编辑的版本号。</span><span class="sxs-lookup"><span data-stu-id="db817-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="db817-113">GetILCode 方法</span><span class="sxs-lookup"><span data-stu-id="db817-113">GetILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|<span data-ttu-id="db817-114">获取此函数的 Microsoft 中间语言 (MSIL) 代码。</span><span class="sxs-lookup"><span data-stu-id="db817-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="db817-115">GetLocalVarSigToken 方法</span><span class="sxs-lookup"><span data-stu-id="db817-115">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="db817-116">获取表示此函数的局部变量签名的元数据令牌`ICorDebugFunction`实例。</span><span class="sxs-lookup"><span data-stu-id="db817-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="db817-117">GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="db817-117">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|<span data-ttu-id="db817-118">获取在其中定义此函数的模块。</span><span class="sxs-lookup"><span data-stu-id="db817-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="db817-119">GetNativeCode 方法</span><span class="sxs-lookup"><span data-stu-id="db817-119">GetNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|<span data-ttu-id="db817-120">获取此函数的本机代码。</span><span class="sxs-lookup"><span data-stu-id="db817-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="db817-121">GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="db817-121">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|<span data-ttu-id="db817-122">获取此函数的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="db817-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db817-123">备注</span><span class="sxs-lookup"><span data-stu-id="db817-123">Remarks</span></span>  
 <span data-ttu-id="db817-124">`ICorDebugFunction`接口不表示泛型类型参数的函数。</span><span class="sxs-lookup"><span data-stu-id="db817-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="db817-125">例如，`ICorDebugFunction`实例将表示`Func<T>`但不是`Func<string>`。</span><span class="sxs-lookup"><span data-stu-id="db817-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="db817-126">调用[ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)获取泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="db817-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="db817-127">方法的元数据标记之间的关系`mdMethodDef`，和方法的`ICorDebugFunction`对象所依赖的函数上是否允许编辑并继续：</span><span class="sxs-lookup"><span data-stu-id="db817-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
-   <span data-ttu-id="db817-128">如果该函数不允许编辑并继续，之间存在一对一的关系`ICorDebugFunction`对象和`mdMethodDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="db817-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="db817-129">也就是说，该函数具有一个`ICorDebugFunction`对象，另一个`mdMethodDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="db817-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
-   <span data-ttu-id="db817-130">编辑并继续允许对该函数，如果之间存在多对一关系`ICorDebugFunction`对象和`mdMethodDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="db817-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="db817-131">这就是，该函数可能具有的多个实例`ICorDebugFunction`，一个用于每个版本的函数，但只有一个`mdMethodDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="db817-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db817-132">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="db817-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db817-133">要求</span><span class="sxs-lookup"><span data-stu-id="db817-133">Requirements</span></span>  
 <span data-ttu-id="db817-134">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="db817-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db817-135">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db817-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db817-136">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db817-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="db817-137">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db817-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db817-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="db817-138">See also</span></span>

- [<span data-ttu-id="db817-139">调试接口</span><span class="sxs-lookup"><span data-stu-id="db817-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
