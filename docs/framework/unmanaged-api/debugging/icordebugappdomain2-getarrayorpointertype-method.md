---
title: "ICorDebugAppDomain2::GetArrayOrPointerType 方法"
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
- ICorDebugAppDomain2.GetArrayOrPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetArrayOrPointerType
helpviewer_keywords:
- GetArrayOrPointerType method [.NET Framework debugging]
- ICorDebugAppDomain2::GetArrayOrPointerType method [.NET Framework debugging]
ms.assetid: 97e493f5-3a62-4ec7-b42f-4af57bf71f57
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6beb75638ccbf81149fd7fa1682acca3e7673dc8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a><span data-ttu-id="5fbd4-102">ICorDebugAppDomain2::GetArrayOrPointerType 方法</span><span class="sxs-lookup"><span data-stu-id="5fbd4-102">ICorDebugAppDomain2::GetArrayOrPointerType Method</span></span>
<span data-ttu-id="5fbd4-103">获取指定的类型、 指针或对指定的类型引用的数组。</span><span class="sxs-lookup"><span data-stu-id="5fbd4-103">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fbd4-104">语法</span><span class="sxs-lookup"><span data-stu-id="5fbd4-104">Syntax</span></span>  
  
```  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5fbd4-105">参数</span><span class="sxs-lookup"><span data-stu-id="5fbd4-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="5fbd4-106">[in]CorElementType 枚举，指定 （数组、 指针或引用） 要创建的基础本机类型的值。</span><span class="sxs-lookup"><span data-stu-id="5fbd4-106">[in] A value of the CorElementType enumeration that specifies the underlying native type (an array, pointer, or reference) to be created.</span></span>  
  
 `nRank`  
 <span data-ttu-id="5fbd4-107">[in]数组的秩 （也就是说，多个维度）。</span><span class="sxs-lookup"><span data-stu-id="5fbd4-107">[in] The rank (that is, number of dimensions) of the array.</span></span> <span data-ttu-id="5fbd4-108">此值必须为 0，如果`elementType`指定指针或引用类型。</span><span class="sxs-lookup"><span data-stu-id="5fbd4-108">This value must be 0 if `elementType` specifies a pointer or reference type.</span></span>  
  
 `pTypeArg`  
 <span data-ttu-id="5fbd4-109">[in]指针指向表示数组的类型的 ICorDebugType 对象、 指针或引用要创建。</span><span class="sxs-lookup"><span data-stu-id="5fbd4-109">[in] A pointer to an ICorDebugType object that represents the type of array, pointer, or reference to be created.</span></span>  
  
 `ppType`  
 <span data-ttu-id="5fbd4-110">[out]指向的地址的指针`ICorDebugType`对象表示构造的数组、 指针类型或引用类型。</span><span class="sxs-lookup"><span data-stu-id="5fbd4-110">[out] A pointer to the address of an `ICorDebugType` object that represents the constructed array, pointer type, or reference type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fbd4-111">备注</span><span class="sxs-lookup"><span data-stu-id="5fbd4-111">Remarks</span></span>  
 <span data-ttu-id="5fbd4-112">值*elementType*必须是以下之一：</span><span class="sxs-lookup"><span data-stu-id="5fbd4-112">The value of *elementType* must be one of the following:</span></span>  
  
-   <span data-ttu-id="5fbd4-113">ELEMENT_TYPE_PTR</span><span class="sxs-lookup"><span data-stu-id="5fbd4-113">ELEMENT_TYPE_PTR</span></span>  
  
-   <span data-ttu-id="5fbd4-114">ELEMENT_TYPE_BYREF</span><span class="sxs-lookup"><span data-stu-id="5fbd4-114">ELEMENT_TYPE_BYREF</span></span>  
  
-   <span data-ttu-id="5fbd4-115">ELEMENT_TYPE_ARRAY 或 ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="5fbd4-115">ELEMENT_TYPE_ARRAY or ELEMENT_TYPE_SZARRAY</span></span>  
  
 <span data-ttu-id="5fbd4-116">如果值*elementType* ELEMENT_TYPE_PTR 或 ELEMENT_TYPE_BYREF， *nRank*必须为零。</span><span class="sxs-lookup"><span data-stu-id="5fbd4-116">If the value of *elementType* is ELEMENT_TYPE_PTR or ELEMENT_TYPE_BYREF, *nRank* must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fbd4-117">惠?</span><span class="sxs-lookup"><span data-stu-id="5fbd4-117">Requirements</span></span>  
 <span data-ttu-id="5fbd4-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5fbd4-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fbd4-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fbd4-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fbd4-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fbd4-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fbd4-121">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fbd4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
