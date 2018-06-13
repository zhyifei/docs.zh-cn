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
ms.openlocfilehash: e06c98067fea9368ac8f750d9187636d2ca9a8c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420103"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="8edec-102">ICorDebugVariableHome::GetRegister 方法</span><span class="sxs-lookup"><span data-stu-id="8edec-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="8edec-103">获取包含的位置类型的变量的寄存器`VLT_REGISTER`，和的变量的位置类型的基寄存器`VLT_REGISTER_RELATIVE`。</span><span class="sxs-lookup"><span data-stu-id="8edec-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8edec-104">语法</span><span class="sxs-lookup"><span data-stu-id="8edec-104">Syntax</span></span>  
  
```  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8edec-105">参数</span><span class="sxs-lookup"><span data-stu-id="8edec-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="8edec-106">[out]CorDebugRegister 枚举值，该值指示与位置类型的变量的寄存器`VLT_REGISTER`，和的变量的位置类型的基寄存器`VLT_REGISTER_RELATIVE`。</span><span class="sxs-lookup"><span data-stu-id="8edec-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8edec-107">返回值</span><span class="sxs-lookup"><span data-stu-id="8edec-107">Return Value</span></span>  
 <span data-ttu-id="8edec-108">该方法返回以下值：</span><span class="sxs-lookup"><span data-stu-id="8edec-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="8edec-109">值</span><span class="sxs-lookup"><span data-stu-id="8edec-109">Value</span></span>|<span data-ttu-id="8edec-110">描述</span><span class="sxs-lookup"><span data-stu-id="8edec-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="8edec-111">变量是在由寄存器中`pRegister`自变量。</span><span class="sxs-lookup"><span data-stu-id="8edec-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="8edec-112">该变量不是在注册或注册相对位置。</span><span class="sxs-lookup"><span data-stu-id="8edec-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8edec-113">要求</span><span class="sxs-lookup"><span data-stu-id="8edec-113">Requirements</span></span>  
 <span data-ttu-id="8edec-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8edec-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8edec-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8edec-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8edec-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8edec-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8edec-117">**.NET framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8edec-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8edec-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="8edec-118">See Also</span></span>  
 [<span data-ttu-id="8edec-119">VariableLocationType 枚举</span><span class="sxs-lookup"><span data-stu-id="8edec-119">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 [<span data-ttu-id="8edec-120">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="8edec-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
