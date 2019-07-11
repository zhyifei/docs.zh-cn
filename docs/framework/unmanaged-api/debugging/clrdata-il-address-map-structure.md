---
title: CLRDATA_IL_ADDRESS_MAP 结构
ms.date: 01/16/2019
api.name:
- CLRDATA_IL_ADDRESS_MAP Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure
helpviewer.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 2f34ae3e6687027aeb75e7ea169487fc8cbda466
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741029"
---
# <a name="clrdatailaddressmap-structure"></a><span data-ttu-id="a141f-102">CLRDATA_IL_ADDRESS_MAP 结构</span><span class="sxs-lookup"><span data-stu-id="a141f-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="a141f-103">定义从 IL 到地址映射。</span><span class="sxs-lookup"><span data-stu-id="a141f-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a141f-104">语法</span><span class="sxs-lookup"><span data-stu-id="a141f-104">Syntax</span></span>

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="a141f-105">成员</span><span class="sxs-lookup"><span data-stu-id="a141f-105">Members</span></span>

| <span data-ttu-id="a141f-106">成员</span><span class="sxs-lookup"><span data-stu-id="a141f-106">Member</span></span>         | <span data-ttu-id="a141f-107">描述</span><span class="sxs-lookup"><span data-stu-id="a141f-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="a141f-108">包含的地址范围的的 IL 偏移量</span><span class="sxs-lookup"><span data-stu-id="a141f-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="a141f-109">范围的起始地址。</span><span class="sxs-lookup"><span data-stu-id="a141f-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="a141f-110">范围的结束地址。</span><span class="sxs-lookup"><span data-stu-id="a141f-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="a141f-111">数据的类型。</span><span class="sxs-lookup"><span data-stu-id="a141f-111">The type of the data.</span></span> <span data-ttu-id="a141f-112">当前未使用此值</span><span class="sxs-lookup"><span data-stu-id="a141f-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="a141f-113">备注</span><span class="sxs-lookup"><span data-stu-id="a141f-113">Remarks</span></span>

<span data-ttu-id="a141f-114">此结构存在于运行时内，不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="a141f-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="a141f-115">若要使用它，将结构定义为指定更高版本，其中`CLRDATA_ADDRESS`是 64 位无符号的整数。</span><span class="sxs-lookup"><span data-stu-id="a141f-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="a141f-116">要求</span><span class="sxs-lookup"><span data-stu-id="a141f-116">Requirements</span></span>

<span data-ttu-id="a141f-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a141f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="a141f-118">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="a141f-118">**Header:** None</span></span>  
<span data-ttu-id="a141f-119">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="a141f-119">**Library:** None</span></span>   
<span data-ttu-id="a141f-120">**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a141f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="a141f-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="a141f-121">See also</span></span>

- [<span data-ttu-id="a141f-122">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="a141f-122">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="a141f-123">调试</span><span class="sxs-lookup"><span data-stu-id="a141f-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="a141f-124">调试结构</span><span class="sxs-lookup"><span data-stu-id="a141f-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
