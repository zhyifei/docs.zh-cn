---
title: ICorDebugType 接口
ms.date: 03/30/2017
api_name:
- ICorDebugType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType
helpviewer_keywords:
- ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74863af1096f8600b8095e593c1f3c820c512e9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166798"
---
# <a name="icordebugtype-interface"></a><span data-ttu-id="dd4d8-102">ICorDebugType 接口</span><span class="sxs-lookup"><span data-stu-id="dd4d8-102">ICorDebugType Interface</span></span>
<span data-ttu-id="dd4d8-103">表示的类型，基本或复杂 （是，用户定义的）。</span><span class="sxs-lookup"><span data-stu-id="dd4d8-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="dd4d8-104">如果该类型是泛型类型，则 `ICorDebugType` 表示未实例化的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="dd4d8-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dd4d8-105">方法</span><span class="sxs-lookup"><span data-stu-id="dd4d8-105">Methods</span></span>  
  
|<span data-ttu-id="dd4d8-106">方法</span><span class="sxs-lookup"><span data-stu-id="dd4d8-106">Method</span></span>|<span data-ttu-id="dd4d8-107">描述</span><span class="sxs-lookup"><span data-stu-id="dd4d8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dd4d8-108">EnumerateTypeParameters 方法</span><span class="sxs-lookup"><span data-stu-id="dd4d8-108">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="dd4d8-109">获取一个接口指针到引用泛型 ICorDebugTypeEnum<xref:System.Type>引用此类参数`ICorDebugType`。</span><span class="sxs-lookup"><span data-stu-id="dd4d8-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="dd4d8-110">GetBase 方法</span><span class="sxs-lookup"><span data-stu-id="dd4d8-110">GetBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|<span data-ttu-id="dd4d8-111">获取到的接口指针`ICorDebugType`引用此引用的类的基类`ICorDebugType`，如果存在一个。</span><span class="sxs-lookup"><span data-stu-id="dd4d8-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="dd4d8-112">GetClass 方法</span><span class="sxs-lookup"><span data-stu-id="dd4d8-112">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|<span data-ttu-id="dd4d8-113">获取一个接口指针到引用此类型化的构造函数 ICorDebugClass `ICorDebugType`。</span><span class="sxs-lookup"><span data-stu-id="dd4d8-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="dd4d8-114">GetFirstTypeParameter 方法</span><span class="sxs-lookup"><span data-stu-id="dd4d8-114">GetFirstTypeParameter Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="dd4d8-115">获取到的接口指针`ICorDebugType`引用的第一个泛型<xref:System.Type>此引用的类，构造函数参数`ICorDebugType`。</span><span class="sxs-lookup"><span data-stu-id="dd4d8-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="dd4d8-116">GetRank 方法</span><span class="sxs-lookup"><span data-stu-id="dd4d8-116">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|<span data-ttu-id="dd4d8-117">获取数组类型中的维度数。</span><span class="sxs-lookup"><span data-stu-id="dd4d8-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="dd4d8-118">GetStaticFieldValue 方法</span><span class="sxs-lookup"><span data-stu-id="dd4d8-118">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="dd4d8-119">获取为包含值的按指定字段引用的静态字段 ICorDebugValue 接口指针标记中指定的堆栈帧。</span><span class="sxs-lookup"><span data-stu-id="dd4d8-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="dd4d8-120">GetType 方法</span><span class="sxs-lookup"><span data-stu-id="dd4d8-120">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|<span data-ttu-id="dd4d8-121">获取用于描述公共语言运行时的本机类型的 CorElementType 值<xref:System.Type>引用此`ICorDebugType`。</span><span class="sxs-lookup"><span data-stu-id="dd4d8-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd4d8-122">备注</span><span class="sxs-lookup"><span data-stu-id="dd4d8-122">Remarks</span></span>  
 <span data-ttu-id="dd4d8-123">如果类型是泛型，`ICorDebugClass`表示未实例化的类型。</span><span class="sxs-lookup"><span data-stu-id="dd4d8-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="dd4d8-124">`ICorDebugType`接口表示实例化泛型类型。</span><span class="sxs-lookup"><span data-stu-id="dd4d8-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="dd4d8-125">例如，哈希表\<K，V > 将由表示`ICorDebugClass`，而哈希表\<Int32，String > 将由表示`ICorDebugType`。</span><span class="sxs-lookup"><span data-stu-id="dd4d8-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="dd4d8-126">非泛型类型表示由`ICorDebugClass`和`ICorDebugType`。</span><span class="sxs-lookup"><span data-stu-id="dd4d8-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="dd4d8-127">在处理类型实例化在.NET Framework 2.0 版中引入的后一种接口。</span><span class="sxs-lookup"><span data-stu-id="dd4d8-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd4d8-128">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="dd4d8-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd4d8-129">要求</span><span class="sxs-lookup"><span data-stu-id="dd4d8-129">Requirements</span></span>  
 <span data-ttu-id="dd4d8-130">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dd4d8-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd4d8-131">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd4d8-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd4d8-132">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd4d8-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd4d8-133">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd4d8-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd4d8-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd4d8-134">See also</span></span>

- [<span data-ttu-id="dd4d8-135">调试接口</span><span class="sxs-lookup"><span data-stu-id="dd4d8-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
