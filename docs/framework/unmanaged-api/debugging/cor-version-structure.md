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
ms.openlocfilehash: e07487f536454d9d2dcfff15eb871124112d250e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634938"
---
# <a name="corversion-structure"></a><span data-ttu-id="f681f-102">COR_VERSION 结构</span><span class="sxs-lookup"><span data-stu-id="f681f-102">COR_VERSION Structure</span></span>
<span data-ttu-id="f681f-103">存储由四个部分组成的公共语言运行时标准版本号。</span><span class="sxs-lookup"><span data-stu-id="f681f-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f681f-104">语法</span><span class="sxs-lookup"><span data-stu-id="f681f-104">Syntax</span></span>  
  
```  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="f681f-105">成员</span><span class="sxs-lookup"><span data-stu-id="f681f-105">Members</span></span>  
  
|<span data-ttu-id="f681f-106">成员</span><span class="sxs-lookup"><span data-stu-id="f681f-106">Member</span></span>|<span data-ttu-id="f681f-107">描述</span><span class="sxs-lookup"><span data-stu-id="f681f-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="f681f-108">主版本号。</span><span class="sxs-lookup"><span data-stu-id="f681f-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="f681f-109">次版本号。</span><span class="sxs-lookup"><span data-stu-id="f681f-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="f681f-110">内部版本号。</span><span class="sxs-lookup"><span data-stu-id="f681f-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="f681f-111">子内部版本号。</span><span class="sxs-lookup"><span data-stu-id="f681f-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f681f-112">备注</span><span class="sxs-lookup"><span data-stu-id="f681f-112">Remarks</span></span>  
 <span data-ttu-id="f681f-113">如果版本号为 1.0.3705.288，1 表示主版本号 0 的次版本号、 3705 是内部版本号，是 288 为子内部版本号。</span><span class="sxs-lookup"><span data-stu-id="f681f-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f681f-114">要求</span><span class="sxs-lookup"><span data-stu-id="f681f-114">Requirements</span></span>  
 <span data-ttu-id="f681f-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f681f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f681f-116">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="f681f-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="f681f-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f681f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f681f-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f681f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f681f-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="f681f-119">See also</span></span>
- [<span data-ttu-id="f681f-120">调试结构</span><span class="sxs-lookup"><span data-stu-id="f681f-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="f681f-121">调试</span><span class="sxs-lookup"><span data-stu-id="f681f-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
