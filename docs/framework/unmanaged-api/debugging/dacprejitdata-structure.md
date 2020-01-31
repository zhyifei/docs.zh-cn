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
ms.openlocfilehash: 46031f29da6916eeaeea863ebef6924a720d7155
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793818"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="42aaf-102">DacpReJitData 结构</span><span class="sxs-lookup"><span data-stu-id="42aaf-102">DacpReJitData Structure</span></span>

<span data-ttu-id="42aaf-103">定义有关给定探查器检测到的方法的基本信息。</span><span class="sxs-lookup"><span data-stu-id="42aaf-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="42aaf-104">语法</span><span class="sxs-lookup"><span data-stu-id="42aaf-104">Syntax</span></span>

```cpp
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

## <a name="members"></a><span data-ttu-id="42aaf-105">Members</span><span class="sxs-lookup"><span data-stu-id="42aaf-105">Members</span></span>

| <span data-ttu-id="42aaf-106">成员</span><span class="sxs-lookup"><span data-stu-id="42aaf-106">Member</span></span>           | <span data-ttu-id="42aaf-107">描述</span><span class="sxs-lookup"><span data-stu-id="42aaf-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="42aaf-108">方法的 ReJit 修订号。</span><span class="sxs-lookup"><span data-stu-id="42aaf-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="42aaf-109">一个标志，指示给定版本的该方法的 ReJit 检测的当前状态。</span><span class="sxs-lookup"><span data-stu-id="42aaf-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="42aaf-110">该方法的 rejitted 实现的基址。</span><span class="sxs-lookup"><span data-stu-id="42aaf-110">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="42aaf-111">备注</span><span class="sxs-lookup"><span data-stu-id="42aaf-111">Remarks</span></span>

<span data-ttu-id="42aaf-112">此结构存在于运行时中，并且不会通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="42aaf-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="42aaf-113">若要使用它，请定义上面指定的结构。</span><span class="sxs-lookup"><span data-stu-id="42aaf-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="42aaf-114">如果不使用 Microsoft 编译器，还必须使用 `ms_struct` 封装来定义结构。</span><span class="sxs-lookup"><span data-stu-id="42aaf-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="42aaf-115">需求</span><span class="sxs-lookup"><span data-stu-id="42aaf-115">Requirements</span></span>
<span data-ttu-id="42aaf-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="42aaf-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="42aaf-117">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="42aaf-117">**Header:** None</span></span>  
<span data-ttu-id="42aaf-118">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="42aaf-118">**Library:** None</span></span>  
<span data-ttu-id="42aaf-119">**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="42aaf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="42aaf-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42aaf-120">See also</span></span>

- [<span data-ttu-id="42aaf-121">调试</span><span class="sxs-lookup"><span data-stu-id="42aaf-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="42aaf-122">调试结构</span><span class="sxs-lookup"><span data-stu-id="42aaf-122">Debugging Structures</span></span>](debugging-structures.md)
