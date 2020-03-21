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
ms.openlocfilehash: e680a7a0dc3209d1988f6c84be0864572a74b3a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179376"
---
# <a name="clrdata_il_address_map-structure"></a><span data-ttu-id="c569f-102">CLRDATA_IL_ADDRESS_MAP 结构</span><span class="sxs-lookup"><span data-stu-id="c569f-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="c569f-103">定义 IL 以解决映射。</span><span class="sxs-lookup"><span data-stu-id="c569f-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="c569f-104">语法</span><span class="sxs-lookup"><span data-stu-id="c569f-104">Syntax</span></span>

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="c569f-105">成员</span><span class="sxs-lookup"><span data-stu-id="c569f-105">Members</span></span>

| <span data-ttu-id="c569f-106">成员</span><span class="sxs-lookup"><span data-stu-id="c569f-106">Member</span></span>         | <span data-ttu-id="c569f-107">说明</span><span class="sxs-lookup"><span data-stu-id="c569f-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="c569f-108">包含地址范围的 IL 偏移量</span><span class="sxs-lookup"><span data-stu-id="c569f-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="c569f-109">范围的起始地址。</span><span class="sxs-lookup"><span data-stu-id="c569f-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="c569f-110">范围的结束地址。</span><span class="sxs-lookup"><span data-stu-id="c569f-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="c569f-111">数据的类型。</span><span class="sxs-lookup"><span data-stu-id="c569f-111">The type of the data.</span></span> <span data-ttu-id="c569f-112">当前未使用此值</span><span class="sxs-lookup"><span data-stu-id="c569f-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="c569f-113">备注</span><span class="sxs-lookup"><span data-stu-id="c569f-113">Remarks</span></span>

<span data-ttu-id="c569f-114">此结构位于运行时内，不会通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="c569f-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="c569f-115">要使用它，请定义上面指定的结构，其中`CLRDATA_ADDRESS`是 64 位无符号整数。</span><span class="sxs-lookup"><span data-stu-id="c569f-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="c569f-116">要求</span><span class="sxs-lookup"><span data-stu-id="c569f-116">Requirements</span></span>

<span data-ttu-id="c569f-117">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c569f-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="c569f-118">**标题：** 没有</span><span class="sxs-lookup"><span data-stu-id="c569f-118">**Header:** None</span></span>  
<span data-ttu-id="c569f-119">**库：** 无 **.NET 框架版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c569f-119">**Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="c569f-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c569f-120">See also</span></span>

- [<span data-ttu-id="c569f-121">CLRDataSource 类型枚举</span><span class="sxs-lookup"><span data-stu-id="c569f-121">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="c569f-122">调试</span><span class="sxs-lookup"><span data-stu-id="c569f-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="c569f-123">调试结构</span><span class="sxs-lookup"><span data-stu-id="c569f-123">Debugging Structures</span></span>](debugging-structures.md)
