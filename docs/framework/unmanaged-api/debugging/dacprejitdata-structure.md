---
title: DacpReJitData 结构
ms.date: 02/01/2019
api.name:
- DacpReJitData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpReJitData Structure
helpviewer.keywords:
- DacpReJitData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: a2850add9acb2f7c5297ac6956e349c9277be291
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965907"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="2bff8-102">DacpReJitData 结构</span><span class="sxs-lookup"><span data-stu-id="2bff8-102">DacpReJitData Structure</span></span>

<span data-ttu-id="2bff8-103">定义给定探查器检测方法有关的基本信息。</span><span class="sxs-lookup"><span data-stu-id="2bff8-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="2bff8-104">语法</span><span class="sxs-lookup"><span data-stu-id="2bff8-104">Syntax</span></span>

```
struct MSLAYOUT DacpReJitData
{
    enum Flags
    {
        kUnknown,
        kRequested,
        kActive,
        kReverted,
    };

    CLRDATA_ADDRESS                 rejitID;
    Flags                           flags;
    CLRDATA_ADDRESS                 NativeCodeAddr;
};
```

## <a name="members"></a><span data-ttu-id="2bff8-105">成员</span><span class="sxs-lookup"><span data-stu-id="2bff8-105">Members</span></span>

| <span data-ttu-id="2bff8-106">成员</span><span class="sxs-lookup"><span data-stu-id="2bff8-106">Member</span></span>           | <span data-ttu-id="2bff8-107">描述</span><span class="sxs-lookup"><span data-stu-id="2bff8-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="2bff8-108">一种方法 ReJit 修订号。</span><span class="sxs-lookup"><span data-stu-id="2bff8-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="2bff8-109">一个标志，指示该方法的给定版本的 ReJit 检测的当前状态。</span><span class="sxs-lookup"><span data-stu-id="2bff8-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="2bff8-110">方法的 rejitted 实现基址。</span><span class="sxs-lookup"><span data-stu-id="2bff8-110">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="2bff8-111">备注</span><span class="sxs-lookup"><span data-stu-id="2bff8-111">Remarks</span></span>

<span data-ttu-id="2bff8-112">此结构存在于运行时内，不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="2bff8-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="2bff8-113">若要使用它，如上所示定义的结构。</span><span class="sxs-lookup"><span data-stu-id="2bff8-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="2bff8-114">此外必须使用定义结构`ms_struct`打包，如果不是使用 Microsoft 编译器。</span><span class="sxs-lookup"><span data-stu-id="2bff8-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="2bff8-115">要求</span><span class="sxs-lookup"><span data-stu-id="2bff8-115">Requirements</span></span>
<span data-ttu-id="2bff8-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2bff8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="2bff8-117">**标头：** None</span><span class="sxs-lookup"><span data-stu-id="2bff8-117">**Header:** None</span></span>  
<span data-ttu-id="2bff8-118">**库：** None</span><span class="sxs-lookup"><span data-stu-id="2bff8-118">**Library:** None</span></span>  
<span data-ttu-id="2bff8-119">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2bff8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="2bff8-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="2bff8-120">See also</span></span>

- [<span data-ttu-id="2bff8-121">调试</span><span class="sxs-lookup"><span data-stu-id="2bff8-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="2bff8-122">调试结构</span><span class="sxs-lookup"><span data-stu-id="2bff8-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
