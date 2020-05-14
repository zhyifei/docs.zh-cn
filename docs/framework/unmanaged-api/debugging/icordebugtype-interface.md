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
ms.openlocfilehash: 5e88652ff75223e30e6abc454f1e1af91494c7b2
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396692"
---
# <a name="icordebugtype-interface"></a><span data-ttu-id="3857d-102">ICorDebugType 接口</span><span class="sxs-lookup"><span data-stu-id="3857d-102">ICorDebugType Interface</span></span>
<span data-ttu-id="3857d-103">表示基本或复杂类型（即用户定义的类型）。</span><span class="sxs-lookup"><span data-stu-id="3857d-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="3857d-104">如果该类型是泛型类型，则 `ICorDebugType` 表示未实例化的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="3857d-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3857d-105">方法</span><span class="sxs-lookup"><span data-stu-id="3857d-105">Methods</span></span>  
  
|<span data-ttu-id="3857d-106">方法</span><span class="sxs-lookup"><span data-stu-id="3857d-106">Method</span></span>|<span data-ttu-id="3857d-107">说明</span><span class="sxs-lookup"><span data-stu-id="3857d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3857d-108">EnumerateTypeParameters 方法</span><span class="sxs-lookup"><span data-stu-id="3857d-108">EnumerateTypeParameters Method</span></span>](icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="3857d-109">获取一个接口指针，该指针指向引用 <xref:System.Type> 此所引用类的泛型参数的 ICorDebugTypeEnum `ICorDebugType` 。</span><span class="sxs-lookup"><span data-stu-id="3857d-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="3857d-110">GetBase 方法</span><span class="sxs-lookup"><span data-stu-id="3857d-110">GetBase Method</span></span>](icordebugtype-getbase-method.md)|<span data-ttu-id="3857d-111">获取一个接口指针，该指针指向 `ICorDebugType` 引用此引用的类 `ICorDebugType` （如果存在此类）的基类。</span><span class="sxs-lookup"><span data-stu-id="3857d-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="3857d-112">GetClass 方法</span><span class="sxs-lookup"><span data-stu-id="3857d-112">GetClass Method</span></span>](icordebugtype-getclass-method.md)|<span data-ttu-id="3857d-113">获取一个接口指针，该指针指向引用此的类型化构造函数的 ICorDebugClass `ICorDebugType` 。</span><span class="sxs-lookup"><span data-stu-id="3857d-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="3857d-114">GetFirstTypeParameter 方法</span><span class="sxs-lookup"><span data-stu-id="3857d-114">GetFirstTypeParameter Method</span></span>](icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="3857d-115">获取一个接口指针 `ICorDebugType` ，该指针指向引用此引用的类的构造函数的第一个泛型 <xref:System.Type> 参数 `ICorDebugType` 。</span><span class="sxs-lookup"><span data-stu-id="3857d-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="3857d-116">GetRank 方法</span><span class="sxs-lookup"><span data-stu-id="3857d-116">GetRank Method</span></span>](icordebugtype-getrank-method.md)|<span data-ttu-id="3857d-117">获取数组类型中的维度数。</span><span class="sxs-lookup"><span data-stu-id="3857d-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="3857d-118">GetStaticFieldValue 方法</span><span class="sxs-lookup"><span data-stu-id="3857d-118">GetStaticFieldValue Method</span></span>](icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="3857d-119">获取一个指向 ICorDebugValue 的接口指针，该指针包含指定的堆栈帧中指定字段标记所引用的静态字段的值。</span><span class="sxs-lookup"><span data-stu-id="3857d-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="3857d-120">GetType 方法</span><span class="sxs-lookup"><span data-stu-id="3857d-120">GetType Method</span></span>](icordebugtype-gettype-method.md)|<span data-ttu-id="3857d-121">获取一个 CorElementType 值，该值描述此所引用的公共语言运行时的本机类型 <xref:System.Type> `ICorDebugType` 。</span><span class="sxs-lookup"><span data-stu-id="3857d-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3857d-122">备注</span><span class="sxs-lookup"><span data-stu-id="3857d-122">Remarks</span></span>  
 <span data-ttu-id="3857d-123">如果类型为泛型，则 `ICorDebugClass` 表示未实例化的类型。</span><span class="sxs-lookup"><span data-stu-id="3857d-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="3857d-124">`ICorDebugType`接口表示一个实例化的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="3857d-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="3857d-125">例如，哈希表 \< K，V> 将由表示 `ICorDebugClass` ，而哈希表 \< Int32，字符串> 将由表示 `ICorDebugType` 。</span><span class="sxs-lookup"><span data-stu-id="3857d-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="3857d-126">非泛型类型由 `ICorDebugClass` 和表示 `ICorDebugType` 。</span><span class="sxs-lookup"><span data-stu-id="3857d-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="3857d-127">后一种接口在 .NET Framework 版本2.0 中引入，用于处理类型实例化。</span><span class="sxs-lookup"><span data-stu-id="3857d-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3857d-128">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="3857d-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3857d-129">要求</span><span class="sxs-lookup"><span data-stu-id="3857d-129">Requirements</span></span>  
 <span data-ttu-id="3857d-130">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3857d-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3857d-131">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3857d-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3857d-132">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3857d-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3857d-133">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3857d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3857d-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="3857d-134">See also</span></span>

- [<span data-ttu-id="3857d-135">调试接口</span><span class="sxs-lookup"><span data-stu-id="3857d-135">Debugging Interfaces</span></span>](debugging-interfaces.md)
