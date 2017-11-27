---
title: "ICorDebugFunction 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction
helpviewer_keywords: ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 327ef9f74e94e3b1b20e78eb6a833038b5bfe16d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunction-interface1"></a><span data-ttu-id="cfe09-102">ICorDebugFunction 接口 1</span><span class="sxs-lookup"><span data-stu-id="cfe09-102">ICorDebugFunction Interface1</span></span>
<span data-ttu-id="cfe09-103">表示一个托管函数或方法。</span><span class="sxs-lookup"><span data-stu-id="cfe09-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cfe09-104">方法</span><span class="sxs-lookup"><span data-stu-id="cfe09-104">Methods</span></span>  
  
|<span data-ttu-id="cfe09-105">方法</span><span class="sxs-lookup"><span data-stu-id="cfe09-105">Method</span></span>|<span data-ttu-id="cfe09-106">描述</span><span class="sxs-lookup"><span data-stu-id="cfe09-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cfe09-107">CreateBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="cfe09-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="cfe09-108">此函数的开始处创建断点。</span><span class="sxs-lookup"><span data-stu-id="cfe09-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="cfe09-109">GetClass 方法</span><span class="sxs-lookup"><span data-stu-id="cfe09-109">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|<span data-ttu-id="cfe09-110">获取表示此函数是的成员的类的 ICorDebugClass 对象。</span><span class="sxs-lookup"><span data-stu-id="cfe09-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="cfe09-111">GetCurrentVersionNumber 方法</span><span class="sxs-lookup"><span data-stu-id="cfe09-111">GetCurrentVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="cfe09-112">获取对此函数进行的最新编辑的版本号。</span><span class="sxs-lookup"><span data-stu-id="cfe09-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="cfe09-113">GetILCode 方法</span><span class="sxs-lookup"><span data-stu-id="cfe09-113">GetILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|<span data-ttu-id="cfe09-114">此函数获取 Microsoft 中间语言 (MSIL) 代码。</span><span class="sxs-lookup"><span data-stu-id="cfe09-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="cfe09-115">GetLocalVarSigToken 方法</span><span class="sxs-lookup"><span data-stu-id="cfe09-115">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="cfe09-116">获取元数据标记表示由此的函数的局部变量签名`ICorDebugFunction`实例。</span><span class="sxs-lookup"><span data-stu-id="cfe09-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="cfe09-117">GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="cfe09-117">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|<span data-ttu-id="cfe09-118">获取在其中定义此函数的模块。</span><span class="sxs-lookup"><span data-stu-id="cfe09-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="cfe09-119">GetNativeCode 方法</span><span class="sxs-lookup"><span data-stu-id="cfe09-119">GetNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|<span data-ttu-id="cfe09-120">获取此函数的本机代码。</span><span class="sxs-lookup"><span data-stu-id="cfe09-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="cfe09-121">GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="cfe09-121">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|<span data-ttu-id="cfe09-122">获取此函数的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="cfe09-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfe09-123">备注</span><span class="sxs-lookup"><span data-stu-id="cfe09-123">Remarks</span></span>  
 <span data-ttu-id="cfe09-124">`ICorDebugFunction`接口不表示带泛型类型参数的函数。</span><span class="sxs-lookup"><span data-stu-id="cfe09-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="cfe09-125">例如，`ICorDebugFunction`实例将表示`Func<T>`但不是`Func<string>`。</span><span class="sxs-lookup"><span data-stu-id="cfe09-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="cfe09-126">调用[icordebugilframe2:: Enumeratetypeparameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)来获取泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="cfe09-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="cfe09-127">该方法的元数据标记之间的关系`mdMethodDef`，和方法的`ICorDebugFunction`对象所依赖的函数上是否允许编辑并继续：</span><span class="sxs-lookup"><span data-stu-id="cfe09-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
-   <span data-ttu-id="cfe09-128">如果对该函数不允许编辑并继续，之间存在一对一的关系`ICorDebugFunction`对象和`mdMethodDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="cfe09-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="cfe09-129">也就是说，该函数具有一个`ICorDebugFunction`对象和一个`mdMethodDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="cfe09-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
-   <span data-ttu-id="cfe09-130">如果允许编辑并继续，则对该函数，之间存在多对一关系`ICorDebugFunction`对象和`mdMethodDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="cfe09-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="cfe09-131">这就是，该函数可能具有的多个实例`ICorDebugFunction`，一个用于每个版本的函数，但只能是一个`mdMethodDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="cfe09-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cfe09-132">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="cfe09-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfe09-133">要求</span><span class="sxs-lookup"><span data-stu-id="cfe09-133">Requirements</span></span>  
 <span data-ttu-id="cfe09-134">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cfe09-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfe09-135">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cfe09-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cfe09-136">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfe09-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfe09-137">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfe09-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfe09-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cfe09-138">See Also</span></span>  
 [<span data-ttu-id="cfe09-139">调试接口</span><span class="sxs-lookup"><span data-stu-id="cfe09-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
