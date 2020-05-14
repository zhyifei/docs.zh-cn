---
title: ICorDebugVariableHome：： GetLocationType 方法
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
ms.openlocfilehash: 8874deede8b46b93df0e298fb3970fa153b51415
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396564"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="cd11f-102">ICorDebugVariableHome：： GetLocationType 方法</span><span class="sxs-lookup"><span data-stu-id="cd11f-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="cd11f-103">获取变量的本机位置的类型。</span><span class="sxs-lookup"><span data-stu-id="cd11f-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd11f-104">语法</span><span class="sxs-lookup"><span data-stu-id="cd11f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd11f-105">参数</span><span class="sxs-lookup"><span data-stu-id="cd11f-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="cd11f-106">弄指向变量的本机位置的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="cd11f-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="cd11f-107">有关详细信息，请参阅[VariableLocationType](variablelocationtype-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="cd11f-107">See the [VariableLocationType](variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd11f-108">要求</span><span class="sxs-lookup"><span data-stu-id="cd11f-108">Requirements</span></span>  
 <span data-ttu-id="cd11f-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cd11f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd11f-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd11f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd11f-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd11f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd11f-112">**.NET Framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd11f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd11f-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd11f-113">See also</span></span>

- [<span data-ttu-id="cd11f-114">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="cd11f-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="cd11f-115">VariableLocationType 枚举</span><span class="sxs-lookup"><span data-stu-id="cd11f-115">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
