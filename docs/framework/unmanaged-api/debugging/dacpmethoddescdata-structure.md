---
title: DacpMethodDescData 结构
ms.date: 02/01/2019
api.name:
- DacpMethodDescData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpMethodDescData Structure
helpviewer.keywords:
- DacpMethodDescData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: e9037fc035693e079e2471ad37263108656b8c01
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828582"
---
# <a name="dacpmethoddescdata-structure"></a><span data-ttu-id="d7124-102">DacpMethodDescData 结构</span><span class="sxs-lookup"><span data-stu-id="d7124-102">DacpMethodDescData Structure</span></span>

<span data-ttu-id="d7124-103">定义方法的运行时信息的传输缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d7124-103">Defines a transport buffer for a method's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="d7124-104">语法</span><span class="sxs-lookup"><span data-stu-id="d7124-104">Syntax</span></span>

```
struct DacpMethodDescData
{
    int             bHasNativeCode;
    int             bIsDynamic;
    unsigned short  wSlotNumber;
    CLRDATA_ADDRESS NativeCodeAddr;
    CLRDATA_ADDRESS data;
    CLRDATA_ADDRESS MethodDescPtr;
    CLRDATA_ADDRESS nativeCodeInfo;
    CLRDATA_ADDRESS moduleInfo;
    mdToken         MDToken;
    CLRDATA_ADDRESS payloadGC;
    CLRDATA_ADDRESS payloadGC2;
    CLRDATA_ADDRESS managedDynamicMethodObject;
    CLRDATA_ADDRESS requestedIP;
    DacpReJitData   rejitDataCurrent;
    DacpReJitData   rejitDataRequested;
    unsigned long   cJittedRejitVersions;
};
```

## <a name="members"></a><span data-ttu-id="d7124-105">成员</span><span class="sxs-lookup"><span data-stu-id="d7124-105">Members</span></span>

| <span data-ttu-id="d7124-106">成员</span><span class="sxs-lookup"><span data-stu-id="d7124-106">Member</span></span>                       | <span data-ttu-id="d7124-107">描述</span><span class="sxs-lookup"><span data-stu-id="d7124-107">Description</span></span>                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | <span data-ttu-id="d7124-108">指示运行时是否有可用于该方法的给定实例化的本机代码。</span><span class="sxs-lookup"><span data-stu-id="d7124-108">Indicates if the runtime has native code available for the given instantiation of the method.</span></span> |
| `bIsDynamic`                 | <span data-ttu-id="d7124-109">指示是否通过轻量级代码生成动态生成方法。</span><span class="sxs-lookup"><span data-stu-id="d7124-109">Indicates if the method is generated dynamically through lightweight code generation.</span></span>           |
| `wSlotNumber`                | <span data-ttu-id="d7124-110">方法的方法表中的槽数。</span><span class="sxs-lookup"><span data-stu-id="d7124-110">The method's slot number in the method table.</span></span>                                                   |
| `NativeCodeAddr`             | <span data-ttu-id="d7124-111">该方法的初始本机地址。</span><span class="sxs-lookup"><span data-stu-id="d7124-111">The method's initial native address.</span></span>                                                            |
| `data`                       | <span data-ttu-id="d7124-112">指向由运行时在内部使用的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d7124-112">Pointer to a buffer used internally by the runtime.</span></span>                                             |
| `MethodDescPtr`              | <span data-ttu-id="d7124-113">指向`MethodDesc`运行时中。</span><span class="sxs-lookup"><span data-stu-id="d7124-113">Pointer to the `MethodDesc` in the runtime.</span></span>                                                     |
| `nativeCodeInfo`             | <span data-ttu-id="d7124-114">指向由运行时在内部使用，以跟踪方法的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d7124-114">Pointer to a buffer used internally by the runtime to track methods.</span></span>                            |
| `moduleInfo`                 | <span data-ttu-id="d7124-115">模块信息由运行时在内部使用的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="d7124-115">Pointer to a buffer used internally by the runtime for module information.</span></span>                      |
| `MDToken`                    | <span data-ttu-id="d7124-116">与给定的方法相关联的标记。</span><span class="sxs-lookup"><span data-stu-id="d7124-116">Token associated with the given method.</span></span>                                                         |
| `payloadGC`                  | <span data-ttu-id="d7124-117">运行时在内部使用的垃圾收集缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="d7124-117">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `payloadGC2`                 | <span data-ttu-id="d7124-118">运行时在内部使用的垃圾收集缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="d7124-118">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `managedDynamicMethodObject` | <span data-ttu-id="d7124-119">如果该方法是动态的运行时使用此缓冲区在内部跟踪的信息。</span><span class="sxs-lookup"><span data-stu-id="d7124-119">If the method is dynamic, the runtime uses this buffer internally for information tracking.</span></span>     |
| `requestedIP`                | <span data-ttu-id="d7124-120">用于填充每个请求在给定的本机代码地址结构。</span><span class="sxs-lookup"><span data-stu-id="d7124-120">Used to populate the structure per request when given a native code address.</span></span>                    |
| `rejitDataCurrent`           | <span data-ttu-id="d7124-121">有关最新的检测方法版本的信息。</span><span class="sxs-lookup"><span data-stu-id="d7124-121">Information about the latest instrumented version of the method.</span></span>                                   |
| `rejitDataRequested`         | <span data-ttu-id="d7124-122">Rejit 请求的本机地址信息。</span><span class="sxs-lookup"><span data-stu-id="d7124-122">Rejit information for the requested native address.</span></span>                                             |
| `cJittedRejitVersions`       | <span data-ttu-id="d7124-123">该方法已通过检测 rejitted 次数。</span><span class="sxs-lookup"><span data-stu-id="d7124-123">Number of times the method has been rejitted through instrumentation.</span></span>                           |


## <a name="remarks"></a><span data-ttu-id="d7124-124">备注</span><span class="sxs-lookup"><span data-stu-id="d7124-124">Remarks</span></span>

<span data-ttu-id="d7124-125">此结构存在于运行时内，不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="d7124-125">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="d7124-126">若要使用它，如上所示定义的结构。</span><span class="sxs-lookup"><span data-stu-id="d7124-126">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="d7124-127">要求</span><span class="sxs-lookup"><span data-stu-id="d7124-127">Requirements</span></span>
<span data-ttu-id="d7124-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d7124-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d7124-129">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="d7124-129">**Header:** None</span></span>  
<span data-ttu-id="d7124-130">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="d7124-130">**Library:** None</span></span>  
<span data-ttu-id="d7124-131">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d7124-131">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d7124-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7124-132">See also</span></span>
- [<span data-ttu-id="d7124-133">调试</span><span class="sxs-lookup"><span data-stu-id="d7124-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="d7124-134">调试结构</span><span class="sxs-lookup"><span data-stu-id="d7124-134">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="d7124-135">常见数据类型</span><span class="sxs-lookup"><span data-stu-id="d7124-135">Common Data Types</span></span>](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)
