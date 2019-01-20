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
ms.openlocfilehash: 36651de5053e994103f79c9021e8e18e126f91fa
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416288"
---
# <a name="clrdatasourcetype-enumeration"></a><span data-ttu-id="b00d4-102">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="b00d4-102">CLRDataSourceType Enumeration</span></span>

<span data-ttu-id="b00d4-103">提供使用 CLRDATA_IL_ADDRESS_MAP 结构的值。</span><span class="sxs-lookup"><span data-stu-id="b00d4-103">Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b00d4-104">语法</span><span class="sxs-lookup"><span data-stu-id="b00d4-104">Syntax</span></span>

```
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a><span data-ttu-id="b00d4-105">成员</span><span class="sxs-lookup"><span data-stu-id="b00d4-105">Members</span></span>

| <span data-ttu-id="b00d4-106">成员</span><span class="sxs-lookup"><span data-stu-id="b00d4-106">Member</span></span>                        | <span data-ttu-id="b00d4-107">描述</span><span class="sxs-lookup"><span data-stu-id="b00d4-107">Description</span></span>                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | <span data-ttu-id="b00d4-108">若要将指明没有其他应用</span><span class="sxs-lookup"><span data-stu-id="b00d4-108">To indicate that nothing else applies</span></span> |

## <a name="remarks"></a><span data-ttu-id="b00d4-109">备注</span><span class="sxs-lookup"><span data-stu-id="b00d4-109">Remarks</span></span>

<span data-ttu-id="b00d4-110">此枚举存在于运行时内，不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="b00d4-110">This enumeration lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="b00d4-111">若要使用它，定义枚举，如上面代码中定义。</span><span class="sxs-lookup"><span data-stu-id="b00d4-111">To use it, define an enumeration as defined above in your code.</span></span> <span data-ttu-id="b00d4-112">这也是对使用别名`CLRDATA_ENUM`中所述[常见数据类型](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="b00d4-112">This is also aliased to `CLRDATA_ENUM` as mentioned in [Common Data Types](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="b00d4-113">要求</span><span class="sxs-lookup"><span data-stu-id="b00d4-113">Requirements</span></span>

<span data-ttu-id="b00d4-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b00d4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b00d4-115">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="b00d4-115">**Header:** None</span></span>  
<span data-ttu-id="b00d4-116">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="b00d4-116">**Library:** None</span></span>  
<span data-ttu-id="b00d4-117">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b00d4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b00d4-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="b00d4-118">See Also</span></span>

- [<span data-ttu-id="b00d4-119">调试</span><span class="sxs-lookup"><span data-stu-id="b00d4-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="b00d4-120">调试枚举</span><span class="sxs-lookup"><span data-stu-id="b00d4-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
