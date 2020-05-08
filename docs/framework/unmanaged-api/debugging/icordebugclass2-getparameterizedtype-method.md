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
ms.openlocfilehash: 329bcee441b395982a8a8b539c0a938fa8170b14
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894061"
---
# <a name="icordebugclass2getparameterizedtype-method"></a><span data-ttu-id="43870-102">ICorDebugClass2::GetParameterizedType 方法</span><span class="sxs-lookup"><span data-stu-id="43870-102">ICorDebugClass2::GetParameterizedType Method</span></span>
<span data-ttu-id="43870-103">获取此类的类型声明。</span><span class="sxs-lookup"><span data-stu-id="43870-103">Gets the type declaration for this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43870-104">语法</span><span class="sxs-lookup"><span data-stu-id="43870-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43870-105">参数</span><span class="sxs-lookup"><span data-stu-id="43870-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="43870-106">中为此类指定元素类型的 CorElementType 枚举的值：如果此 ICorDebugClass2 表示值类型，请将此值设置为 ELEMENT_TYPE_VALUETYPE。</span><span class="sxs-lookup"><span data-stu-id="43870-106">[in] A value of the CorElementType enumeration that specifies the element type for this class: Set this value to ELEMENT_TYPE_VALUETYPE if this ICorDebugClass2 represents a value type.</span></span> <span data-ttu-id="43870-107">如果此`ICorDebugClass2`表示复杂类型，则将此值设置为 ELEMENT_TYPE_CLASS。</span><span class="sxs-lookup"><span data-stu-id="43870-107">Set this value to ELEMENT_TYPE_CLASS if this `ICorDebugClass2` represents a complex type.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="43870-108">中如果类型为泛型，则为类型参数的数目。</span><span class="sxs-lookup"><span data-stu-id="43870-108">[in] The number of type parameters, if the type is generic.</span></span> <span data-ttu-id="43870-109">类型参数（如果有）的数目必须与类所需的数字匹配。</span><span class="sxs-lookup"><span data-stu-id="43870-109">The number of type parameters (if any) must match the number required by the class.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="43870-110">中指针的数组，其中每个都指向表示类型参数的 ICorDebugType 对象。</span><span class="sxs-lookup"><span data-stu-id="43870-110">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type parameter.</span></span> <span data-ttu-id="43870-111">如果类为非泛型类，则此值为 null。</span><span class="sxs-lookup"><span data-stu-id="43870-111">If the class is non-generic, this value is null.</span></span>  
  
 `ppType`  
 <span data-ttu-id="43870-112">弄指向表示类型声明的`ICorDebugType`对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="43870-112">[out] A pointer to the address of an `ICorDebugType` object that represents the type declaration.</span></span> <span data-ttu-id="43870-113">此对象等效于托管代码<xref:System.Type>中的对象。</span><span class="sxs-lookup"><span data-stu-id="43870-113">This object is equivalent to a <xref:System.Type> object in managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43870-114">备注</span><span class="sxs-lookup"><span data-stu-id="43870-114">Remarks</span></span>  
 <span data-ttu-id="43870-115">如果类是非泛型类（即，如果它没有类型参数）， `GetParameterizedType`只需获取与类相对应的运行时类型对象。</span><span class="sxs-lookup"><span data-stu-id="43870-115">If the class is non-generic, that is, if it has no type parameters, `GetParameterizedType` simply gets the runtime type object corresponding to the class.</span></span> <span data-ttu-id="43870-116">如果`elementType`类是值类型，则应将参数设置为类的正确元素类型： ELEMENT_TYPE_VALUETYPE。否则，ELEMENT_TYPE_CLASS。</span><span class="sxs-lookup"><span data-stu-id="43870-116">The `elementType` parameter should be set to the correct element type for the class: ELEMENT_TYPE_VALUETYPE if the class is a value type; otherwise, ELEMENT_TYPE_CLASS.</span></span>  
  
 <span data-ttu-id="43870-117">如果类接受类型参数（例如`ArrayList<T>`），则可以使用`GetParameterizedType`为实例化的类型（如）构造类型对象。 `ArrayList<int>`</span><span class="sxs-lookup"><span data-stu-id="43870-117">If the class accepts type parameters (for example, `ArrayList<T>`), you can use `GetParameterizedType` to construct a type object for an instantiated type such as `ArrayList<int>`.</span></span>  
  
## <a name="background-information"></a><span data-ttu-id="43870-118">背景信息</span><span class="sxs-lookup"><span data-stu-id="43870-118">Background Information</span></span>  
 <span data-ttu-id="43870-119">在 .NET Framework 版本1.0 和1.1 中，元数据中的每个类型都可以直接映射到正在运行的进程中的类型。</span><span class="sxs-lookup"><span data-stu-id="43870-119">In the .NET Framework versions 1.0 and 1.1, every type in the metadata could be directly mapped to a type in the running process.</span></span> <span data-ttu-id="43870-120">因此，元数据类型和运行时类型在正在运行的进程中具有单个表示形式。</span><span class="sxs-lookup"><span data-stu-id="43870-120">Thus, a metadata type and a runtime type had a single representation in the running process.</span></span> <span data-ttu-id="43870-121">但是，元数据中的一种泛型类型可以映射到正在运行的进程中类型的许多不同的实例化。</span><span class="sxs-lookup"><span data-stu-id="43870-121">However, one generic type in metadata can be mapped to many different instantiations of the type in the running process.</span></span> <span data-ttu-id="43870-122">`SortedList<K,V>`例如，元数据类型可以映射到`SortedList<String, EmployeeRecord>`、 `SortedList<Int32, String>` `SortedList<String,Array<Int32>>`、等。</span><span class="sxs-lookup"><span data-stu-id="43870-122">For example, the metadata type `SortedList<K,V>` can map to `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`, and so on.</span></span> <span data-ttu-id="43870-123">因此，您需要一种方法来处理类型实例化。</span><span class="sxs-lookup"><span data-stu-id="43870-123">Thus, you need a way to handle type instantiation.</span></span>  
  
 <span data-ttu-id="43870-124">.NET Framework 版本2.0 引入了`ICorDebugType`接口。</span><span class="sxs-lookup"><span data-stu-id="43870-124">The .NET Framework version 2.0 introduces the `ICorDebugType` interface.</span></span> <span data-ttu-id="43870-125">对于泛型类型`ICorDebugClass` ，或`ICorDebugClass2`对象表示未实例化的类型（`SortedList<K,V>`），而`ICorDebugType`对象表示各种实例化的类型。</span><span class="sxs-lookup"><span data-stu-id="43870-125">For a generic type, an `ICorDebugClass` or `ICorDebugClass2` object represents the uninstantiated type (`SortedList<K,V>`), and an `ICorDebugType` object represents the various instantiated types.</span></span> <span data-ttu-id="43870-126">给定`ICorDebugClass`或`ICorDebugClass2`对象，可以通过调用`ICorDebugType` `ICorDebugClass2::GetParameterizedType`方法为任何实例化创建对象。</span><span class="sxs-lookup"><span data-stu-id="43870-126">Given an `ICorDebugClass` or `ICorDebugClass2` object, you can create an `ICorDebugType` object for any instantiation by calling the `ICorDebugClass2::GetParameterizedType` method.</span></span> <span data-ttu-id="43870-127">还可以为简单类型`ICorDebugType` （如 Int32）或非泛型类型创建对象。</span><span class="sxs-lookup"><span data-stu-id="43870-127">You can also create an `ICorDebugType` object for a simple type, such as Int32, or for a non-generic type.</span></span>  
  
 <span data-ttu-id="43870-128">引入`ICorDebugType`对象来表示类型的运行时概念会在整个 API 中产生波纹效果。</span><span class="sxs-lookup"><span data-stu-id="43870-128">The introduction of the `ICorDebugType` object to represent the run-time notion of a type has a ripple effect throughout the API.</span></span> <span data-ttu-id="43870-129">`ICorDebugClass`以前用过`ICorDebugClass2`或对象甚至`CorElementType`值的函数被通用化为采用`ICorDebugType`对象。</span><span class="sxs-lookup"><span data-stu-id="43870-129">Functions that previously took an `ICorDebugClass` or `ICorDebugClass2` object or even a `CorElementType` value are generalized to take an `ICorDebugType` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43870-130">要求</span><span class="sxs-lookup"><span data-stu-id="43870-130">Requirements</span></span>  
 <span data-ttu-id="43870-131">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="43870-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43870-132">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43870-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43870-133">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43870-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43870-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43870-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
