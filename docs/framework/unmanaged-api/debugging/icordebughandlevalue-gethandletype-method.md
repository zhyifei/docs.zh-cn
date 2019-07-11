---
title: ICorDebugHandleValue::GetHandleType 方法
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.GetHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::GetHandleType
helpviewer_keywords:
- GetHandleType method [.NET Framework debugging]
- ICorDebugHandleValue::GetHandleType method [.NET Framework debugging]
ms.assetid: d5e7b12d-835a-4e86-ae2f-d658d4f1c67c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0bc65cdeada059f6e9b41dc8eb4d7589a232143d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756823"
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="10829-102">ICorDebugHandleValue::GetHandleType 方法</span><span class="sxs-lookup"><span data-stu-id="10829-102">ICorDebugHandleValue::GetHandleType Method</span></span>
<span data-ttu-id="10829-103">获取一个值，该值指示此 ICorDebugHandleValue 对象引用的句柄的类型。</span><span class="sxs-lookup"><span data-stu-id="10829-103">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10829-104">语法</span><span class="sxs-lookup"><span data-stu-id="10829-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10829-105">参数</span><span class="sxs-lookup"><span data-stu-id="10829-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="10829-106">[out]CorDebugHandleType 枚举，该值指示此句柄类型的值指向的指针。</span><span class="sxs-lookup"><span data-stu-id="10829-106">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10829-107">要求</span><span class="sxs-lookup"><span data-stu-id="10829-107">Requirements</span></span>  
 <span data-ttu-id="10829-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="10829-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10829-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10829-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10829-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10829-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10829-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10829-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
