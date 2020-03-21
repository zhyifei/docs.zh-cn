---
title: DacpModuleData 结构
ms.date: 02/01/2019
api.name:
- DacpModuleData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpModuleData Structure
helpviewer.keywords:
- DacpModuleData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: c24bdce64eb7e208bf3830940d7beab1ebf92e78
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179192"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="1a8b4-102">DacpModuleData 结构</span><span class="sxs-lookup"><span data-stu-id="1a8b4-102">DacpModuleData Structure</span></span>

<span data-ttu-id="1a8b4-103">为模块的运行时信息定义传输缓冲区。</span><span class="sxs-lookup"><span data-stu-id="1a8b4-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="1a8b4-104">语法</span><span class="sxs-lookup"><span data-stu-id="1a8b4-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File;
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="1a8b4-105">成员</span><span class="sxs-lookup"><span data-stu-id="1a8b4-105">Members</span></span>

| <span data-ttu-id="1a8b4-106">成员</span><span class="sxs-lookup"><span data-stu-id="1a8b4-106">Member</span></span>    | <span data-ttu-id="1a8b4-107">说明</span><span class="sxs-lookup"><span data-stu-id="1a8b4-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="1a8b4-108">模块对象的地址。</span><span class="sxs-lookup"><span data-stu-id="1a8b4-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="1a8b4-109">指向可移植可执行文件 （PE） 文件的指针。</span><span class="sxs-lookup"><span data-stu-id="1a8b4-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="1a8b4-110">加载图像的基的地址。</span><span class="sxs-lookup"><span data-stu-id="1a8b4-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="1a8b4-111">用于运行时使用的其他模块信息的有效负载缓冲区。</span><span class="sxs-lookup"><span data-stu-id="1a8b4-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="1a8b4-112">备注</span><span class="sxs-lookup"><span data-stu-id="1a8b4-112">Remarks</span></span>

<span data-ttu-id="1a8b4-113">此结构位于运行时内，不会通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="1a8b4-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="1a8b4-114">要使用它，请定义上面指定的结构。</span><span class="sxs-lookup"><span data-stu-id="1a8b4-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="1a8b4-115">要求</span><span class="sxs-lookup"><span data-stu-id="1a8b4-115">Requirements</span></span>
<span data-ttu-id="1a8b4-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1a8b4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="1a8b4-117">**标题：** 没有</span><span class="sxs-lookup"><span data-stu-id="1a8b4-117">**Header:** None</span></span>  
<span data-ttu-id="1a8b4-118">**库：** 没有</span><span class="sxs-lookup"><span data-stu-id="1a8b4-118">**Library:** None</span></span>  
<span data-ttu-id="1a8b4-119">**.NET 框架版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1a8b4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1a8b4-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a8b4-120">See also</span></span>

- [<span data-ttu-id="1a8b4-121">调试</span><span class="sxs-lookup"><span data-stu-id="1a8b4-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="1a8b4-122">调试结构</span><span class="sxs-lookup"><span data-stu-id="1a8b4-122">Debugging Structures</span></span>](debugging-structures.md)
