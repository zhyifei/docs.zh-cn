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
ms.openlocfilehash: b46a04d67f59c5031b5bd195cef4cc2275e1e5e0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793799"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="9e634-102">DacpModuleData 结构</span><span class="sxs-lookup"><span data-stu-id="9e634-102">DacpModuleData Structure</span></span>

<span data-ttu-id="9e634-103">定义模块的运行时信息的传输缓冲区。</span><span class="sxs-lookup"><span data-stu-id="9e634-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9e634-104">语法</span><span class="sxs-lookup"><span data-stu-id="9e634-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File; 
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="9e634-105">Members</span><span class="sxs-lookup"><span data-stu-id="9e634-105">Members</span></span>

| <span data-ttu-id="9e634-106">成员</span><span class="sxs-lookup"><span data-stu-id="9e634-106">Member</span></span>    | <span data-ttu-id="9e634-107">描述</span><span class="sxs-lookup"><span data-stu-id="9e634-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="9e634-108">Module 对象的地址。</span><span class="sxs-lookup"><span data-stu-id="9e634-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="9e634-109">指向可移植可执行（PE）文件的指针。</span><span class="sxs-lookup"><span data-stu-id="9e634-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="9e634-110">加载的映像的基址。</span><span class="sxs-lookup"><span data-stu-id="9e634-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="9e634-111">运行时使用的其他模块信息的负载缓冲区。</span><span class="sxs-lookup"><span data-stu-id="9e634-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="9e634-112">备注</span><span class="sxs-lookup"><span data-stu-id="9e634-112">Remarks</span></span>

<span data-ttu-id="9e634-113">此结构存在于运行时中，并且不会通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="9e634-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="9e634-114">若要使用它，请定义上面指定的结构。</span><span class="sxs-lookup"><span data-stu-id="9e634-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="9e634-115">需求</span><span class="sxs-lookup"><span data-stu-id="9e634-115">Requirements</span></span>
<span data-ttu-id="9e634-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9e634-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9e634-117">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="9e634-117">**Header:** None</span></span>  
<span data-ttu-id="9e634-118">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="9e634-118">**Library:** None</span></span>  
<span data-ttu-id="9e634-119">**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9e634-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9e634-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e634-120">See also</span></span>

- [<span data-ttu-id="9e634-121">调试</span><span class="sxs-lookup"><span data-stu-id="9e634-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="9e634-122">调试结构</span><span class="sxs-lookup"><span data-stu-id="9e634-122">Debugging Structures</span></span>](debugging-structures.md)
