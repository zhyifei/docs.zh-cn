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
ms.openlocfilehash: c8b3f338659e2784db8deca3e1776e7926c30c32
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506078"
---
# <a name="clrdatasourcetype-enumeration"></a><span data-ttu-id="9743b-102">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="9743b-102">CLRDataSourceType Enumeration</span></span>

<span data-ttu-id="9743b-103">提供使用 CLRDATA_IL_ADDRESS_MAP 结构的值。</span><span class="sxs-lookup"><span data-stu-id="9743b-103">Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9743b-104">语法</span><span class="sxs-lookup"><span data-stu-id="9743b-104">Syntax</span></span>

```
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a><span data-ttu-id="9743b-105">成员</span><span class="sxs-lookup"><span data-stu-id="9743b-105">Members</span></span>

| <span data-ttu-id="9743b-106">成员</span><span class="sxs-lookup"><span data-stu-id="9743b-106">Member</span></span>                        | <span data-ttu-id="9743b-107">描述</span><span class="sxs-lookup"><span data-stu-id="9743b-107">Description</span></span>                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | <span data-ttu-id="9743b-108">若要将指明没有其他应用</span><span class="sxs-lookup"><span data-stu-id="9743b-108">To indicate that nothing else applies</span></span> |

## <a name="remarks"></a><span data-ttu-id="9743b-109">备注</span><span class="sxs-lookup"><span data-stu-id="9743b-109">Remarks</span></span>

<span data-ttu-id="9743b-110">此枚举存在于运行时内，不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="9743b-110">This enumeration lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="9743b-111">若要使用它，定义枚举，如上面代码中定义。</span><span class="sxs-lookup"><span data-stu-id="9743b-111">To use it, define an enumeration as defined above in your code.</span></span> <span data-ttu-id="9743b-112">这也是对使用别名`CLRDATA_ENUM`中所述[常见数据类型](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="9743b-112">This is also aliased to `CLRDATA_ENUM` as mentioned in [Common Data Types](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="9743b-113">要求</span><span class="sxs-lookup"><span data-stu-id="9743b-113">Requirements</span></span>

<span data-ttu-id="9743b-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9743b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9743b-115">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="9743b-115">**Header:** None</span></span>  
<span data-ttu-id="9743b-116">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="9743b-116">**Library:** None</span></span>  
<span data-ttu-id="9743b-117">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9743b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9743b-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="9743b-118">See also</span></span>

- [<span data-ttu-id="9743b-119">调试</span><span class="sxs-lookup"><span data-stu-id="9743b-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="9743b-120">调试枚举</span><span class="sxs-lookup"><span data-stu-id="9743b-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
