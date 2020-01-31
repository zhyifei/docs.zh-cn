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
ms.openlocfilehash: 5d33c917ab814083ec2f3a3f3de6bdc264d90b77
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791009"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="4839d-102">ICorDebugVariableHome：： GetLocationType 方法</span><span class="sxs-lookup"><span data-stu-id="4839d-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="4839d-103">获取变量的本机位置的类型。</span><span class="sxs-lookup"><span data-stu-id="4839d-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4839d-104">语法</span><span class="sxs-lookup"><span data-stu-id="4839d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4839d-105">参数</span><span class="sxs-lookup"><span data-stu-id="4839d-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="4839d-106">弄指向变量的本机位置的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="4839d-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="4839d-107">有关详细信息，请参阅[VariableLocationType](variablelocationtype-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="4839d-107">See the [VariableLocationType](variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4839d-108">需求</span><span class="sxs-lookup"><span data-stu-id="4839d-108">Requirements</span></span>  
 <span data-ttu-id="4839d-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4839d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4839d-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4839d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4839d-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4839d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4839d-112">**.NET Framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4839d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4839d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4839d-113">See also</span></span>

- [<span data-ttu-id="4839d-114">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="4839d-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="4839d-115">VariableLocationType 枚举</span><span class="sxs-lookup"><span data-stu-id="4839d-115">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
