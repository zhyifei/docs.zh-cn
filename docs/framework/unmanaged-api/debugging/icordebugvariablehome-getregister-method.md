---
title: "ICorDebugVariableHome::GetRegister 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetRegister
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f16e4bfe4767e1b49d7dacf0481e8911a90e178
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="ca4b6-102">ICorDebugVariableHome::GetRegister 方法</span><span class="sxs-lookup"><span data-stu-id="ca4b6-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="ca4b6-103">获取包含的位置类型的变量的寄存器`VLT_REGISTER`，和的变量的位置类型的基寄存器`VLT_REGISTER_RELATIVE`。</span><span class="sxs-lookup"><span data-stu-id="ca4b6-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca4b6-104">语法</span><span class="sxs-lookup"><span data-stu-id="ca4b6-104">Syntax</span></span>  
  
```  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca4b6-105">参数</span><span class="sxs-lookup"><span data-stu-id="ca4b6-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="ca4b6-106">[out]CorDebugRegister 枚举值，该值指示与位置类型的变量的寄存器`VLT_REGISTER`，和的变量的位置类型的基寄存器`VLT_REGISTER_RELATIVE`。</span><span class="sxs-lookup"><span data-stu-id="ca4b6-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca4b6-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ca4b6-107">Return Value</span></span>  
 <span data-ttu-id="ca4b6-108">该方法返回以下值：</span><span class="sxs-lookup"><span data-stu-id="ca4b6-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="ca4b6-109">值</span><span class="sxs-lookup"><span data-stu-id="ca4b6-109">Value</span></span>|<span data-ttu-id="ca4b6-110">描述</span><span class="sxs-lookup"><span data-stu-id="ca4b6-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="ca4b6-111">变量是在由寄存器中`pRegister`自变量。</span><span class="sxs-lookup"><span data-stu-id="ca4b6-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="ca4b6-112">该变量不是在注册或注册相对位置。</span><span class="sxs-lookup"><span data-stu-id="ca4b6-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ca4b6-113">要求</span><span class="sxs-lookup"><span data-stu-id="ca4b6-113">Requirements</span></span>  
 <span data-ttu-id="ca4b6-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ca4b6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca4b6-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca4b6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca4b6-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca4b6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca4b6-117">**.NET framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca4b6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca4b6-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca4b6-118">See Also</span></span>  
 [<span data-ttu-id="ca4b6-119">VariableLocationType 枚举</span><span class="sxs-lookup"><span data-stu-id="ca4b6-119">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 [<span data-ttu-id="ca4b6-120">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="ca4b6-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
