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
ms.openlocfilehash: 7ace405e2624f15b1cdb6d383222ae87c93289bb
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274099"
---
# <a name="clrdatasourcetype-enumeration"></a><span data-ttu-id="3ccfe-102">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="3ccfe-102">CLRDataSourceType Enumeration</span></span>

<span data-ttu-id="3ccfe-103">提供 CLRDATA_IL_ADDRESS_MAP 结构使用的值。</span><span class="sxs-lookup"><span data-stu-id="3ccfe-103">Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="3ccfe-104">语法</span><span class="sxs-lookup"><span data-stu-id="3ccfe-104">Syntax</span></span>

```cpp
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a><span data-ttu-id="3ccfe-105">成员</span><span class="sxs-lookup"><span data-stu-id="3ccfe-105">Members</span></span>

| <span data-ttu-id="3ccfe-106">成员</span><span class="sxs-lookup"><span data-stu-id="3ccfe-106">Member</span></span>                        | <span data-ttu-id="3ccfe-107">描述</span><span class="sxs-lookup"><span data-stu-id="3ccfe-107">Description</span></span>                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | <span data-ttu-id="3ccfe-108">指示无其他应用</span><span class="sxs-lookup"><span data-stu-id="3ccfe-108">To indicate that nothing else applies</span></span> |

## <a name="remarks"></a><span data-ttu-id="3ccfe-109">备注</span><span class="sxs-lookup"><span data-stu-id="3ccfe-109">Remarks</span></span>

<span data-ttu-id="3ccfe-110">此枚举位于运行时中，并且不会通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="3ccfe-110">This enumeration lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="3ccfe-111">若要使用它，请在代码中定义上面定义的枚举。</span><span class="sxs-lookup"><span data-stu-id="3ccfe-111">To use it, define an enumeration as defined above in your code.</span></span> <span data-ttu-id="3ccfe-112">这也会化名为`CLRDATA_ENUM` ，如[常用数据类型](../common-data-types-unmanaged-api-reference.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="3ccfe-112">This is also aliased to `CLRDATA_ENUM` as mentioned in [Common Data Types](../common-data-types-unmanaged-api-reference.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="3ccfe-113">要求</span><span class="sxs-lookup"><span data-stu-id="3ccfe-113">Requirements</span></span>

<span data-ttu-id="3ccfe-114">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3ccfe-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="3ccfe-115">**标头：** None</span><span class="sxs-lookup"><span data-stu-id="3ccfe-115">**Header:** None</span></span>  
<span data-ttu-id="3ccfe-116">**类库**None</span><span class="sxs-lookup"><span data-stu-id="3ccfe-116">**Library:** None</span></span>  
<span data-ttu-id="3ccfe-117">**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3ccfe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3ccfe-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ccfe-118">See also</span></span>

- [<span data-ttu-id="3ccfe-119">调试</span><span class="sxs-lookup"><span data-stu-id="3ccfe-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="3ccfe-120">调试枚举</span><span class="sxs-lookup"><span data-stu-id="3ccfe-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
