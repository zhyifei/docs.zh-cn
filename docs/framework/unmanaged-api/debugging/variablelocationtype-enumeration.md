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
ms.openlocfilehash: 455fd06dbdbfd5d9753f3d7270647a742751d804
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420651"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="d3829-102">VariableLocationType 枚举</span><span class="sxs-lookup"><span data-stu-id="d3829-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="d3829-103">指示变量的本机位置类型。</span><span class="sxs-lookup"><span data-stu-id="d3829-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3829-104">语法</span><span class="sxs-lookup"><span data-stu-id="d3829-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="d3829-105">成员</span><span class="sxs-lookup"><span data-stu-id="d3829-105">Members</span></span>  
  
|<span data-ttu-id="d3829-106">成员</span><span class="sxs-lookup"><span data-stu-id="d3829-106">Member</span></span>|<span data-ttu-id="d3829-107">描述</span><span class="sxs-lookup"><span data-stu-id="d3829-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="d3829-108">变量在寄存器中。</span><span class="sxs-lookup"><span data-stu-id="d3829-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="d3829-109">变量在寄存器相对内存位置。</span><span class="sxs-lookup"><span data-stu-id="d3829-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="d3829-110">变量不存储在寄存器或寄存器相对内存位置中。</span><span class="sxs-lookup"><span data-stu-id="d3829-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3829-111">备注</span><span class="sxs-lookup"><span data-stu-id="d3829-111">Remarks</span></span>  
 <span data-ttu-id="d3829-112">枚举的成员 `VariableLocationType` 由[ICorDebugVariableHome：： GetLocationType](icordebugvariablehome-getlocationtype-method.md)方法返回。</span><span class="sxs-lookup"><span data-stu-id="d3829-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3829-113">要求</span><span class="sxs-lookup"><span data-stu-id="d3829-113">Requirements</span></span>  
 <span data-ttu-id="d3829-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d3829-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3829-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3829-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3829-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3829-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3829-117">**.NET Framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3829-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3829-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3829-118">See also</span></span>

- [<span data-ttu-id="d3829-119">调试枚举</span><span class="sxs-lookup"><span data-stu-id="d3829-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
