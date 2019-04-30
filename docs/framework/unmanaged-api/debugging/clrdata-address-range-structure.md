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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961300"
---
# <a name="clrdataaddressrange-structure"></a><span data-ttu-id="145bc-102">CLRDATA_ADDRESS_RANGE 结构</span><span class="sxs-lookup"><span data-stu-id="145bc-102">CLRDATA_ADDRESS_RANGE Structure</span></span>

<span data-ttu-id="145bc-103">定义一个地址范围。</span><span class="sxs-lookup"><span data-stu-id="145bc-103">Defines an address range.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="145bc-104">语法</span><span class="sxs-lookup"><span data-stu-id="145bc-104">Syntax</span></span>

```
typedef struct
{
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
} CLRDATA_ADDRESS_RANGE;
```

## <a name="members"></a><span data-ttu-id="145bc-105">成员</span><span class="sxs-lookup"><span data-stu-id="145bc-105">Members</span></span>

| <span data-ttu-id="145bc-106">成员</span><span class="sxs-lookup"><span data-stu-id="145bc-106">Member</span></span>         | <span data-ttu-id="145bc-107">描述</span><span class="sxs-lookup"><span data-stu-id="145bc-107">Description</span></span>                     |
| -------------- | ------------------------------- |
| `startAddress` | <span data-ttu-id="145bc-108">范围的起始地址。</span><span class="sxs-lookup"><span data-stu-id="145bc-108">The start address of the range.</span></span> |
| `endAddress`   | <span data-ttu-id="145bc-109">范围的结束地址。</span><span class="sxs-lookup"><span data-stu-id="145bc-109">The end address of the range.</span></span>   |

## <a name="remarks"></a><span data-ttu-id="145bc-110">备注</span><span class="sxs-lookup"><span data-stu-id="145bc-110">Remarks</span></span>

<span data-ttu-id="145bc-111">此结构存在于运行时内，不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="145bc-111">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="145bc-112">若要使用它，将结构定义为指定更高版本，其中`CLRDATA_ADDRESS`是 64 位无符号的整数。</span><span class="sxs-lookup"><span data-stu-id="145bc-112">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="145bc-113">要求</span><span class="sxs-lookup"><span data-stu-id="145bc-113">Requirements</span></span>

<span data-ttu-id="145bc-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="145bc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="145bc-115">**标头：** None</span><span class="sxs-lookup"><span data-stu-id="145bc-115">**Header:** None</span></span>  
<span data-ttu-id="145bc-116">**库：** None</span><span class="sxs-lookup"><span data-stu-id="145bc-116">**Library:** None</span></span>  
<span data-ttu-id="145bc-117">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="145bc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="145bc-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="145bc-118">See also</span></span>

- [<span data-ttu-id="145bc-119">调试</span><span class="sxs-lookup"><span data-stu-id="145bc-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="145bc-120">调试结构</span><span class="sxs-lookup"><span data-stu-id="145bc-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
