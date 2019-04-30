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
ms.openlocfilehash: 752d87c5f4a6b8d854a06be8962ee754cdd4622d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965953"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="d1164-102">DacpModuleData 结构</span><span class="sxs-lookup"><span data-stu-id="d1164-102">DacpModuleData Structure</span></span>

<span data-ttu-id="d1164-103">定义模块的运行时信息的传输缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d1164-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="d1164-104">语法</span><span class="sxs-lookup"><span data-stu-id="d1164-104">Syntax</span></span>

```
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File; 
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="d1164-105">成员</span><span class="sxs-lookup"><span data-stu-id="d1164-105">Members</span></span>

| <span data-ttu-id="d1164-106">成员</span><span class="sxs-lookup"><span data-stu-id="d1164-106">Member</span></span>    | <span data-ttu-id="d1164-107">描述</span><span class="sxs-lookup"><span data-stu-id="d1164-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="d1164-108">模块对象的地址。</span><span class="sxs-lookup"><span data-stu-id="d1164-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="d1164-109">指向可移植可执行 (PE) 文件的指针。</span><span class="sxs-lookup"><span data-stu-id="d1164-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="d1164-110">地址加载映像的基。</span><span class="sxs-lookup"><span data-stu-id="d1164-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="d1164-111">运行时使用的其他模块信息有效负载缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d1164-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d1164-112">备注</span><span class="sxs-lookup"><span data-stu-id="d1164-112">Remarks</span></span>

<span data-ttu-id="d1164-113">此结构存在于运行时内，不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="d1164-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="d1164-114">若要使用它，如上所示定义的结构。</span><span class="sxs-lookup"><span data-stu-id="d1164-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="d1164-115">要求</span><span class="sxs-lookup"><span data-stu-id="d1164-115">Requirements</span></span>
<span data-ttu-id="d1164-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d1164-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d1164-117">**标头：** None</span><span class="sxs-lookup"><span data-stu-id="d1164-117">**Header:** None</span></span>  
<span data-ttu-id="d1164-118">**库：** None</span><span class="sxs-lookup"><span data-stu-id="d1164-118">**Library:** None</span></span>  
<span data-ttu-id="d1164-119">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d1164-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d1164-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1164-120">See also</span></span>

- [<span data-ttu-id="d1164-121">调试</span><span class="sxs-lookup"><span data-stu-id="d1164-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="d1164-122">调试结构</span><span class="sxs-lookup"><span data-stu-id="d1164-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
