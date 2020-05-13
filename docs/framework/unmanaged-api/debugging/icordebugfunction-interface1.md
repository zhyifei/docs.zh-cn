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
ms.openlocfilehash: 6b7b6969c1f207decbf47217e98b7fee3aa9ce54
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213231"
---
# <a name="icordebugfunction-interface"></a><span data-ttu-id="56b9e-102">ICorDebugFunction 接口</span><span class="sxs-lookup"><span data-stu-id="56b9e-102">ICorDebugFunction Interface</span></span>

<span data-ttu-id="56b9e-103">表示一个托管函数或方法。</span><span class="sxs-lookup"><span data-stu-id="56b9e-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="56b9e-104">方法</span><span class="sxs-lookup"><span data-stu-id="56b9e-104">Methods</span></span>  
  
|<span data-ttu-id="56b9e-105">方法</span><span class="sxs-lookup"><span data-stu-id="56b9e-105">Method</span></span>|<span data-ttu-id="56b9e-106">描述</span><span class="sxs-lookup"><span data-stu-id="56b9e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="56b9e-107">CreateBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="56b9e-107">CreateBreakpoint Method</span></span>](icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="56b9e-108">在此函数的开头创建一个断点。</span><span class="sxs-lookup"><span data-stu-id="56b9e-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="56b9e-109">GetClass 方法</span><span class="sxs-lookup"><span data-stu-id="56b9e-109">GetClass Method</span></span>](icordebugfunction-getclass-method.md)|<span data-ttu-id="56b9e-110">获取一个 ICorDebugClass 对象，该对象表示此函数所属的类。</span><span class="sxs-lookup"><span data-stu-id="56b9e-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="56b9e-111">GetCurrentVersionNumber 方法</span><span class="sxs-lookup"><span data-stu-id="56b9e-111">GetCurrentVersionNumber Method</span></span>](icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="56b9e-112">获取对此函数进行的最新编辑的版本号。</span><span class="sxs-lookup"><span data-stu-id="56b9e-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="56b9e-113">GetILCode 方法</span><span class="sxs-lookup"><span data-stu-id="56b9e-113">GetILCode Method</span></span>](icordebugfunction-getilcode-method.md)|<span data-ttu-id="56b9e-114">获取此函数的 Microsoft 中间语言（MSIL）代码。</span><span class="sxs-lookup"><span data-stu-id="56b9e-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="56b9e-115">GetLocalVarSigToken 方法</span><span class="sxs-lookup"><span data-stu-id="56b9e-115">GetLocalVarSigToken Method</span></span>](icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="56b9e-116">获取由此实例表示的函数的局部变量签名的元数据标记 `ICorDebugFunction` 。</span><span class="sxs-lookup"><span data-stu-id="56b9e-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="56b9e-117">GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="56b9e-117">GetModule Method</span></span>](icordebugfunction-getmodule-method.md)|<span data-ttu-id="56b9e-118">获取在其中定义此函数的模块。</span><span class="sxs-lookup"><span data-stu-id="56b9e-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="56b9e-119">GetNativeCode 方法</span><span class="sxs-lookup"><span data-stu-id="56b9e-119">GetNativeCode Method</span></span>](icordebugfunction-getnativecode-method.md)|<span data-ttu-id="56b9e-120">获取此函数的本机代码。</span><span class="sxs-lookup"><span data-stu-id="56b9e-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="56b9e-121">GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="56b9e-121">GetToken Method</span></span>](icordebugfunction-gettoken-method.md)|<span data-ttu-id="56b9e-122">获取此函数的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="56b9e-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56b9e-123">备注</span><span class="sxs-lookup"><span data-stu-id="56b9e-123">Remarks</span></span>  
 <span data-ttu-id="56b9e-124">`ICorDebugFunction`接口不表示包含泛型类型参数的函数。</span><span class="sxs-lookup"><span data-stu-id="56b9e-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="56b9e-125">例如，一个 `ICorDebugFunction` 实例将表示， `Func<T>` 而不是 `Func<string>` 。</span><span class="sxs-lookup"><span data-stu-id="56b9e-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="56b9e-126">调用[ICorDebugILFrame2：： EnumerateTypeParameters](icordebugilframe2-enumeratetypeparameters-method.md)以获取泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="56b9e-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="56b9e-127">方法的元数据标记、 `mdMethodDef` 和方法的对象之间的关系 `ICorDebugFunction` 取决于函数是否允许 "编辑并继续"：</span><span class="sxs-lookup"><span data-stu-id="56b9e-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
- <span data-ttu-id="56b9e-128">如果函数上不允许使用 "编辑并继续"，则在对象与标记之间存在一对一关系 `ICorDebugFunction` `mdMethodDef` 。</span><span class="sxs-lookup"><span data-stu-id="56b9e-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="56b9e-129">也就是说，该函数有一个 `ICorDebugFunction` 对象和一个 `mdMethodDef` 标记。</span><span class="sxs-lookup"><span data-stu-id="56b9e-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
- <span data-ttu-id="56b9e-130">如果允许在函数上使用 "编辑并继续"，则在对象与标记之间存在多对一关系 `ICorDebugFunction` `mdMethodDef` 。</span><span class="sxs-lookup"><span data-stu-id="56b9e-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="56b9e-131">也就是说，该函数可能有多个实例 `ICorDebugFunction` ，每个版本一个，而只是一个 `mdMethodDef` 标记。</span><span class="sxs-lookup"><span data-stu-id="56b9e-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="56b9e-132">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="56b9e-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56b9e-133">要求</span><span class="sxs-lookup"><span data-stu-id="56b9e-133">Requirements</span></span>  
 <span data-ttu-id="56b9e-134">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="56b9e-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56b9e-135">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56b9e-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56b9e-136">**库：** Corguids.lib</span><span class="sxs-lookup"><span data-stu-id="56b9e-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="56b9e-137">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56b9e-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56b9e-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="56b9e-138">See also</span></span>

- [<span data-ttu-id="56b9e-139">调试接口</span><span class="sxs-lookup"><span data-stu-id="56b9e-139">Debugging Interfaces</span></span>](debugging-interfaces.md)
