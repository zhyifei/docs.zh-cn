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
ms.openlocfilehash: ba0e0b1b2bac785e28f41e09dda74841121a748d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794504"
---
# <a name="icordebugfunction-interface"></a><span data-ttu-id="4161f-102">ICorDebugFunction 接口</span><span class="sxs-lookup"><span data-stu-id="4161f-102">ICorDebugFunction Interface</span></span>

<span data-ttu-id="4161f-103">表示一个托管函数或方法。</span><span class="sxs-lookup"><span data-stu-id="4161f-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4161f-104">方法</span><span class="sxs-lookup"><span data-stu-id="4161f-104">Methods</span></span>  
  
|<span data-ttu-id="4161f-105">方法</span><span class="sxs-lookup"><span data-stu-id="4161f-105">Method</span></span>|<span data-ttu-id="4161f-106">描述</span><span class="sxs-lookup"><span data-stu-id="4161f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4161f-107">CreateBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="4161f-107">CreateBreakpoint Method</span></span>](icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="4161f-108">在此函数的开头创建一个断点。</span><span class="sxs-lookup"><span data-stu-id="4161f-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="4161f-109">GetClass 方法</span><span class="sxs-lookup"><span data-stu-id="4161f-109">GetClass Method</span></span>](icordebugfunction-getclass-method.md)|<span data-ttu-id="4161f-110">获取一个 ICorDebugClass 对象，该对象表示此函数所属的类。</span><span class="sxs-lookup"><span data-stu-id="4161f-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="4161f-111">GetCurrentVersionNumber 方法</span><span class="sxs-lookup"><span data-stu-id="4161f-111">GetCurrentVersionNumber Method</span></span>](icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="4161f-112">获取对此函数进行的最新编辑的版本号。</span><span class="sxs-lookup"><span data-stu-id="4161f-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="4161f-113">GetILCode 方法</span><span class="sxs-lookup"><span data-stu-id="4161f-113">GetILCode Method</span></span>](icordebugfunction-getilcode-method.md)|<span data-ttu-id="4161f-114">获取此函数的 Microsoft 中间语言（MSIL）代码。</span><span class="sxs-lookup"><span data-stu-id="4161f-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="4161f-115">GetLocalVarSigToken 方法</span><span class="sxs-lookup"><span data-stu-id="4161f-115">GetLocalVarSigToken Method</span></span>](icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="4161f-116">获取此 `ICorDebugFunction` 实例所表示的函数的局部变量签名的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="4161f-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="4161f-117">GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="4161f-117">GetModule Method</span></span>](icordebugfunction-getmodule-method.md)|<span data-ttu-id="4161f-118">获取在其中定义此函数的模块。</span><span class="sxs-lookup"><span data-stu-id="4161f-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="4161f-119">GetNativeCode 方法</span><span class="sxs-lookup"><span data-stu-id="4161f-119">GetNativeCode Method</span></span>](icordebugfunction-getnativecode-method.md)|<span data-ttu-id="4161f-120">获取此函数的本机代码。</span><span class="sxs-lookup"><span data-stu-id="4161f-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="4161f-121">GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="4161f-121">GetToken Method</span></span>](icordebugfunction-gettoken-method.md)|<span data-ttu-id="4161f-122">获取此函数的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="4161f-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4161f-123">备注</span><span class="sxs-lookup"><span data-stu-id="4161f-123">Remarks</span></span>  
 <span data-ttu-id="4161f-124">`ICorDebugFunction` 接口不表示包含泛型类型参数的函数。</span><span class="sxs-lookup"><span data-stu-id="4161f-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="4161f-125">例如，`ICorDebugFunction` 实例将表示 `Func<T>` 而不是 `Func<string>`。</span><span class="sxs-lookup"><span data-stu-id="4161f-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="4161f-126">调用[ICorDebugILFrame2：： EnumerateTypeParameters](icordebugilframe2-enumeratetypeparameters-method.md)以获取泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="4161f-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="4161f-127">方法的元数据标记、`mdMethodDef`和方法 `ICorDebugFunction` 对象之间的关系取决于函数是否允许 "编辑并继续"：</span><span class="sxs-lookup"><span data-stu-id="4161f-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
- <span data-ttu-id="4161f-128">如果函数上不允许使用 "编辑并继续"，则 `ICorDebugFunction` 对象与 `mdMethodDef` 标记之间存在一对一关系。</span><span class="sxs-lookup"><span data-stu-id="4161f-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="4161f-129">也就是说，该函数有一个 `ICorDebugFunction` 对象和一个 `mdMethodDef` 标记。</span><span class="sxs-lookup"><span data-stu-id="4161f-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
- <span data-ttu-id="4161f-130">如果允许在函数上使用 "编辑并继续"，则 `ICorDebugFunction` 对象与 `mdMethodDef` 标记之间存在多对一的关系。</span><span class="sxs-lookup"><span data-stu-id="4161f-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="4161f-131">也就是说，该函数可能有多个 `ICorDebugFunction`实例，每个版本对应一个函数，但只有一个 `mdMethodDef` 标记。</span><span class="sxs-lookup"><span data-stu-id="4161f-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4161f-132">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="4161f-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4161f-133">需求</span><span class="sxs-lookup"><span data-stu-id="4161f-133">Requirements</span></span>  
 <span data-ttu-id="4161f-134">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4161f-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4161f-135">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4161f-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4161f-136">**库：** Corguids.lib</span><span class="sxs-lookup"><span data-stu-id="4161f-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="4161f-137">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4161f-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4161f-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4161f-138">See also</span></span>

- [<span data-ttu-id="4161f-139">调试接口</span><span class="sxs-lookup"><span data-stu-id="4161f-139">Debugging Interfaces</span></span>](debugging-interfaces.md)
