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
ms.openlocfilehash: 2f62707fb1e52a96cf3f131e9c11fee82ab03f4e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097182"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="a3bdb-102">CorDebugIlToNativeMappingTypes 枚举</span><span class="sxs-lookup"><span data-stu-id="a3bdb-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="a3bdb-103">指示本机指令，COR_DEBUG_IL_TO_NATIVE_MAP 结构的实例所表示的特定范围是否与特殊的代码区域相符。</span><span class="sxs-lookup"><span data-stu-id="a3bdb-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3bdb-104">语法</span><span class="sxs-lookup"><span data-stu-id="a3bdb-104">Syntax</span></span>  
  
```  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="a3bdb-105">成员</span><span class="sxs-lookup"><span data-stu-id="a3bdb-105">Members</span></span>  
  
|<span data-ttu-id="a3bdb-106">成员</span><span class="sxs-lookup"><span data-stu-id="a3bdb-106">Member</span></span>|<span data-ttu-id="a3bdb-107">描述</span><span class="sxs-lookup"><span data-stu-id="a3bdb-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="a3bdb-108">本机指令的范围不对应任何特殊的代码区域。</span><span class="sxs-lookup"><span data-stu-id="a3bdb-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="a3bdb-109">本机指令的范围对应于在 prolog。</span><span class="sxs-lookup"><span data-stu-id="a3bdb-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="a3bdb-110">本机指令的范围与 epilog 相对应。</span><span class="sxs-lookup"><span data-stu-id="a3bdb-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a3bdb-111">要求</span><span class="sxs-lookup"><span data-stu-id="a3bdb-111">Requirements</span></span>  
 <span data-ttu-id="a3bdb-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a3bdb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3bdb-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3bdb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3bdb-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3bdb-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a3bdb-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="a3bdb-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a3bdb-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3bdb-116">See also</span></span>

- [<span data-ttu-id="a3bdb-117">GetILToNativeMapping 方法</span><span class="sxs-lookup"><span data-stu-id="a3bdb-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="a3bdb-118">调试枚举</span><span class="sxs-lookup"><span data-stu-id="a3bdb-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
