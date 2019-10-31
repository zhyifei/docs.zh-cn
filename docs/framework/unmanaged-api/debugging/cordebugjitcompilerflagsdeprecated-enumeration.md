---
title: CorDebugJITCompilerFlagsDeprecated 枚举
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlagsDeprecated
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlagsDeprecated
helpviewer_keywords:
- CorDebugJITCompilerFlagsDeprecated enumeration [.NET Framework debugging]
ms.assetid: af15e2ca-6be1-472b-bd36-03644a1e3ddd
topic_type:
- apiref
ms.openlocfilehash: d731b12ddf195137ff38d32ab0ca52aa90f48d4e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132785"
---
# <a name="cordebugjitcompilerflagsdeprecated-enumeration"></a><span data-ttu-id="42eb1-102">CorDebugJITCompilerFlagsDeprecated 枚举</span><span class="sxs-lookup"><span data-stu-id="42eb1-102">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>
<span data-ttu-id="42eb1-103">此枚举已过时。</span><span class="sxs-lookup"><span data-stu-id="42eb1-103">This enumeration is obsolete.</span></span> <span data-ttu-id="42eb1-104">改为使用[CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)枚举的 `CORDEBUG_JIT_DEFAULT` 成员。</span><span class="sxs-lookup"><span data-stu-id="42eb1-104">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42eb1-105">语法</span><span class="sxs-lookup"><span data-stu-id="42eb1-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlagsDeprecated {  
    CORDEBUG_JIT_TRACK_DEBUG_INFO  = 0x1  
} CorDebugJITCompilerFlagsDeprecated;  
```  
  
## <a name="members"></a><span data-ttu-id="42eb1-106">Members</span><span class="sxs-lookup"><span data-stu-id="42eb1-106">Members</span></span>  
  
|<span data-ttu-id="42eb1-107">成员</span><span class="sxs-lookup"><span data-stu-id="42eb1-107">Member</span></span>|<span data-ttu-id="42eb1-108">描述</span><span class="sxs-lookup"><span data-stu-id="42eb1-108">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_TRACK_DEBUG_INFO`|<span data-ttu-id="42eb1-109">请改用 `CORDEBUG_JIT_DEFAULT` 。</span><span class="sxs-lookup"><span data-stu-id="42eb1-109">Use `CORDEBUG_JIT_DEFAULT` instead.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="42eb1-110">要求</span><span class="sxs-lookup"><span data-stu-id="42eb1-110">Requirements</span></span>  
 <span data-ttu-id="42eb1-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="42eb1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42eb1-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42eb1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42eb1-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42eb1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42eb1-114">**.NET Framework 版本：** 1.0、1。1</span><span class="sxs-lookup"><span data-stu-id="42eb1-114">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42eb1-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="42eb1-115">See also</span></span>

- [<span data-ttu-id="42eb1-116">调试枚举</span><span class="sxs-lookup"><span data-stu-id="42eb1-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
