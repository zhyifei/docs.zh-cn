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
ms.openlocfilehash: 396dd9c017fca6dc7037b43355ba7f726d7390ea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790978"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="361e6-102">ICorDebugVariableHome：： GetRegister 方法</span><span class="sxs-lookup"><span data-stu-id="361e6-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="361e6-103">获取一个寄存器，其中包含位置类型为 `VLT_REGISTER`的变量，以及位置类型为 `VLT_REGISTER_RELATIVE`的变量的基寄存器。</span><span class="sxs-lookup"><span data-stu-id="361e6-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="361e6-104">语法</span><span class="sxs-lookup"><span data-stu-id="361e6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="361e6-105">参数</span><span class="sxs-lookup"><span data-stu-id="361e6-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="361e6-106">弄一个 CorDebugRegister 枚举值，该值指示注册位置类型为 `VLT_REGISTER`的变量，并使用 `VLT_REGISTER_RELATIVE`位置类型的变量的基寄存器。</span><span class="sxs-lookup"><span data-stu-id="361e6-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="361e6-107">返回值</span><span class="sxs-lookup"><span data-stu-id="361e6-107">Return Value</span></span>  
 <span data-ttu-id="361e6-108">方法返回以下值：</span><span class="sxs-lookup"><span data-stu-id="361e6-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="361e6-109">{2&gt;值&lt;2}</span><span class="sxs-lookup"><span data-stu-id="361e6-109">Value</span></span>|<span data-ttu-id="361e6-110">描述</span><span class="sxs-lookup"><span data-stu-id="361e6-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="361e6-111">变量位于 `pRegister` 参数所指示的寄存器中。</span><span class="sxs-lookup"><span data-stu-id="361e6-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="361e6-112">变量不在寄存器或寄存器相对位置中。</span><span class="sxs-lookup"><span data-stu-id="361e6-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="361e6-113">需求</span><span class="sxs-lookup"><span data-stu-id="361e6-113">Requirements</span></span>  
 <span data-ttu-id="361e6-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="361e6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="361e6-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="361e6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="361e6-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="361e6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="361e6-117">**.NET Framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="361e6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="361e6-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="361e6-118">See also</span></span>

- [<span data-ttu-id="361e6-119">VariableLocationType 枚举</span><span class="sxs-lookup"><span data-stu-id="361e6-119">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
- [<span data-ttu-id="361e6-120">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="361e6-120">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
