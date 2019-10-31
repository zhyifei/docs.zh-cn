---
title: ICorDebugVariableHome：： GetRegister 方法
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type:
- apiref
ms.openlocfilehash: 4c9932c3eeebd0101ee364c9b4d0b0a26862c4b1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125072"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="835bb-102">ICorDebugVariableHome：： GetRegister 方法</span><span class="sxs-lookup"><span data-stu-id="835bb-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="835bb-103">获取一个寄存器，其中包含位置类型为 `VLT_REGISTER`的变量，以及位置类型为 `VLT_REGISTER_RELATIVE`的变量的基寄存器。</span><span class="sxs-lookup"><span data-stu-id="835bb-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="835bb-104">语法</span><span class="sxs-lookup"><span data-stu-id="835bb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="835bb-105">参数</span><span class="sxs-lookup"><span data-stu-id="835bb-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="835bb-106">弄一个 CorDebugRegister 枚举值，该值指示注册位置类型为 `VLT_REGISTER`的变量，并使用 `VLT_REGISTER_RELATIVE`位置类型的变量的基寄存器。</span><span class="sxs-lookup"><span data-stu-id="835bb-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="835bb-107">返回值</span><span class="sxs-lookup"><span data-stu-id="835bb-107">Return Value</span></span>  
 <span data-ttu-id="835bb-108">方法返回以下值：</span><span class="sxs-lookup"><span data-stu-id="835bb-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="835bb-109">“值”</span><span class="sxs-lookup"><span data-stu-id="835bb-109">Value</span></span>|<span data-ttu-id="835bb-110">描述</span><span class="sxs-lookup"><span data-stu-id="835bb-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="835bb-111">变量位于 `pRegister` 参数所指示的寄存器中。</span><span class="sxs-lookup"><span data-stu-id="835bb-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="835bb-112">变量不在寄存器或寄存器相对位置中。</span><span class="sxs-lookup"><span data-stu-id="835bb-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="835bb-113">要求</span><span class="sxs-lookup"><span data-stu-id="835bb-113">Requirements</span></span>  
 <span data-ttu-id="835bb-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="835bb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="835bb-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="835bb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="835bb-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="835bb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="835bb-117">**.NET Framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="835bb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="835bb-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="835bb-118">See also</span></span>

- [<span data-ttu-id="835bb-119">VariableLocationType 枚举</span><span class="sxs-lookup"><span data-stu-id="835bb-119">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
- [<span data-ttu-id="835bb-120">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="835bb-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
