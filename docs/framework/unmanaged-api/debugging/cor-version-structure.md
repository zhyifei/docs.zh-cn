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
ms.openlocfilehash: 00e58d83c19c3cb6a2e1eb38942500d7f5dc5cf9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118919"
---
# <a name="corversion-structure"></a><span data-ttu-id="620d9-102">COR_VERSION 结构</span><span class="sxs-lookup"><span data-stu-id="620d9-102">COR_VERSION Structure</span></span>
<span data-ttu-id="620d9-103">存储由四个部分组成的公共语言运行时标准版本号。</span><span class="sxs-lookup"><span data-stu-id="620d9-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="620d9-104">语法</span><span class="sxs-lookup"><span data-stu-id="620d9-104">Syntax</span></span>  
  
```  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="620d9-105">成员</span><span class="sxs-lookup"><span data-stu-id="620d9-105">Members</span></span>  
  
|<span data-ttu-id="620d9-106">成员</span><span class="sxs-lookup"><span data-stu-id="620d9-106">Member</span></span>|<span data-ttu-id="620d9-107">描述</span><span class="sxs-lookup"><span data-stu-id="620d9-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="620d9-108">主版本号。</span><span class="sxs-lookup"><span data-stu-id="620d9-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="620d9-109">次版本号。</span><span class="sxs-lookup"><span data-stu-id="620d9-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="620d9-110">内部版本号。</span><span class="sxs-lookup"><span data-stu-id="620d9-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="620d9-111">子内部版本号。</span><span class="sxs-lookup"><span data-stu-id="620d9-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="620d9-112">备注</span><span class="sxs-lookup"><span data-stu-id="620d9-112">Remarks</span></span>  
 <span data-ttu-id="620d9-113">如果版本号为 1.0.3705.288，1 表示主版本号 0 的次版本号、 3705 是内部版本号，是 288 为子内部版本号。</span><span class="sxs-lookup"><span data-stu-id="620d9-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="620d9-114">要求</span><span class="sxs-lookup"><span data-stu-id="620d9-114">Requirements</span></span>  
 <span data-ttu-id="620d9-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="620d9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="620d9-116">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="620d9-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="620d9-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="620d9-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="620d9-118">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="620d9-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="620d9-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="620d9-119">See also</span></span>

- [<span data-ttu-id="620d9-120">调试结构</span><span class="sxs-lookup"><span data-stu-id="620d9-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="620d9-121">调试</span><span class="sxs-lookup"><span data-stu-id="620d9-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
