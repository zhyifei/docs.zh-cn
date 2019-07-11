---
title: COR_VERSION 结构
ms.date: 03/30/2017
api_name:
- COR_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_VERSION
helpviewer_keywords:
- COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1f0a36d186c6d9788d43b075bf9d67c36ed1acb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740565"
---
# <a name="corversion-structure"></a><span data-ttu-id="98411-102">COR_VERSION 结构</span><span class="sxs-lookup"><span data-stu-id="98411-102">COR_VERSION Structure</span></span>
<span data-ttu-id="98411-103">存储由四个部分组成的公共语言运行时标准版本号。</span><span class="sxs-lookup"><span data-stu-id="98411-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98411-104">语法</span><span class="sxs-lookup"><span data-stu-id="98411-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="98411-105">成员</span><span class="sxs-lookup"><span data-stu-id="98411-105">Members</span></span>  
  
|<span data-ttu-id="98411-106">成员</span><span class="sxs-lookup"><span data-stu-id="98411-106">Member</span></span>|<span data-ttu-id="98411-107">描述</span><span class="sxs-lookup"><span data-stu-id="98411-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="98411-108">主版本号。</span><span class="sxs-lookup"><span data-stu-id="98411-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="98411-109">次版本号。</span><span class="sxs-lookup"><span data-stu-id="98411-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="98411-110">内部版本号。</span><span class="sxs-lookup"><span data-stu-id="98411-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="98411-111">子内部版本号。</span><span class="sxs-lookup"><span data-stu-id="98411-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98411-112">备注</span><span class="sxs-lookup"><span data-stu-id="98411-112">Remarks</span></span>  
 <span data-ttu-id="98411-113">如果版本号为 1.0.3705.288，1 表示主版本号 0 的次版本号、 3705 是内部版本号，是 288 为子内部版本号。</span><span class="sxs-lookup"><span data-stu-id="98411-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98411-114">要求</span><span class="sxs-lookup"><span data-stu-id="98411-114">Requirements</span></span>  
 <span data-ttu-id="98411-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="98411-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98411-116">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="98411-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="98411-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98411-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98411-118">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98411-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98411-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="98411-119">See also</span></span>

- [<span data-ttu-id="98411-120">调试结构</span><span class="sxs-lookup"><span data-stu-id="98411-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="98411-121">调试</span><span class="sxs-lookup"><span data-stu-id="98411-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
