---
title: ICorDebugType::GetClass 方法
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0915027ce6a3768ff854eafc5496c5057081cc4d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946206"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="d656b-102">ICorDebugType::GetClass 方法</span><span class="sxs-lookup"><span data-stu-id="d656b-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="d656b-103">获取表示未实例化泛型类型 ICorDebugClass 接口指针。</span><span class="sxs-lookup"><span data-stu-id="d656b-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d656b-104">语法</span><span class="sxs-lookup"><span data-stu-id="d656b-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d656b-105">参数</span><span class="sxs-lookup"><span data-stu-id="d656b-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="d656b-106">[out]指向的地址的指针`ICorDebugClass`表示未实例化泛型类型的接口。</span><span class="sxs-lookup"><span data-stu-id="d656b-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d656b-107">备注</span><span class="sxs-lookup"><span data-stu-id="d656b-107">Remarks</span></span>  
 <span data-ttu-id="d656b-108">`GetClass` 可以仅在某些情况下调用。</span><span class="sxs-lookup"><span data-stu-id="d656b-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="d656b-109">调用[icordebugtype:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)然后才能调用`GetClass`。</span><span class="sxs-lookup"><span data-stu-id="d656b-109">Call [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="d656b-110">如果`ICorDebugType::GetType`返回 ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE，CorElementType 值`GetClass`可以调用以获取泛型类型实例化的类型。</span><span class="sxs-lookup"><span data-stu-id="d656b-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d656b-111">要求</span><span class="sxs-lookup"><span data-stu-id="d656b-111">Requirements</span></span>  
 <span data-ttu-id="d656b-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d656b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d656b-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d656b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d656b-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d656b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d656b-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d656b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
