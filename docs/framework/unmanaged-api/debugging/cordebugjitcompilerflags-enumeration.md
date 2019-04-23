---
title: CorDebugJITCompilerFlags 枚举
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlags
helpviewer_keywords:
- CorDebugJITCompilerFlags enumeration [.NET Framework debugging]
ms.assetid: c0774f70-5bed-45e8-9922-fdad778c4c33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66a8ba59d221bb3fa2e815a1cbcfa79c474666cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105464"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="5b208-102">CorDebugJITCompilerFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="5b208-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="5b208-103">包含影响托管的实时 (JIT) 编译器的行为的值。</span><span class="sxs-lookup"><span data-stu-id="5b208-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b208-104">语法</span><span class="sxs-lookup"><span data-stu-id="5b208-104">Syntax</span></span>  
  
```  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="5b208-105">成员</span><span class="sxs-lookup"><span data-stu-id="5b208-105">Members</span></span>  
  
|<span data-ttu-id="5b208-106">成员</span><span class="sxs-lookup"><span data-stu-id="5b208-106">Member</span></span>|<span data-ttu-id="5b208-107">描述</span><span class="sxs-lookup"><span data-stu-id="5b208-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="5b208-108">指定编译器应跟踪编译数据，并允许进行优化。</span><span class="sxs-lookup"><span data-stu-id="5b208-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="5b208-109">指定编译器应跟踪编译数据，但禁用优化。</span><span class="sxs-lookup"><span data-stu-id="5b208-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="5b208-110">指定编译器应跟踪编译数据，禁用优化并启用编辑并继续技术。</span><span class="sxs-lookup"><span data-stu-id="5b208-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5b208-111">要求</span><span class="sxs-lookup"><span data-stu-id="5b208-111">Requirements</span></span>  
 <span data-ttu-id="5b208-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5b208-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b208-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b208-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b208-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b208-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b208-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b208-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b208-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b208-116">See also</span></span>

- [<span data-ttu-id="5b208-117">调试枚举</span><span class="sxs-lookup"><span data-stu-id="5b208-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
