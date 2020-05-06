---
title: “Cor调试状态已更改”枚举
ms.date: 02/07/2019
api_name:
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
ms.openlocfilehash: d94422d25da91cd2a6653a95cbd852c3930a151a
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795685"
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="cd06a-102">“Cor调试状态已更改”枚举</span><span class="sxs-lookup"><span data-stu-id="cd06a-102">CorDebugStateChange Enumeration</span></span>

<span data-ttu-id="cd06a-103">描述基于进程变化必须删除的缓存数据数量。</span><span class="sxs-lookup"><span data-stu-id="cd06a-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>

## <a name="syntax"></a><span data-ttu-id="cd06a-104">语法</span><span class="sxs-lookup"><span data-stu-id="cd06a-104">Syntax</span></span>

```cpp
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a><span data-ttu-id="cd06a-105">成员</span><span class="sxs-lookup"><span data-stu-id="cd06a-105">Members</span></span>

| <span data-ttu-id="cd06a-106">成员</span><span class="sxs-lookup"><span data-stu-id="cd06a-106">Member</span></span>            | <span data-ttu-id="cd06a-107">说明</span><span class="sxs-lookup"><span data-stu-id="cd06a-107">Description</span></span>                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | <span data-ttu-id="cd06a-108">该进程向前执行，达到了一种新的内存状态。</span><span class="sxs-lookup"><span data-stu-id="cd06a-108">The process reached a new memory state via forward execution.</span></span>            |
| `FLUSH_ALL`       | <span data-ttu-id="cd06a-109">进程的内存可能与以往截然不同。</span><span class="sxs-lookup"><span data-stu-id="cd06a-109">The process' memory may be arbitrarily different than it was previously.</span></span> |

## <a name="remarks"></a><span data-ttu-id="cd06a-110">备注</span><span class="sxs-lookup"><span data-stu-id="cd06a-110">Remarks</span></span>

 <span data-ttu-id="cd06a-111">当调试器使用`CorDebugStateChange` [ICorDebugProcess4：:P rocessstatechanged](icordebugprocess4-processstatechanged-method.md)或[ICorDebugProcess6：:P rocessstatechanged](icordebugprocess6-processstatechanged-method.md)调用`ProcessStateChanged`方法时，枚举的成员作为参数提供。</span><span class="sxs-lookup"><span data-stu-id="cd06a-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the `ProcessStateChanged` method either with [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) or [ICorDebugProcess6::ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span></span>

## <a name="requirements"></a><span data-ttu-id="cd06a-112">要求</span><span class="sxs-lookup"><span data-stu-id="cd06a-112">Requirements</span></span>

 <span data-ttu-id="cd06a-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cd06a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="cd06a-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd06a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="cd06a-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd06a-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="cd06a-116">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd06a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cd06a-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd06a-117">See also</span></span>

- [<span data-ttu-id="cd06a-118">调试枚举</span><span class="sxs-lookup"><span data-stu-id="cd06a-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="cd06a-119">调试</span><span class="sxs-lookup"><span data-stu-id="cd06a-119">Debugging</span></span>](index.md)
