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
ms.openlocfilehash: 1aa59ee559abff8006f0ac63a812e4315aa48154
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790313"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="882ca-102">VariableLocationType 枚举</span><span class="sxs-lookup"><span data-stu-id="882ca-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="882ca-103">指示变量的本机位置类型。</span><span class="sxs-lookup"><span data-stu-id="882ca-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="882ca-104">语法</span><span class="sxs-lookup"><span data-stu-id="882ca-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="882ca-105">Members</span><span class="sxs-lookup"><span data-stu-id="882ca-105">Members</span></span>  
  
|<span data-ttu-id="882ca-106">成员</span><span class="sxs-lookup"><span data-stu-id="882ca-106">Member</span></span>|<span data-ttu-id="882ca-107">描述</span><span class="sxs-lookup"><span data-stu-id="882ca-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="882ca-108">变量在寄存器中。</span><span class="sxs-lookup"><span data-stu-id="882ca-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="882ca-109">变量在寄存器相对内存位置。</span><span class="sxs-lookup"><span data-stu-id="882ca-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="882ca-110">变量不存储在寄存器或寄存器相对内存位置中。</span><span class="sxs-lookup"><span data-stu-id="882ca-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="882ca-111">备注</span><span class="sxs-lookup"><span data-stu-id="882ca-111">Remarks</span></span>  
 <span data-ttu-id="882ca-112">`VariableLocationType` 枚举的成员由[ICorDebugVariableHome：： GetLocationType](icordebugvariablehome-getlocationtype-method.md)方法返回。</span><span class="sxs-lookup"><span data-stu-id="882ca-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="882ca-113">需求</span><span class="sxs-lookup"><span data-stu-id="882ca-113">Requirements</span></span>  
 <span data-ttu-id="882ca-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="882ca-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="882ca-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="882ca-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="882ca-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="882ca-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="882ca-117">**.NET Framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="882ca-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="882ca-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="882ca-118">See also</span></span>

- [<span data-ttu-id="882ca-119">调试枚举</span><span class="sxs-lookup"><span data-stu-id="882ca-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
