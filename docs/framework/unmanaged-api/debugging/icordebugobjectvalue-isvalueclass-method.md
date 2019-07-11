---
title: ICorDebugObjectValue::IsValueClass 方法
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.IsValueClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::IsValueClass
helpviewer_keywords:
- ICorDebugObjectValue::IsValueClass method [.NET Framework debugging]
- IsValueClass method [.NET Framework debugging]
ms.assetid: 13d89a4a-5d9d-4a79-9600-5e2a98c3d166
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b08937182797c8e94048d734d65473fad21b85cc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766310"
---
# <a name="icordebugobjectvalueisvalueclass-method"></a><span data-ttu-id="9eea8-102">ICorDebugObjectValue::IsValueClass 方法</span><span class="sxs-lookup"><span data-stu-id="9eea8-102">ICorDebugObjectValue::IsValueClass Method</span></span>
<span data-ttu-id="9eea8-103">获取一个值，该值指示此对象值是否为值类型。</span><span class="sxs-lookup"><span data-stu-id="9eea8-103">Gets a value that indicates whether this object value is a value type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9eea8-104">语法</span><span class="sxs-lookup"><span data-stu-id="9eea8-104">Syntax</span></span>  
  
```cpp  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9eea8-105">参数</span><span class="sxs-lookup"><span data-stu-id="9eea8-105">Parameters</span></span>  
 `pbIsValueClass`  
 <span data-ttu-id="9eea8-106">[out]指向布尔值为`true`如果此"ICorDebugObjectValue"所表示的对象值是值类型，而不是引用类型; 否则为`pbIsValueClass`是`false`。</span><span class="sxs-lookup"><span data-stu-id="9eea8-106">[out] A pointer to a Boolean value that is `true` if the object value, represented by this "ICorDebugObjectValue", is a value type rather than a reference type; otherwise, `pbIsValueClass` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9eea8-107">要求</span><span class="sxs-lookup"><span data-stu-id="9eea8-107">Requirements</span></span>  
 <span data-ttu-id="9eea8-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9eea8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9eea8-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9eea8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9eea8-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9eea8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9eea8-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9eea8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eea8-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="9eea8-112">See also</span></span>
