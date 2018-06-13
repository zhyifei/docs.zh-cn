---
title: ICorDebugType::GetType 方法
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d881a1fe3965b6e1d89e6172c887061434cd52ff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418713"
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="5a11f-102">ICorDebugType::GetType 方法</span><span class="sxs-lookup"><span data-stu-id="5a11f-102">ICorDebugType::GetType Method</span></span>
<span data-ttu-id="5a11f-103">获取一个 CorElementType 值，描述公共语言运行时 (CLR) 的本机类型<xref:System.Type>表示通过此 ICorDebugType。</span><span class="sxs-lookup"><span data-stu-id="5a11f-103">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a11f-104">语法</span><span class="sxs-lookup"><span data-stu-id="5a11f-104">Syntax</span></span>  
  
```  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a11f-105">参数</span><span class="sxs-lookup"><span data-stu-id="5a11f-105">Parameters</span></span>  
 `ty`  
 <span data-ttu-id="5a11f-106">[out]指向的值的指针`CorElementType`枚举，指示 CLR<xref:System.Type>此`ICorDebugType`表示。</span><span class="sxs-lookup"><span data-stu-id="5a11f-106">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a11f-107">备注</span><span class="sxs-lookup"><span data-stu-id="5a11f-107">Remarks</span></span>  
 <span data-ttu-id="5a11f-108">如果值`ty`ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE， [icordebugtype:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)方法可调用以获取泛型类型实例化的类型; 否则，不调用`ICorDebugType::GetClass`。</span><span class="sxs-lookup"><span data-stu-id="5a11f-108">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a11f-109">要求</span><span class="sxs-lookup"><span data-stu-id="5a11f-109">Requirements</span></span>  
 <span data-ttu-id="5a11f-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5a11f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a11f-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a11f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a11f-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a11f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a11f-113">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a11f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
