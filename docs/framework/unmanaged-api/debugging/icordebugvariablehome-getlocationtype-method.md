---
title: ICorDebugVariableHome::GetLocationType 方法
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ba0387b84f8d32831b79dd6c361bcdbb78f8bbba
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499474"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="9351b-102">ICorDebugVariableHome::GetLocationType 方法</span><span class="sxs-lookup"><span data-stu-id="9351b-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="9351b-103">获取变量的本机位置的类型。</span><span class="sxs-lookup"><span data-stu-id="9351b-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9351b-104">语法</span><span class="sxs-lookup"><span data-stu-id="9351b-104">Syntax</span></span>  
  
```  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9351b-105">参数</span><span class="sxs-lookup"><span data-stu-id="9351b-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="9351b-106">[out]指向的变量的本机位置的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="9351b-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="9351b-107">请参阅[VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)枚举的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9351b-107">See the [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9351b-108">要求</span><span class="sxs-lookup"><span data-stu-id="9351b-108">Requirements</span></span>  
 <span data-ttu-id="9351b-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9351b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9351b-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9351b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9351b-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9351b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9351b-112">**.NET Framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9351b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9351b-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="9351b-113">See also</span></span>
- [<span data-ttu-id="9351b-114">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="9351b-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
- [<span data-ttu-id="9351b-115">VariableLocationType 枚举</span><span class="sxs-lookup"><span data-stu-id="9351b-115">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
