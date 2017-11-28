---
title: "ICorDebugType::GetClass 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: be9999cd0dd8db5439dd41e51429841666597b16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="19881-102">ICorDebugType::GetClass 方法</span><span class="sxs-lookup"><span data-stu-id="19881-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="19881-103">获取表示未实例化泛型类型 ICorDebugClass 接口指针。</span><span class="sxs-lookup"><span data-stu-id="19881-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19881-104">语法</span><span class="sxs-lookup"><span data-stu-id="19881-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="19881-105">参数</span><span class="sxs-lookup"><span data-stu-id="19881-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="19881-106">[out]指向的地址的指针`ICorDebugClass`表示未实例化泛型类型的接口。</span><span class="sxs-lookup"><span data-stu-id="19881-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19881-107">备注</span><span class="sxs-lookup"><span data-stu-id="19881-107">Remarks</span></span>  
 <span data-ttu-id="19881-108">`GetClass`可以仅在某些情况下调用。</span><span class="sxs-lookup"><span data-stu-id="19881-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="19881-109">调用[icordebugtype:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)之前调用`GetClass`。</span><span class="sxs-lookup"><span data-stu-id="19881-109">Call [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="19881-110">如果`ICorDebugType::GetType`返回 ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE，CorElementType 值`GetClass`可以调用来获取泛型类型实例化的类型。</span><span class="sxs-lookup"><span data-stu-id="19881-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19881-111">要求</span><span class="sxs-lookup"><span data-stu-id="19881-111">Requirements</span></span>  
 <span data-ttu-id="19881-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="19881-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19881-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19881-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19881-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19881-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19881-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19881-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
