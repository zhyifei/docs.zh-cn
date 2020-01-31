---
title: DacpGetModuleAddress 结构
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress Structure
helpviewer.keywords:
- DacpGetModuleAddress Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 1e3a62de3259c012438c64ece26e696682ec96e6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789209"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="c6bb9-102">DacpGetModuleAddress 结构</span><span class="sxs-lookup"><span data-stu-id="c6bb9-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="c6bb9-103">定义模块地址请求的容器。</span><span class="sxs-lookup"><span data-stu-id="c6bb9-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="c6bb9-104">语法</span><span class="sxs-lookup"><span data-stu-id="c6bb9-104">Syntax</span></span>

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="c6bb9-105">Members</span><span class="sxs-lookup"><span data-stu-id="c6bb9-105">Members</span></span>

| <span data-ttu-id="c6bb9-106">成员</span><span class="sxs-lookup"><span data-stu-id="c6bb9-106">Member</span></span>      | <span data-ttu-id="c6bb9-107">描述</span><span class="sxs-lookup"><span data-stu-id="c6bb9-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="c6bb9-108">指向模块的指针。</span><span class="sxs-lookup"><span data-stu-id="c6bb9-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="c6bb9-109">方法</span><span class="sxs-lookup"><span data-stu-id="c6bb9-109">Methods</span></span>

| <span data-ttu-id="c6bb9-110">方法</span><span class="sxs-lookup"><span data-stu-id="c6bb9-110">Method</span></span>                                                                                               | <span data-ttu-id="c6bb9-111">描述</span><span class="sxs-lookup"><span data-stu-id="c6bb9-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="c6bb9-112">请求</span><span class="sxs-lookup"><span data-stu-id="c6bb9-112">Request</span></span>](dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="c6bb9-113">执行从给定的运行时结构填充结构的请求。</span><span class="sxs-lookup"><span data-stu-id="c6bb9-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="c6bb9-114">备注</span><span class="sxs-lookup"><span data-stu-id="c6bb9-114">Remarks</span></span>

<span data-ttu-id="c6bb9-115">此结构存在于运行时中，并且不会通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="c6bb9-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="c6bb9-116">若要使用它，请定义上面指定的结构，其中 `CLRDATA_ADDRESS` 为64位无符号整数。</span><span class="sxs-lookup"><span data-stu-id="c6bb9-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="c6bb9-117">需求</span><span class="sxs-lookup"><span data-stu-id="c6bb9-117">Requirements</span></span>
<span data-ttu-id="c6bb9-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c6bb9-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="c6bb9-119">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="c6bb9-119">**Header:** None</span></span>  
<span data-ttu-id="c6bb9-120">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="c6bb9-120">**Library:** None</span></span>  
<span data-ttu-id="c6bb9-121">**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c6bb9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="c6bb9-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6bb9-122">See also</span></span>

- [<span data-ttu-id="c6bb9-123">调试</span><span class="sxs-lookup"><span data-stu-id="c6bb9-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="c6bb9-124">调试结构</span><span class="sxs-lookup"><span data-stu-id="c6bb9-124">Debugging Structures</span></span>](debugging-structures.md)
