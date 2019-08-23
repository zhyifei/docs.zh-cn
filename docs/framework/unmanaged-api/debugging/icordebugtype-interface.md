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
ms.openlocfilehash: b830af5d59c0eb177d815451ecedbdc14121aaad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964761"
---
# <a name="icordebugtype-interface"></a><span data-ttu-id="5e52a-102">ICorDebugType 接口</span><span class="sxs-lookup"><span data-stu-id="5e52a-102">ICorDebugType Interface</span></span>
<span data-ttu-id="5e52a-103">表示基本或复杂类型 (即用户定义的类型)。</span><span class="sxs-lookup"><span data-stu-id="5e52a-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="5e52a-104">如果该类型是泛型类型，则 `ICorDebugType` 表示未实例化的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="5e52a-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5e52a-105">方法</span><span class="sxs-lookup"><span data-stu-id="5e52a-105">Methods</span></span>  
  
|<span data-ttu-id="5e52a-106">方法</span><span class="sxs-lookup"><span data-stu-id="5e52a-106">Method</span></span>|<span data-ttu-id="5e52a-107">描述</span><span class="sxs-lookup"><span data-stu-id="5e52a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5e52a-108">EnumerateTypeParameters 方法</span><span class="sxs-lookup"><span data-stu-id="5e52a-108">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="5e52a-109">获取一个接口指针, 该指针指向引用此<xref:System.Type> `ICorDebugType`所引用类的泛型参数的 ICorDebugTypeEnum。</span><span class="sxs-lookup"><span data-stu-id="5e52a-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="5e52a-110">GetBase 方法</span><span class="sxs-lookup"><span data-stu-id="5e52a-110">GetBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|<span data-ttu-id="5e52a-111">获取一个接口指针, `ICorDebugType`该指针指向引用此引用的类 (如果存在此`ICorDebugType`类) 的基类。</span><span class="sxs-lookup"><span data-stu-id="5e52a-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="5e52a-112">GetClass 方法</span><span class="sxs-lookup"><span data-stu-id="5e52a-112">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|<span data-ttu-id="5e52a-113">获取一个接口指针, 该指针指向引用此`ICorDebugType`的类型化构造函数的 ICorDebugClass。</span><span class="sxs-lookup"><span data-stu-id="5e52a-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="5e52a-114">GetFirstTypeParameter 方法</span><span class="sxs-lookup"><span data-stu-id="5e52a-114">GetFirstTypeParameter Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="5e52a-115">获取一个接口指针`ICorDebugType` , 该指针指向引用此`ICorDebugType`引用<xref:System.Type>的类的构造函数的第一个泛型参数。</span><span class="sxs-lookup"><span data-stu-id="5e52a-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="5e52a-116">GetRank 方法</span><span class="sxs-lookup"><span data-stu-id="5e52a-116">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|<span data-ttu-id="5e52a-117">获取数组类型中的维度数。</span><span class="sxs-lookup"><span data-stu-id="5e52a-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="5e52a-118">GetStaticFieldValue 方法</span><span class="sxs-lookup"><span data-stu-id="5e52a-118">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="5e52a-119">获取一个指向 ICorDebugValue 的接口指针, 该指针包含指定的堆栈帧中指定字段标记所引用的静态字段的值。</span><span class="sxs-lookup"><span data-stu-id="5e52a-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="5e52a-120">GetType 方法</span><span class="sxs-lookup"><span data-stu-id="5e52a-120">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|<span data-ttu-id="5e52a-121">获取一个 CorElementType 值, 该值描述此<xref:System.Type> `ICorDebugType`所引用的公共语言运行时的本机类型。</span><span class="sxs-lookup"><span data-stu-id="5e52a-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e52a-122">备注</span><span class="sxs-lookup"><span data-stu-id="5e52a-122">Remarks</span></span>  
 <span data-ttu-id="5e52a-123">如果类型为泛型, `ICorDebugClass`则表示未实例化的类型。</span><span class="sxs-lookup"><span data-stu-id="5e52a-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="5e52a-124">`ICorDebugType`接口表示一个实例化的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="5e52a-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="5e52a-125">例如, 哈希\<表 K, V > 将由`ICorDebugClass`表示, 而哈\<希表`ICorDebugType`Int32, 字符串 > 将由表示。</span><span class="sxs-lookup"><span data-stu-id="5e52a-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="5e52a-126">非泛型类型由`ICorDebugClass`和`ICorDebugType`表示。</span><span class="sxs-lookup"><span data-stu-id="5e52a-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="5e52a-127">后一种接口在 .NET Framework 版本2.0 中引入, 用于处理类型实例化。</span><span class="sxs-lookup"><span data-stu-id="5e52a-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5e52a-128">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="5e52a-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e52a-129">要求</span><span class="sxs-lookup"><span data-stu-id="5e52a-129">Requirements</span></span>  
 <span data-ttu-id="5e52a-130">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5e52a-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e52a-131">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="5e52a-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e52a-132">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e52a-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e52a-133">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e52a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e52a-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e52a-134">See also</span></span>

- [<span data-ttu-id="5e52a-135">调试接口</span><span class="sxs-lookup"><span data-stu-id="5e52a-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
