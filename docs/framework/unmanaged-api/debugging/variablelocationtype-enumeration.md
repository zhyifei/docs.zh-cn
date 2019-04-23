---
title: VariableLocationType 枚举
ms.date: 03/30/2017
api_name:
- VariableLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- VariableLocationType
helpviewer_keywords:
- VariableLocationType enumeration [.NET Framework debugging]
ms.assetid: 8635ee3a-c84b-4626-876c-416bee54f787
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 392254efcd099aca60e58b3cc0bc61ca85aa2c66
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099945"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="ffa13-102">VariableLocationType 枚举</span><span class="sxs-lookup"><span data-stu-id="ffa13-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="ffa13-103">指示变量的本机位置类型。</span><span class="sxs-lookup"><span data-stu-id="ffa13-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffa13-104">语法</span><span class="sxs-lookup"><span data-stu-id="ffa13-104">Syntax</span></span>  
  
```  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="ffa13-105">成员</span><span class="sxs-lookup"><span data-stu-id="ffa13-105">Members</span></span>  
  
|<span data-ttu-id="ffa13-106">成员</span><span class="sxs-lookup"><span data-stu-id="ffa13-106">Member</span></span>|<span data-ttu-id="ffa13-107">描述</span><span class="sxs-lookup"><span data-stu-id="ffa13-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="ffa13-108">该变量是在寄存器中。</span><span class="sxs-lookup"><span data-stu-id="ffa13-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="ffa13-109">该变量是在寄存器相对内存位置。</span><span class="sxs-lookup"><span data-stu-id="ffa13-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="ffa13-110">该变量不存储在寄存器或寄存器相对内存位置。</span><span class="sxs-lookup"><span data-stu-id="ffa13-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffa13-111">备注</span><span class="sxs-lookup"><span data-stu-id="ffa13-111">Remarks</span></span>  
 <span data-ttu-id="ffa13-112">成员`VariableLocationType`枚举返回的[ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ffa13-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffa13-113">要求</span><span class="sxs-lookup"><span data-stu-id="ffa13-113">Requirements</span></span>  
 <span data-ttu-id="ffa13-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ffa13-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffa13-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ffa13-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ffa13-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffa13-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffa13-117">**.NET Framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffa13-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffa13-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="ffa13-118">See also</span></span>

- [<span data-ttu-id="ffa13-119">调试枚举</span><span class="sxs-lookup"><span data-stu-id="ffa13-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
