---
title: DacpGetModuleAddress Structure
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
ms.openlocfilehash: cbea6c0562c68ae5d18247dc97bc53eb9dfbfd7e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104099"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="0f0ff-102">DacpGetModuleAddress Structure</span><span class="sxs-lookup"><span data-stu-id="0f0ff-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="0f0ff-103">定义模块地址请求的容器。</span><span class="sxs-lookup"><span data-stu-id="0f0ff-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="0f0ff-104">语法</span><span class="sxs-lookup"><span data-stu-id="0f0ff-104">Syntax</span></span>

```
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="0f0ff-105">成员</span><span class="sxs-lookup"><span data-stu-id="0f0ff-105">Members</span></span>

| <span data-ttu-id="0f0ff-106">成员</span><span class="sxs-lookup"><span data-stu-id="0f0ff-106">Member</span></span>      | <span data-ttu-id="0f0ff-107">描述</span><span class="sxs-lookup"><span data-stu-id="0f0ff-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="0f0ff-108">指向模块的指针。</span><span class="sxs-lookup"><span data-stu-id="0f0ff-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="0f0ff-109">方法</span><span class="sxs-lookup"><span data-stu-id="0f0ff-109">Methods</span></span>

| <span data-ttu-id="0f0ff-110">方法</span><span class="sxs-lookup"><span data-stu-id="0f0ff-110">Method</span></span>                                                                                               | <span data-ttu-id="0f0ff-111">描述</span><span class="sxs-lookup"><span data-stu-id="0f0ff-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="0f0ff-112">请求</span><span class="sxs-lookup"><span data-stu-id="0f0ff-112">Request</span></span>](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="0f0ff-113">执行请求以填充从给定的运行时结构的结构。</span><span class="sxs-lookup"><span data-stu-id="0f0ff-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="0f0ff-114">备注</span><span class="sxs-lookup"><span data-stu-id="0f0ff-114">Remarks</span></span>

<span data-ttu-id="0f0ff-115">此结构存在于运行时内，不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="0f0ff-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="0f0ff-116">若要使用它，将结构定义为指定更高版本，其中`CLRDATA_ADDRESS`是 64 位无符号的整数。</span><span class="sxs-lookup"><span data-stu-id="0f0ff-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="0f0ff-117">要求</span><span class="sxs-lookup"><span data-stu-id="0f0ff-117">Requirements</span></span>
<span data-ttu-id="0f0ff-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0f0ff-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="0f0ff-119">**标头：** None</span><span class="sxs-lookup"><span data-stu-id="0f0ff-119">**Header:** None</span></span>  
<span data-ttu-id="0f0ff-120">**库：** None</span><span class="sxs-lookup"><span data-stu-id="0f0ff-120">**Library:** None</span></span>  
<span data-ttu-id="0f0ff-121">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0f0ff-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="0f0ff-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f0ff-122">See also</span></span>

- [<span data-ttu-id="0f0ff-123">调试</span><span class="sxs-lookup"><span data-stu-id="0f0ff-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="0f0ff-124">调试结构</span><span class="sxs-lookup"><span data-stu-id="0f0ff-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
