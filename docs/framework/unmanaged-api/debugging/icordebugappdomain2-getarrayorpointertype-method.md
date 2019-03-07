---
title: ICorDebugAppDomain2::GetArrayOrPointerType 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58a39771bd89fc9c4947f80a3c87b4d340b5461c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484233"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a><span data-ttu-id="eb81c-102">ICorDebugAppDomain2::GetArrayOrPointerType 方法</span><span class="sxs-lookup"><span data-stu-id="eb81c-102">ICorDebugAppDomain2::GetArrayOrPointerType Method</span></span>
<span data-ttu-id="eb81c-103">获取指定的类型或指针或引用为指定类型的数组。</span><span class="sxs-lookup"><span data-stu-id="eb81c-103">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb81c-104">语法</span><span class="sxs-lookup"><span data-stu-id="eb81c-104">Syntax</span></span>  
  
```  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb81c-105">参数</span><span class="sxs-lookup"><span data-stu-id="eb81c-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="eb81c-106">[in]CorElementType 枚举，用于指定基础本机类型 （数组、 指针或引用） 若要创建一个值。</span><span class="sxs-lookup"><span data-stu-id="eb81c-106">[in] A value of the CorElementType enumeration that specifies the underlying native type (an array, pointer, or reference) to be created.</span></span>  
  
 `nRank`  
 <span data-ttu-id="eb81c-107">[in]数组的秩 （即维数）。</span><span class="sxs-lookup"><span data-stu-id="eb81c-107">[in] The rank (that is, number of dimensions) of the array.</span></span> <span data-ttu-id="eb81c-108">此值必须为 0，如果`elementType`指定指针或引用类型。</span><span class="sxs-lookup"><span data-stu-id="eb81c-108">This value must be 0 if `elementType` specifies a pointer or reference type.</span></span>  
  
 `pTypeArg`  
 <span data-ttu-id="eb81c-109">[in]指向一个 ICorDebugType 对象，表示数组的类型、 指针或引用要创建。</span><span class="sxs-lookup"><span data-stu-id="eb81c-109">[in] A pointer to an ICorDebugType object that represents the type of array, pointer, or reference to be created.</span></span>  
  
 `ppType`  
 <span data-ttu-id="eb81c-110">[out]指向的地址的指针`ICorDebugType`表示构造的数组、 指针类型或引用的对象类型。</span><span class="sxs-lookup"><span data-stu-id="eb81c-110">[out] A pointer to the address of an `ICorDebugType` object that represents the constructed array, pointer type, or reference type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb81c-111">备注</span><span class="sxs-lookup"><span data-stu-id="eb81c-111">Remarks</span></span>  
 <span data-ttu-id="eb81c-112">值*elementType*必须是以下值之一：</span><span class="sxs-lookup"><span data-stu-id="eb81c-112">The value of *elementType* must be one of the following:</span></span>  
  
-   <span data-ttu-id="eb81c-113">ELEMENT_TYPE_PTR</span><span class="sxs-lookup"><span data-stu-id="eb81c-113">ELEMENT_TYPE_PTR</span></span>  
  
-   <span data-ttu-id="eb81c-114">ELEMENT_TYPE_BYREF</span><span class="sxs-lookup"><span data-stu-id="eb81c-114">ELEMENT_TYPE_BYREF</span></span>  
  
-   <span data-ttu-id="eb81c-115">ELEMENT_TYPE_ARRAY 或 ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="eb81c-115">ELEMENT_TYPE_ARRAY or ELEMENT_TYPE_SZARRAY</span></span>  
  
 <span data-ttu-id="eb81c-116">如果的值*elementType* ELEMENT_TYPE_PTR 或 ELEMENT_TYPE_BYREF， *nRank*必须为零。</span><span class="sxs-lookup"><span data-stu-id="eb81c-116">If the value of *elementType* is ELEMENT_TYPE_PTR or ELEMENT_TYPE_BYREF, *nRank* must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb81c-117">要求</span><span class="sxs-lookup"><span data-stu-id="eb81c-117">Requirements</span></span>  
 <span data-ttu-id="eb81c-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eb81c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb81c-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb81c-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb81c-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb81c-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb81c-121">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb81c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
