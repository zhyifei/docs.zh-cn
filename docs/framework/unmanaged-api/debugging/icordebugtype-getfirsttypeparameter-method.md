---
title: ICorDebugType::GetFirstTypeParameter 方法
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetFirstTypeParameter
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetFirstTypeParameter
helpviewer_keywords:
- ICorDebugType::GetFirstTypeParameter method [.NET Framework debugging]
- GetFirstTypeParameter method [.NET Framework debugging]
ms.assetid: 35bb594f-af6a-4349-83fe-e98702674e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4d872e4a65c0556dddac468336e6a42dd7d7923c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986981"
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a><span data-ttu-id="22621-102">ICorDebugType::GetFirstTypeParameter 方法</span><span class="sxs-lookup"><span data-stu-id="22621-102">ICorDebugType::GetFirstTypeParameter Method</span></span>
<span data-ttu-id="22621-103">获取的接口指针指向表示第一个 ICorDebugType<xref:System.Type>由此所表示的类型参数`ICorDebugType`。</span><span class="sxs-lookup"><span data-stu-id="22621-103">Gets an interface pointer to an ICorDebugType that represents the first <xref:System.Type> parameter of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22621-104">语法</span><span class="sxs-lookup"><span data-stu-id="22621-104">Syntax</span></span>  
  
```  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22621-105">参数</span><span class="sxs-lookup"><span data-stu-id="22621-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="22621-106">[out]指向的地址的指针`ICorDebugType`对象，表示第一个参数。</span><span class="sxs-lookup"><span data-stu-id="22621-106">[out] A pointer to the address of an `ICorDebugType` object that represents the first parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22621-107">备注</span><span class="sxs-lookup"><span data-stu-id="22621-107">Remarks</span></span>  
 <span data-ttu-id="22621-108">`GetFirstTypeParameter` 可以调用在类型有关的附加信息的涉及其中，最多的情况下一个类型参数。</span><span class="sxs-lookup"><span data-stu-id="22621-108">`GetFirstTypeParameter` can be called in cases where the additional information about the type involves, at most, one type parameter.</span></span> <span data-ttu-id="22621-109">具体而言，它可以用作类型 ELEMENT_TYPE_ARRAY、 ELEMENT_TYPE_SZARRAY、 ELEMENT_TYPE_BYREF 或 ELEMENT_TYPE_PTR，是否由[icordebugtype:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="22621-109">In particular, it can be used if the type is an ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22621-110">要求</span><span class="sxs-lookup"><span data-stu-id="22621-110">Requirements</span></span>  
 <span data-ttu-id="22621-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="22621-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22621-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22621-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22621-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22621-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22621-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22621-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
