---
title: CorDebugIlToNativeMappingTypes 枚举
ms.date: 03/30/2017
api_name:
- CorDebugIlToNativeMappingTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIlToNativeMappingTypes
helpviewer_keywords:
- CorDebugIIToNativeMappingTypes enumeration [.NET Framework debugging]
ms.assetid: c35e2919-42c3-4ba0-ae28-443c35f66f93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c7d9f5373f2b4ea216ca517813b1334b9f5c38a6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739968"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="721d4-102">CorDebugIlToNativeMappingTypes 枚举</span><span class="sxs-lookup"><span data-stu-id="721d4-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="721d4-103">指示本机指令，COR_DEBUG_IL_TO_NATIVE_MAP 结构的实例所表示的特定范围是否与特殊的代码区域相符。</span><span class="sxs-lookup"><span data-stu-id="721d4-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="721d4-104">语法</span><span class="sxs-lookup"><span data-stu-id="721d4-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="721d4-105">成员</span><span class="sxs-lookup"><span data-stu-id="721d4-105">Members</span></span>  
  
|<span data-ttu-id="721d4-106">成员</span><span class="sxs-lookup"><span data-stu-id="721d4-106">Member</span></span>|<span data-ttu-id="721d4-107">描述</span><span class="sxs-lookup"><span data-stu-id="721d4-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="721d4-108">本机指令的范围不对应任何特殊的代码区域。</span><span class="sxs-lookup"><span data-stu-id="721d4-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="721d4-109">本机指令的范围对应于在 prolog。</span><span class="sxs-lookup"><span data-stu-id="721d4-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="721d4-110">本机指令的范围与 epilog 相对应。</span><span class="sxs-lookup"><span data-stu-id="721d4-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="721d4-111">要求</span><span class="sxs-lookup"><span data-stu-id="721d4-111">Requirements</span></span>  
 <span data-ttu-id="721d4-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="721d4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="721d4-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="721d4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="721d4-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="721d4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="721d4-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="721d4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="721d4-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="721d4-116">See also</span></span>

- [<span data-ttu-id="721d4-117">GetILToNativeMapping 方法</span><span class="sxs-lookup"><span data-stu-id="721d4-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="721d4-118">调试枚举</span><span class="sxs-lookup"><span data-stu-id="721d4-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
