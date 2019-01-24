---
title: CLRDATA_ADDRESS_RANGE 结构
ms.date: 01/16/2019
api.name:
- CLRDATA_ADDRESS_RANGE Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDATA_ADDRESS_RANGE Structure
helpviewer.keywords:
- CLRDATA_ADDRESS_RANGE Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 484ca79483fc4a5d8f0d1cf2cd5a961c297249e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654797"
---
# <a name="clrdataaddressrange-structure"></a><span data-ttu-id="3f034-102">CLRDATA_ADDRESS_RANGE 结构</span><span class="sxs-lookup"><span data-stu-id="3f034-102">CLRDATA_ADDRESS_RANGE Structure</span></span>

<span data-ttu-id="3f034-103">定义一个地址范围。</span><span class="sxs-lookup"><span data-stu-id="3f034-103">Defines an address range.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="3f034-104">语法</span><span class="sxs-lookup"><span data-stu-id="3f034-104">Syntax</span></span>

```
typedef struct
{
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
} CLRDATA_ADDRESS_RANGE;
```

## <a name="members"></a><span data-ttu-id="3f034-105">成员</span><span class="sxs-lookup"><span data-stu-id="3f034-105">Members</span></span>

| <span data-ttu-id="3f034-106">成员</span><span class="sxs-lookup"><span data-stu-id="3f034-106">Member</span></span>         | <span data-ttu-id="3f034-107">描述</span><span class="sxs-lookup"><span data-stu-id="3f034-107">Description</span></span>                     |
| -------------- | ------------------------------- |
| `startAddress` | <span data-ttu-id="3f034-108">范围的起始地址。</span><span class="sxs-lookup"><span data-stu-id="3f034-108">The start address of the range.</span></span> |
| `endAddress`   | <span data-ttu-id="3f034-109">范围的结束地址。</span><span class="sxs-lookup"><span data-stu-id="3f034-109">The end address of the range.</span></span>   |

## <a name="remarks"></a><span data-ttu-id="3f034-110">备注</span><span class="sxs-lookup"><span data-stu-id="3f034-110">Remarks</span></span>

<span data-ttu-id="3f034-111">此结构存在于运行时内，不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="3f034-111">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="3f034-112">若要使用它，将结构定义为指定更高版本，其中`CLRDATA_ADDRESS`是 64 位无符号的整数。</span><span class="sxs-lookup"><span data-stu-id="3f034-112">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="3f034-113">要求</span><span class="sxs-lookup"><span data-stu-id="3f034-113">Requirements</span></span>

<span data-ttu-id="3f034-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3f034-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="3f034-115">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="3f034-115">**Header:** None</span></span>  
<span data-ttu-id="3f034-116">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="3f034-116">**Library:** None</span></span>  
<span data-ttu-id="3f034-117">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3f034-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3f034-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f034-118">See also</span></span>

- [<span data-ttu-id="3f034-119">调试</span><span class="sxs-lookup"><span data-stu-id="3f034-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="3f034-120">调试结构</span><span class="sxs-lookup"><span data-stu-id="3f034-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
