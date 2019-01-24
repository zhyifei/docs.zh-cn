---
title: ICorDebugVariableHome::GetRegister 方法
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d678b6f52719287a1e8bbe88d178fa47b2893ca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563140"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="f372e-102">ICorDebugVariableHome::GetRegister 方法</span><span class="sxs-lookup"><span data-stu-id="f372e-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="f372e-103">获取包含的位置类型的变量的寄存器`VLT_REGISTER`，并与位置类型的变量的基寄存器`VLT_REGISTER_RELATIVE`。</span><span class="sxs-lookup"><span data-stu-id="f372e-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f372e-104">语法</span><span class="sxs-lookup"><span data-stu-id="f372e-104">Syntax</span></span>  
  
```  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f372e-105">参数</span><span class="sxs-lookup"><span data-stu-id="f372e-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="f372e-106">[out]CorDebugRegister 枚举值，该值指示的位置类型的变量的寄存器`VLT_REGISTER`，并与位置类型的变量的基寄存器`VLT_REGISTER_RELATIVE`。</span><span class="sxs-lookup"><span data-stu-id="f372e-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f372e-107">返回值</span><span class="sxs-lookup"><span data-stu-id="f372e-107">Return Value</span></span>  
 <span data-ttu-id="f372e-108">此方法返回以下值：</span><span class="sxs-lookup"><span data-stu-id="f372e-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="f372e-109">“值”</span><span class="sxs-lookup"><span data-stu-id="f372e-109">Value</span></span>|<span data-ttu-id="f372e-110">描述</span><span class="sxs-lookup"><span data-stu-id="f372e-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="f372e-111">该变量是由在寄存器中`pRegister`参数。</span><span class="sxs-lookup"><span data-stu-id="f372e-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="f372e-112">该变量不是在寄存器或寄存器相对位置。</span><span class="sxs-lookup"><span data-stu-id="f372e-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f372e-113">要求</span><span class="sxs-lookup"><span data-stu-id="f372e-113">Requirements</span></span>  
 <span data-ttu-id="f372e-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f372e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f372e-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f372e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f372e-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f372e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f372e-117">**.NET Framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f372e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f372e-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f372e-118">See also</span></span>
- [<span data-ttu-id="f372e-119">VariableLocationType 枚举</span><span class="sxs-lookup"><span data-stu-id="f372e-119">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
- [<span data-ttu-id="f372e-120">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="f372e-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
