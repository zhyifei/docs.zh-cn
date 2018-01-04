---
title: "ICorDebugVariableHome::GetLocationType 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetLocationType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ec44705f75959dce893932789b026504d65a3105
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="49baa-102">ICorDebugVariableHome::GetLocationType 方法</span><span class="sxs-lookup"><span data-stu-id="49baa-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="49baa-103">获取变量的本机位置的类型。</span><span class="sxs-lookup"><span data-stu-id="49baa-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49baa-104">语法</span><span class="sxs-lookup"><span data-stu-id="49baa-104">Syntax</span></span>  
  
```  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49baa-105">参数</span><span class="sxs-lookup"><span data-stu-id="49baa-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="49baa-106">[out]指向的变量的本机位置的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="49baa-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="49baa-107">请参阅[VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)枚举有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="49baa-107">See the [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49baa-108">惠?</span><span class="sxs-lookup"><span data-stu-id="49baa-108">Requirements</span></span>  
 <span data-ttu-id="49baa-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="49baa-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49baa-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49baa-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49baa-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49baa-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49baa-112">**.NET framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49baa-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49baa-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="49baa-113">See Also</span></span>  
 [<span data-ttu-id="49baa-114">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="49baa-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 [<span data-ttu-id="49baa-115">VariableLocationType 枚举</span><span class="sxs-lookup"><span data-stu-id="49baa-115">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
