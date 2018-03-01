---
title: "ICorDebugClass2::GetParameterizedType 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugClass2.GetParameterizedType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a9cbb755bd8f52482f7eece6e9d236f29cadc419
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugclass2getparameterizedtype-method"></a><span data-ttu-id="64efe-102">ICorDebugClass2::GetParameterizedType 方法</span><span class="sxs-lookup"><span data-stu-id="64efe-102">ICorDebugClass2::GetParameterizedType Method</span></span>
<span data-ttu-id="64efe-103">获取此类的类型声明。</span><span class="sxs-lookup"><span data-stu-id="64efe-103">Gets the type declaration for this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64efe-104">语法</span><span class="sxs-lookup"><span data-stu-id="64efe-104">Syntax</span></span>  
  
```  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64efe-105">参数</span><span class="sxs-lookup"><span data-stu-id="64efe-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="64efe-106">[in]CorElementType 枚举，指定此类的元素类型的值： 将此值设置为 ELEMENT_TYPE_VALUETYPE，如果此 ICorDebugClass2 表示值类型。</span><span class="sxs-lookup"><span data-stu-id="64efe-106">[in] A value of the CorElementType enumeration that specifies the element type for this class: Set this value to ELEMENT_TYPE_VALUETYPE if this ICorDebugClass2 represents a value type.</span></span> <span data-ttu-id="64efe-107">将此值设置为 ELEMENT_TYPE_CLASS，如果此`ICorDebugClass2`表示一个复杂类型。</span><span class="sxs-lookup"><span data-stu-id="64efe-107">Set this value to ELEMENT_TYPE_CLASS if this `ICorDebugClass2` represents a complex type.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="64efe-108">[in]类型参数，如果该类型是泛型的数目。</span><span class="sxs-lookup"><span data-stu-id="64efe-108">[in] The number of type parameters, if the type is generic.</span></span> <span data-ttu-id="64efe-109">类型参数 （如果有） 的数目必须匹配由类所需的数量。</span><span class="sxs-lookup"><span data-stu-id="64efe-109">The number of type parameters (if any) must match the number required by the class.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="64efe-110">[in]一个指针数组，其中每个指向对象的表示类型参数。</span><span class="sxs-lookup"><span data-stu-id="64efe-110">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type parameter.</span></span> <span data-ttu-id="64efe-111">如果此类是非泛型，则此值为 null。</span><span class="sxs-lookup"><span data-stu-id="64efe-111">If the class is non-generic, this value is null.</span></span>  
  
 `ppType`  
 <span data-ttu-id="64efe-112">[out]指向的地址的指针`ICorDebugType`表示类型声明的对象。</span><span class="sxs-lookup"><span data-stu-id="64efe-112">[out] A pointer to the address of an `ICorDebugType` object that represents the type declaration.</span></span> <span data-ttu-id="64efe-113">此对象是否等效于<xref:System.Type>在托管代码中的对象。</span><span class="sxs-lookup"><span data-stu-id="64efe-113">This object is equivalent to a <xref:System.Type> object in managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64efe-114">备注</span><span class="sxs-lookup"><span data-stu-id="64efe-114">Remarks</span></span>  
 <span data-ttu-id="64efe-115">如果此类是非泛型的也就是说，如果它没有任何类型参数，`GetParameterizedType`只需获取对应于类的运行时类型对象。</span><span class="sxs-lookup"><span data-stu-id="64efe-115">If the class is non-generic, that is, if it has no type parameters, `GetParameterizedType` simply gets the runtime type object corresponding to the class.</span></span> <span data-ttu-id="64efe-116">`elementType`参数应设置为类的正确的元素类型： ELEMENT_TYPE_VALUETYPE 如果此类是值类型; 否则为 ELEMENT_TYPE_CLASS。</span><span class="sxs-lookup"><span data-stu-id="64efe-116">The `elementType` parameter should be set to the correct element type for the class: ELEMENT_TYPE_VALUETYPE if the class is a value type; otherwise, ELEMENT_TYPE_CLASS.</span></span>  
  
 <span data-ttu-id="64efe-117">如果类接受类型参数 (例如， `ArrayList<T>`)，你可以使用`GetParameterizedType`如构造实例化类型的类型对象`ArrayList<int>`。</span><span class="sxs-lookup"><span data-stu-id="64efe-117">If the class accepts type parameters (for example, `ArrayList<T>`), you can use `GetParameterizedType` to construct a type object for an instantiated type such as `ArrayList<int>`.</span></span>  
  
## <a name="background-information"></a><span data-ttu-id="64efe-118">背景信息</span><span class="sxs-lookup"><span data-stu-id="64efe-118">Background Information</span></span>  
 <span data-ttu-id="64efe-119">在.NET framework 1.0 和 1.1 版中，每种类型的元数据中无法直接映射到正在运行的进程中的类型。</span><span class="sxs-lookup"><span data-stu-id="64efe-119">In the .NET Framework versions 1.0 and 1.1, every type in the metadata could be directly mapped to a type in the running process.</span></span> <span data-ttu-id="64efe-120">因此，元数据类型和运行时类型也应正在运行的进程中有一种表示形式。</span><span class="sxs-lookup"><span data-stu-id="64efe-120">Thus, a metadata type and a runtime type had a single representation in the running process.</span></span> <span data-ttu-id="64efe-121">但是，在元数据中的一个泛型类型可以映射到的正在运行的进程中的类型的多个不同实例化。</span><span class="sxs-lookup"><span data-stu-id="64efe-121">However, one generic type in metadata can be mapped to many different instantiations of the type in the running process.</span></span> <span data-ttu-id="64efe-122">例如，元数据类型`SortedList<K,V>`可以将映射到`SortedList<String, EmployeeRecord>`， `SortedList<Int32, String>`， `SortedList<String,Array<Int32>>`，依次类推。</span><span class="sxs-lookup"><span data-stu-id="64efe-122">For example, the metadata type `SortedList<K,V>` can map to `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`, and so on.</span></span> <span data-ttu-id="64efe-123">因此，你需要处理类型实例化的方法。</span><span class="sxs-lookup"><span data-stu-id="64efe-123">Thus, you need a way to handle type instantiation.</span></span>  
  
 <span data-ttu-id="64efe-124">.NET Framework 2.0 版引入了`ICorDebugType`接口。</span><span class="sxs-lookup"><span data-stu-id="64efe-124">The .NET Framework version 2.0 introduces the `ICorDebugType` interface.</span></span> <span data-ttu-id="64efe-125">对于泛型类型，`ICorDebugClass`或`ICorDebugClass2`对象表示未实例化的类型 (`SortedList<K,V>`)，和`ICorDebugType`对象表示的各种实例化的类型。</span><span class="sxs-lookup"><span data-stu-id="64efe-125">For a generic type, an `ICorDebugClass` or `ICorDebugClass2` object represents the uninstantiated type (`SortedList<K,V>`), and an `ICorDebugType` object represents the various instantiated types.</span></span> <span data-ttu-id="64efe-126">给定`ICorDebugClass`或`ICorDebugClass2`对象，你可以创建`ICorDebugType`通过调用任何实例化的对象`ICorDebugClass2::GetParameterizedType`方法。</span><span class="sxs-lookup"><span data-stu-id="64efe-126">Given an `ICorDebugClass` or `ICorDebugClass2` object, you can create an `ICorDebugType` object for any instantiation by calling the `ICorDebugClass2::GetParameterizedType` method.</span></span> <span data-ttu-id="64efe-127">你还可以创建`ICorDebugType`简单类型，如 Int32，或非泛型类型的对象。</span><span class="sxs-lookup"><span data-stu-id="64efe-127">You can also create an `ICorDebugType` object for a simple type, such as Int32, or for a non-generic type.</span></span>  
  
 <span data-ttu-id="64efe-128">引入`ICorDebugType`对象来表示一种类型的运行时概念产生连锁反应在整个 API。</span><span class="sxs-lookup"><span data-stu-id="64efe-128">The introduction of the `ICorDebugType` object to represent the run-time notion of a type has a ripple effect throughout the API.</span></span> <span data-ttu-id="64efe-129">以前所用的函数`ICorDebugClass`或`ICorDebugClass2`对象或者甚至`CorElementType`值现在普遍采用`ICorDebugType`对象。</span><span class="sxs-lookup"><span data-stu-id="64efe-129">Functions that previously took an `ICorDebugClass` or `ICorDebugClass2` object or even a `CorElementType` value are generalized to take an `ICorDebugType` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64efe-130">惠?</span><span class="sxs-lookup"><span data-stu-id="64efe-130">Requirements</span></span>  
 <span data-ttu-id="64efe-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="64efe-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64efe-132">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64efe-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64efe-133">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64efe-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64efe-134">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64efe-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
