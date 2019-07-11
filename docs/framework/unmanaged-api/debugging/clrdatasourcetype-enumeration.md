---
title: CLRDataSourceType 枚举
ms.date: 01/16/2019
api.name:
- CLRDataSourceType Enumeration
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDataSourceType Enumeration
helpviewer.keywords:
- CLRDataSourceType Enumeration [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: d26cf45a0243d61757af5d9d0c00cf135ae15bdf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740865"
---
# <a name="clrdatasourcetype-enumeration"></a><span data-ttu-id="d646c-102">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="d646c-102">CLRDataSourceType Enumeration</span></span>

<span data-ttu-id="d646c-103">提供使用 CLRDATA_IL_ADDRESS_MAP 结构的值。</span><span class="sxs-lookup"><span data-stu-id="d646c-103">Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="d646c-104">语法</span><span class="sxs-lookup"><span data-stu-id="d646c-104">Syntax</span></span>

```cpp
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a><span data-ttu-id="d646c-105">成员</span><span class="sxs-lookup"><span data-stu-id="d646c-105">Members</span></span>

| <span data-ttu-id="d646c-106">成员</span><span class="sxs-lookup"><span data-stu-id="d646c-106">Member</span></span>                        | <span data-ttu-id="d646c-107">描述</span><span class="sxs-lookup"><span data-stu-id="d646c-107">Description</span></span>                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | <span data-ttu-id="d646c-108">若要将指明没有其他应用</span><span class="sxs-lookup"><span data-stu-id="d646c-108">To indicate that nothing else applies</span></span> |

## <a name="remarks"></a><span data-ttu-id="d646c-109">备注</span><span class="sxs-lookup"><span data-stu-id="d646c-109">Remarks</span></span>

<span data-ttu-id="d646c-110">此枚举存在于运行时内，不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="d646c-110">This enumeration lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="d646c-111">若要使用它，定义枚举，如上面代码中定义。</span><span class="sxs-lookup"><span data-stu-id="d646c-111">To use it, define an enumeration as defined above in your code.</span></span> <span data-ttu-id="d646c-112">这也是对使用别名`CLRDATA_ENUM`中所述[常见数据类型](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="d646c-112">This is also aliased to `CLRDATA_ENUM` as mentioned in [Common Data Types](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="d646c-113">要求</span><span class="sxs-lookup"><span data-stu-id="d646c-113">Requirements</span></span>

<span data-ttu-id="d646c-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d646c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d646c-115">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="d646c-115">**Header:** None</span></span>  
<span data-ttu-id="d646c-116">**库：** None</span><span class="sxs-lookup"><span data-stu-id="d646c-116">**Library:** None</span></span>  
<span data-ttu-id="d646c-117">**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d646c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d646c-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d646c-118">See also</span></span>

- [<span data-ttu-id="d646c-119">调试</span><span class="sxs-lookup"><span data-stu-id="d646c-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="d646c-120">调试枚举</span><span class="sxs-lookup"><span data-stu-id="d646c-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
