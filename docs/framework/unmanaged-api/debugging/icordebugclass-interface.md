---
title: "ICorDebugClass 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass
helpviewer_keywords: ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3998cf76430612759f69df07fb4f5afebd7a25ed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugclass-interface1"></a><span data-ttu-id="e2648-102">ICorDebugClass 接口 1</span><span class="sxs-lookup"><span data-stu-id="e2648-102">ICorDebugClass Interface1</span></span>
<span data-ttu-id="e2648-103">表示基类型或复杂类型（即用户定义的类型）。</span><span class="sxs-lookup"><span data-stu-id="e2648-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="e2648-104">如果该类型为泛型类型，则 `ICorDebugClass` 表示实例化的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="e2648-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e2648-105">方法</span><span class="sxs-lookup"><span data-stu-id="e2648-105">Methods</span></span>  
  
|<span data-ttu-id="e2648-106">方法</span><span class="sxs-lookup"><span data-stu-id="e2648-106">Method</span></span>|<span data-ttu-id="e2648-107">描述</span><span class="sxs-lookup"><span data-stu-id="e2648-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e2648-108">GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="e2648-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|<span data-ttu-id="e2648-109">获取定义此类的模块。</span><span class="sxs-lookup"><span data-stu-id="e2648-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="e2648-110">GetStaticFieldValue 方法</span><span class="sxs-lookup"><span data-stu-id="e2648-110">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="e2648-111">获取指定的静态字段的值。</span><span class="sxs-lookup"><span data-stu-id="e2648-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="e2648-112">GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="e2648-112">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|<span data-ttu-id="e2648-113">获取`TypeDef`元数据标记，此类。</span><span class="sxs-lookup"><span data-stu-id="e2648-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2648-114">备注</span><span class="sxs-lookup"><span data-stu-id="e2648-114">Remarks</span></span>  
 <span data-ttu-id="e2648-115">`ICorDebugClass`接口表示未实例化的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="e2648-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="e2648-116">ICorDebugType 接口表示实例化泛型类型。</span><span class="sxs-lookup"><span data-stu-id="e2648-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="e2648-117">例如，`Hashtable<K, V>`将由表示`ICorDebugClass`，而`Hashtable<Int32, String>`将由表示`ICorDebugType`。</span><span class="sxs-lookup"><span data-stu-id="e2648-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="e2648-118">非泛型类型表示两个`ICorDebugClass`和`ICorDebugType`。</span><span class="sxs-lookup"><span data-stu-id="e2648-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="e2648-119">类型实例化处理.NET Framework 2.0 版中引入了后者的接口。</span><span class="sxs-lookup"><span data-stu-id="e2648-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2648-120">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="e2648-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2648-121">惠?</span><span class="sxs-lookup"><span data-stu-id="e2648-121">Requirements</span></span>  
 <span data-ttu-id="e2648-122">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e2648-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2648-123">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2648-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2648-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2648-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2648-125">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2648-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2648-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2648-126">See Also</span></span>  
 [<span data-ttu-id="e2648-127">调试接口</span><span class="sxs-lookup"><span data-stu-id="e2648-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
