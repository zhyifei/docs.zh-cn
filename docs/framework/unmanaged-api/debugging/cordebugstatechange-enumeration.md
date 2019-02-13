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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05a29022d3ebad37322aef9826f10689d2b5b06b
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221129"
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="db73c-102">“Cor调试状态已更改”枚举</span><span class="sxs-lookup"><span data-stu-id="db73c-102">CorDebugStateChange Enumeration</span></span>

<span data-ttu-id="db73c-103">描述基于进程变化必须删除的缓存数据数量。</span><span class="sxs-lookup"><span data-stu-id="db73c-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>

## <a name="syntax"></a><span data-ttu-id="db73c-104">语法</span><span class="sxs-lookup"><span data-stu-id="db73c-104">Syntax</span></span>

```
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a><span data-ttu-id="db73c-105">成员</span><span class="sxs-lookup"><span data-stu-id="db73c-105">Members</span></span>

| <span data-ttu-id="db73c-106">成员</span><span class="sxs-lookup"><span data-stu-id="db73c-106">Member</span></span>            | <span data-ttu-id="db73c-107">描述</span><span class="sxs-lookup"><span data-stu-id="db73c-107">Description</span></span>                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | <span data-ttu-id="db73c-108">该进程向前执行，达到了一种新的内存状态。</span><span class="sxs-lookup"><span data-stu-id="db73c-108">The process reached a new memory state via forward execution.</span></span>            |
| `FLUSH_ALL`       | <span data-ttu-id="db73c-109">进程的内存可能与以往截然不同。</span><span class="sxs-lookup"><span data-stu-id="db73c-109">The process' memory may be arbitrarily different than it was previously.</span></span> |

## <a name="remarks"></a><span data-ttu-id="db73c-110">备注</span><span class="sxs-lookup"><span data-stu-id="db73c-110">Remarks</span></span>

 <span data-ttu-id="db73c-111">成员`CorDebugStateChange`调试程序调用时，作为参数提供枚举`ProcessStateChanged`方法使用[ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md)或[ICorDebugProcess6::进程状态已更改](icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="db73c-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the `ProcessStateChanged` method either with [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) or [ICorDebugProcess6::ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span></span>

## <a name="requirements"></a><span data-ttu-id="db73c-112">要求</span><span class="sxs-lookup"><span data-stu-id="db73c-112">Requirements</span></span>

 <span data-ttu-id="db73c-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="db73c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="db73c-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db73c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="db73c-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db73c-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="db73c-116">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db73c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="db73c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="db73c-117">See also</span></span>

- [<span data-ttu-id="db73c-118">调试枚举</span><span class="sxs-lookup"><span data-stu-id="db73c-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="db73c-119">调试</span><span class="sxs-lookup"><span data-stu-id="db73c-119">Debugging</span></span>](index.md)
