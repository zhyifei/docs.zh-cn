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
ms.openlocfilehash: 3f6928832d822422177ebd7def142422953468a0
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274296"
---
# <a name="clrdata_il_address_map-structure"></a><span data-ttu-id="7d133-102">CLRDATA_IL_ADDRESS_MAP 结构</span><span class="sxs-lookup"><span data-stu-id="7d133-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="7d133-103">定义用于寻址映射的 IL。</span><span class="sxs-lookup"><span data-stu-id="7d133-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="7d133-104">语法</span><span class="sxs-lookup"><span data-stu-id="7d133-104">Syntax</span></span>

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="7d133-105">成员</span><span class="sxs-lookup"><span data-stu-id="7d133-105">Members</span></span>

| <span data-ttu-id="7d133-106">成员</span><span class="sxs-lookup"><span data-stu-id="7d133-106">Member</span></span>         | <span data-ttu-id="7d133-107">描述</span><span class="sxs-lookup"><span data-stu-id="7d133-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="7d133-108">所包含的地址范围的 IL 偏移量</span><span class="sxs-lookup"><span data-stu-id="7d133-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="7d133-109">范围的起始地址。</span><span class="sxs-lookup"><span data-stu-id="7d133-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="7d133-110">范围的结束地址。</span><span class="sxs-lookup"><span data-stu-id="7d133-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="7d133-111">数据的类型。</span><span class="sxs-lookup"><span data-stu-id="7d133-111">The type of the data.</span></span> <span data-ttu-id="7d133-112">当前未使用此值</span><span class="sxs-lookup"><span data-stu-id="7d133-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="7d133-113">备注</span><span class="sxs-lookup"><span data-stu-id="7d133-113">Remarks</span></span>

<span data-ttu-id="7d133-114">此结构存在于运行时中，并且不会通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="7d133-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="7d133-115">若要使用它，请定义上面指定的结构， `CLRDATA_ADDRESS`其中是一个64位无符号整数。</span><span class="sxs-lookup"><span data-stu-id="7d133-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="7d133-116">要求</span><span class="sxs-lookup"><span data-stu-id="7d133-116">Requirements</span></span>

<span data-ttu-id="7d133-117">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7d133-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="7d133-118">**标头：** None</span><span class="sxs-lookup"><span data-stu-id="7d133-118">**Header:** None</span></span>  
<span data-ttu-id="7d133-119">**类库**None</span><span class="sxs-lookup"><span data-stu-id="7d133-119">**Library:** None</span></span>   
<span data-ttu-id="7d133-120">**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7d133-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="7d133-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d133-121">See also</span></span>

- [<span data-ttu-id="7d133-122">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="7d133-122">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="7d133-123">调试</span><span class="sxs-lookup"><span data-stu-id="7d133-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="7d133-124">调试结构</span><span class="sxs-lookup"><span data-stu-id="7d133-124">Debugging Structures</span></span>](debugging-structures.md)
