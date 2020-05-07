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
ms.openlocfilehash: d623fe862eaf5902fd89d0e512dd07f73a03246f
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860815"
---
# <a name="dacpmethoddescdata-structure"></a><span data-ttu-id="c4f03-102">DacpMethodDescData 结构</span><span class="sxs-lookup"><span data-stu-id="c4f03-102">DacpMethodDescData Structure</span></span>

<span data-ttu-id="c4f03-103">定义方法的运行时信息的传输缓冲区。</span><span class="sxs-lookup"><span data-stu-id="c4f03-103">Defines a transport buffer for a method's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="c4f03-104">语法</span><span class="sxs-lookup"><span data-stu-id="c4f03-104">Syntax</span></span>

```cpp
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

## <a name="members"></a><span data-ttu-id="c4f03-105">成员</span><span class="sxs-lookup"><span data-stu-id="c4f03-105">Members</span></span>

| <span data-ttu-id="c4f03-106">成员</span><span class="sxs-lookup"><span data-stu-id="c4f03-106">Member</span></span>                       | <span data-ttu-id="c4f03-107">说明</span><span class="sxs-lookup"><span data-stu-id="c4f03-107">Description</span></span>                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | <span data-ttu-id="c4f03-108">指示运行时是否具有可用于方法的给定实例化的本机代码。</span><span class="sxs-lookup"><span data-stu-id="c4f03-108">Indicates if the runtime has native code available for the given instantiation of the method.</span></span> |
| `bIsDynamic`                 | <span data-ttu-id="c4f03-109">指示是否通过轻型代码生成动态生成方法。</span><span class="sxs-lookup"><span data-stu-id="c4f03-109">Indicates if the method is generated dynamically through lightweight code generation.</span></span>           |
| `wSlotNumber`                | <span data-ttu-id="c4f03-110">方法表中的方法的槽号。</span><span class="sxs-lookup"><span data-stu-id="c4f03-110">The method's slot number in the method table.</span></span>                                                   |
| `NativeCodeAddr`             | <span data-ttu-id="c4f03-111">方法的初始本机地址。</span><span class="sxs-lookup"><span data-stu-id="c4f03-111">The method's initial native address.</span></span>                                                            |
| `data`                       | <span data-ttu-id="c4f03-112">指向运行时内部使用的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="c4f03-112">Pointer to a buffer used internally by the runtime.</span></span>                                             |
| `MethodDescPtr`              | <span data-ttu-id="c4f03-113">指向运行时`MethodDesc`中的的指针。</span><span class="sxs-lookup"><span data-stu-id="c4f03-113">Pointer to the `MethodDesc` in the runtime.</span></span>                                                     |
| `nativeCodeInfo`             | <span data-ttu-id="c4f03-114">指向由运行时内部用于跟踪方法的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="c4f03-114">Pointer to a buffer used internally by the runtime to track methods.</span></span>                            |
| `moduleInfo`                 | <span data-ttu-id="c4f03-115">指向由运行时内部用于模块信息的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="c4f03-115">Pointer to a buffer used internally by the runtime for module information.</span></span>                      |
| `MDToken`                    | <span data-ttu-id="c4f03-116">与给定方法关联的标记。</span><span class="sxs-lookup"><span data-stu-id="c4f03-116">Token associated with the given method.</span></span>                                                         |
| `payloadGC`                  | <span data-ttu-id="c4f03-117">指向运行时内部使用的垃圾回收缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="c4f03-117">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `payloadGC2`                 | <span data-ttu-id="c4f03-118">指向运行时内部使用的垃圾回收缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="c4f03-118">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `managedDynamicMethodObject` | <span data-ttu-id="c4f03-119">如果该方法是动态的，则运行时在内部使用此缓冲区进行信息跟踪。</span><span class="sxs-lookup"><span data-stu-id="c4f03-119">If the method is dynamic, the runtime uses this buffer internally for information tracking.</span></span>     |
| `requestedIP`                | <span data-ttu-id="c4f03-120">用于在给定本机代码地址时填充每个请求的结构。</span><span class="sxs-lookup"><span data-stu-id="c4f03-120">Used to populate the structure per request when given a native code address.</span></span>                    |
| `rejitDataCurrent`           | <span data-ttu-id="c4f03-121">有关该方法的最新检测版本的信息。</span><span class="sxs-lookup"><span data-stu-id="c4f03-121">Information about the latest instrumented version of the method.</span></span>                                   |
| `rejitDataRequested`         | <span data-ttu-id="c4f03-122">请求的本机地址的 Rejit 信息。</span><span class="sxs-lookup"><span data-stu-id="c4f03-122">Rejit information for the requested native address.</span></span>                                             |
| `cJittedRejitVersions`       | <span data-ttu-id="c4f03-123">方法已通过检测 rejitted 的次数。</span><span class="sxs-lookup"><span data-stu-id="c4f03-123">Number of times the method has been rejitted through instrumentation.</span></span>                           |

## <a name="remarks"></a><span data-ttu-id="c4f03-124">备注</span><span class="sxs-lookup"><span data-stu-id="c4f03-124">Remarks</span></span>

<span data-ttu-id="c4f03-125">此结构存在于运行时中，并且不会通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="c4f03-125">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="c4f03-126">若要使用它，请定义上面指定的结构。</span><span class="sxs-lookup"><span data-stu-id="c4f03-126">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="c4f03-127">要求</span><span class="sxs-lookup"><span data-stu-id="c4f03-127">Requirements</span></span>
<span data-ttu-id="c4f03-128">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c4f03-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="c4f03-129">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="c4f03-129">**Header:** None</span></span>  
<span data-ttu-id="c4f03-130">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="c4f03-130">**Library:** None</span></span>  
<span data-ttu-id="c4f03-131">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c4f03-131">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="c4f03-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4f03-132">See also</span></span>

- [<span data-ttu-id="c4f03-133">调试</span><span class="sxs-lookup"><span data-stu-id="c4f03-133">Debugging</span></span>](index.md)
- [<span data-ttu-id="c4f03-134">调试结构</span><span class="sxs-lookup"><span data-stu-id="c4f03-134">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="c4f03-135">常见数据类型</span><span class="sxs-lookup"><span data-stu-id="c4f03-135">Common Data Types</span></span>](../common-data-types-unmanaged-api-reference.md)
