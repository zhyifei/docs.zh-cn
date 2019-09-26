---
title: COR_PUB_ENUMPROCESS 枚举
ms.date: 03/30/2017
api_name:
- COR_PUB_ENUMPROCESS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_PUB_ENUMPROCESS
helpviewer_keywords:
- COR_PUB_ENUMPROCESS enumeration [.NET Framework debugging]
ms.assetid: 5d3ada6e-feea-47da-a7ed-b664107c137f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eab5fc13b74d8af4f0baaa3953c5c73ea255bfe6
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274025"
---
# <a name="cor_pub_enumprocess-enumeration"></a><span data-ttu-id="031f3-102">COR_PUB_ENUMPROCESS 枚举</span><span class="sxs-lookup"><span data-stu-id="031f3-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="031f3-103">标识要枚举的进程的类型。</span><span class="sxs-lookup"><span data-stu-id="031f3-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="031f3-104">语法</span><span class="sxs-lookup"><span data-stu-id="031f3-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="031f3-105">成员</span><span class="sxs-lookup"><span data-stu-id="031f3-105">Members</span></span>  
  
|<span data-ttu-id="031f3-106">成员名称</span><span class="sxs-lookup"><span data-stu-id="031f3-106">Member name</span></span>|<span data-ttu-id="031f3-107">描述</span><span class="sxs-lookup"><span data-stu-id="031f3-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="031f3-108">托管进程。</span><span class="sxs-lookup"><span data-stu-id="031f3-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="031f3-109">备注</span><span class="sxs-lookup"><span data-stu-id="031f3-109">Remarks</span></span>  
 <span data-ttu-id="031f3-110">非托管调试 API 的当前版本仅枚举托管进程。</span><span class="sxs-lookup"><span data-stu-id="031f3-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="031f3-111">要求</span><span class="sxs-lookup"><span data-stu-id="031f3-111">Requirements</span></span>  
 <span data-ttu-id="031f3-112">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="031f3-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="031f3-113">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="031f3-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="031f3-114">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="031f3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="031f3-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="031f3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="031f3-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="031f3-116">See also</span></span>

- [<span data-ttu-id="031f3-117">调试枚举</span><span class="sxs-lookup"><span data-stu-id="031f3-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
