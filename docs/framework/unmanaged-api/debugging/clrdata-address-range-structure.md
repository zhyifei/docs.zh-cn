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
ms.openlocfilehash: 8eb841b4c4f06a3932805ae6222bdd693def5ea0
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274301"
---
# <a name="clrdata_address_range-structure"></a><span data-ttu-id="80281-102">CLRDATA_ADDRESS_RANGE 结构</span><span class="sxs-lookup"><span data-stu-id="80281-102">CLRDATA_ADDRESS_RANGE Structure</span></span>

<span data-ttu-id="80281-103">定义地址范围。</span><span class="sxs-lookup"><span data-stu-id="80281-103">Defines an address range.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="80281-104">语法</span><span class="sxs-lookup"><span data-stu-id="80281-104">Syntax</span></span>

```cpp
typedef struct
{
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
} CLRDATA_ADDRESS_RANGE;
```

## <a name="members"></a><span data-ttu-id="80281-105">成员</span><span class="sxs-lookup"><span data-stu-id="80281-105">Members</span></span>

| <span data-ttu-id="80281-106">成员</span><span class="sxs-lookup"><span data-stu-id="80281-106">Member</span></span>         | <span data-ttu-id="80281-107">描述</span><span class="sxs-lookup"><span data-stu-id="80281-107">Description</span></span>                     |
| -------------- | ------------------------------- |
| `startAddress` | <span data-ttu-id="80281-108">范围的起始地址。</span><span class="sxs-lookup"><span data-stu-id="80281-108">The start address of the range.</span></span> |
| `endAddress`   | <span data-ttu-id="80281-109">范围的结束地址。</span><span class="sxs-lookup"><span data-stu-id="80281-109">The end address of the range.</span></span>   |

## <a name="remarks"></a><span data-ttu-id="80281-110">备注</span><span class="sxs-lookup"><span data-stu-id="80281-110">Remarks</span></span>

<span data-ttu-id="80281-111">此结构存在于运行时中，并且不会通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="80281-111">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="80281-112">若要使用它，请定义上面指定的结构， `CLRDATA_ADDRESS`其中是一个64位无符号整数。</span><span class="sxs-lookup"><span data-stu-id="80281-112">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="80281-113">要求</span><span class="sxs-lookup"><span data-stu-id="80281-113">Requirements</span></span>

<span data-ttu-id="80281-114">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="80281-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="80281-115">**标头：** None</span><span class="sxs-lookup"><span data-stu-id="80281-115">**Header:** None</span></span>  
<span data-ttu-id="80281-116">**类库**None</span><span class="sxs-lookup"><span data-stu-id="80281-116">**Library:** None</span></span>  
<span data-ttu-id="80281-117">**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="80281-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="80281-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="80281-118">See also</span></span>

- [<span data-ttu-id="80281-119">调试</span><span class="sxs-lookup"><span data-stu-id="80281-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="80281-120">调试结构</span><span class="sxs-lookup"><span data-stu-id="80281-120">Debugging Structures</span></span>](debugging-structures.md)
