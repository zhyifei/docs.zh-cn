---
title: ICorDebugClass2::GetParameterizedType 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e1734ca91fd48cc15b8dbf25f11518ed0455b6f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475627"
---
# <a name="icordebugclass2getparameterizedtype-method"></a><span data-ttu-id="4935e-102">ICorDebugClass2::GetParameterizedType 方法</span><span class="sxs-lookup"><span data-stu-id="4935e-102">ICorDebugClass2::GetParameterizedType Method</span></span>
<span data-ttu-id="4935e-103">获取此类的类型声明。</span><span class="sxs-lookup"><span data-stu-id="4935e-103">Gets the type declaration for this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4935e-104">语法</span><span class="sxs-lookup"><span data-stu-id="4935e-104">Syntax</span></span>  
  
```  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4935e-105">参数</span><span class="sxs-lookup"><span data-stu-id="4935e-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="4935e-106">[in]CorElementType 枚举，用于指定此类的元素类型的值：如果此 ICorDebugClass2 表示值类型，请将此值设置为 ELEMENT_TYPE_VALUETYPE。</span><span class="sxs-lookup"><span data-stu-id="4935e-106">[in] A value of the CorElementType enumeration that specifies the element type for this class: Set this value to ELEMENT_TYPE_VALUETYPE if this ICorDebugClass2 represents a value type.</span></span> <span data-ttu-id="4935e-107">将此值设置为 ELEMENT_TYPE_CLASS，如果此`ICorDebugClass2`表示复杂类型。</span><span class="sxs-lookup"><span data-stu-id="4935e-107">Set this value to ELEMENT_TYPE_CLASS if this `ICorDebugClass2` represents a complex type.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="4935e-108">[in]类型参数，如果类型是泛型的数目。</span><span class="sxs-lookup"><span data-stu-id="4935e-108">[in] The number of type parameters, if the type is generic.</span></span> <span data-ttu-id="4935e-109">类型参数 （如果有） 的数目必须与类所需的数量匹配。</span><span class="sxs-lookup"><span data-stu-id="4935e-109">The number of type parameters (if any) must match the number required by the class.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="4935e-110">[in]一个指针数组，其中每个指向对象的表示的类型参数。</span><span class="sxs-lookup"><span data-stu-id="4935e-110">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type parameter.</span></span> <span data-ttu-id="4935e-111">如果非泛型类，此值为 null。</span><span class="sxs-lookup"><span data-stu-id="4935e-111">If the class is non-generic, this value is null.</span></span>  
  
 `ppType`  
 <span data-ttu-id="4935e-112">[out]指向的地址的指针`ICorDebugType`表示类型声明的对象。</span><span class="sxs-lookup"><span data-stu-id="4935e-112">[out] A pointer to the address of an `ICorDebugType` object that represents the type declaration.</span></span> <span data-ttu-id="4935e-113">此对象是否等效于<xref:System.Type>在托管代码中的对象。</span><span class="sxs-lookup"><span data-stu-id="4935e-113">This object is equivalent to a <xref:System.Type> object in managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4935e-114">备注</span><span class="sxs-lookup"><span data-stu-id="4935e-114">Remarks</span></span>  
 <span data-ttu-id="4935e-115">如果此类是非泛型的也就是说，如果它没有类型参数，`GetParameterizedType`只是获取对应于类的运行时类型对象。</span><span class="sxs-lookup"><span data-stu-id="4935e-115">If the class is non-generic, that is, if it has no type parameters, `GetParameterizedType` simply gets the runtime type object corresponding to the class.</span></span> <span data-ttu-id="4935e-116">`elementType`参数应设置为正确的元素类型的类：如果此类是值类型，则，ELEMENT_TYPE_VALUETYPE否则为 ELEMENT_TYPE_CLASS。</span><span class="sxs-lookup"><span data-stu-id="4935e-116">The `elementType` parameter should be set to the correct element type for the class: ELEMENT_TYPE_VALUETYPE if the class is a value type; otherwise, ELEMENT_TYPE_CLASS.</span></span>  
  
 <span data-ttu-id="4935e-117">如果类接受类型参数 (例如， `ArrayList<T>`)，可以使用`GetParameterizedType`如构造实例化类型的类型对象`ArrayList<int>`。</span><span class="sxs-lookup"><span data-stu-id="4935e-117">If the class accepts type parameters (for example, `ArrayList<T>`), you can use `GetParameterizedType` to construct a type object for an instantiated type such as `ArrayList<int>`.</span></span>  
  
## <a name="background-information"></a><span data-ttu-id="4935e-118">背景信息</span><span class="sxs-lookup"><span data-stu-id="4935e-118">Background Information</span></span>  
 <span data-ttu-id="4935e-119">在.NET framework 1.0 和 1.1 版中，每种类型的元数据中无法直接映射到正在运行的进程中的类型。</span><span class="sxs-lookup"><span data-stu-id="4935e-119">In the .NET Framework versions 1.0 and 1.1, every type in the metadata could be directly mapped to a type in the running process.</span></span> <span data-ttu-id="4935e-120">因此，元数据类型和运行时类型也应正在运行的进程中有一种表示形式。</span><span class="sxs-lookup"><span data-stu-id="4935e-120">Thus, a metadata type and a runtime type had a single representation in the running process.</span></span> <span data-ttu-id="4935e-121">但是，在元数据中的一种泛型类型可以映射到的正在运行的进程中的类型的多个不同实例化。</span><span class="sxs-lookup"><span data-stu-id="4935e-121">However, one generic type in metadata can be mapped to many different instantiations of the type in the running process.</span></span> <span data-ttu-id="4935e-122">例如，元数据类型`SortedList<K,V>`可以将映射到`SortedList<String, EmployeeRecord>`， `SortedList<Int32, String>`， `SortedList<String,Array<Int32>>`，依次类推。</span><span class="sxs-lookup"><span data-stu-id="4935e-122">For example, the metadata type `SortedList<K,V>` can map to `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`, and so on.</span></span> <span data-ttu-id="4935e-123">因此，您需要一种方法来处理类型实例化。</span><span class="sxs-lookup"><span data-stu-id="4935e-123">Thus, you need a way to handle type instantiation.</span></span>  
  
 <span data-ttu-id="4935e-124">.NET Framework 2.0 版引入了`ICorDebugType`接口。</span><span class="sxs-lookup"><span data-stu-id="4935e-124">The .NET Framework version 2.0 introduces the `ICorDebugType` interface.</span></span> <span data-ttu-id="4935e-125">泛型类型`ICorDebugClass`或`ICorDebugClass2`对象表示未实例化的类型 (`SortedList<K,V>`)，和一个`ICorDebugType`对象表示的各种实例化的类型。</span><span class="sxs-lookup"><span data-stu-id="4935e-125">For a generic type, an `ICorDebugClass` or `ICorDebugClass2` object represents the uninstantiated type (`SortedList<K,V>`), and an `ICorDebugType` object represents the various instantiated types.</span></span> <span data-ttu-id="4935e-126">给定`ICorDebugClass`或`ICorDebugClass2`对象，可以创建`ICorDebugType`对象通过调用任何实例化`ICorDebugClass2::GetParameterizedType`方法。</span><span class="sxs-lookup"><span data-stu-id="4935e-126">Given an `ICorDebugClass` or `ICorDebugClass2` object, you can create an `ICorDebugType` object for any instantiation by calling the `ICorDebugClass2::GetParameterizedType` method.</span></span> <span data-ttu-id="4935e-127">此外可以创建`ICorDebugType`简单类型，如 Int32，或非泛型类型的对象。</span><span class="sxs-lookup"><span data-stu-id="4935e-127">You can also create an `ICorDebugType` object for a simple type, such as Int32, or for a non-generic type.</span></span>  
  
 <span data-ttu-id="4935e-128">引入`ICorDebugType`对象来表示一种类型的运行时概念产生波纹效果在整个 API。</span><span class="sxs-lookup"><span data-stu-id="4935e-128">The introduction of the `ICorDebugType` object to represent the run-time notion of a type has a ripple effect throughout the API.</span></span> <span data-ttu-id="4935e-129">以前需要的函数`ICorDebugClass`或`ICorDebugClass2`对象或甚至`CorElementType`值现在普遍采用`ICorDebugType`对象。</span><span class="sxs-lookup"><span data-stu-id="4935e-129">Functions that previously took an `ICorDebugClass` or `ICorDebugClass2` object or even a `CorElementType` value are generalized to take an `ICorDebugType` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4935e-130">要求</span><span class="sxs-lookup"><span data-stu-id="4935e-130">Requirements</span></span>  
 <span data-ttu-id="4935e-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4935e-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4935e-132">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4935e-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4935e-133">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4935e-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4935e-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4935e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
