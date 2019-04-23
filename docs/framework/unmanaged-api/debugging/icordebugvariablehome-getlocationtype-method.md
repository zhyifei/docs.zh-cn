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
ms.openlocfilehash: af879cbbf8edfd05e79d9b77b0c1fb71b2c835c3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224294"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="8e17a-102">ICorDebugVariableHome::GetLocationType 方法</span><span class="sxs-lookup"><span data-stu-id="8e17a-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="8e17a-103">获取变量的本机位置的类型。</span><span class="sxs-lookup"><span data-stu-id="8e17a-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e17a-104">语法</span><span class="sxs-lookup"><span data-stu-id="8e17a-104">Syntax</span></span>  
  
```  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e17a-105">参数</span><span class="sxs-lookup"><span data-stu-id="8e17a-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="8e17a-106">[out]指向的变量的本机位置的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="8e17a-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="8e17a-107">请参阅[VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)枚举的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8e17a-107">See the [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e17a-108">要求</span><span class="sxs-lookup"><span data-stu-id="8e17a-108">Requirements</span></span>  
 <span data-ttu-id="8e17a-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8e17a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e17a-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e17a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e17a-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e17a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e17a-112">**.NET Framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e17a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e17a-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e17a-113">See also</span></span>

- [<span data-ttu-id="8e17a-114">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="8e17a-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
- [<span data-ttu-id="8e17a-115">VariableLocationType 枚举</span><span class="sxs-lookup"><span data-stu-id="8e17a-115">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
