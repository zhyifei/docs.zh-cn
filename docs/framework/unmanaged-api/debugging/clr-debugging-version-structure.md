---
title: CLR_DEBUGGING_VERSION 结构
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_VERSION
helpviewer_keywords:
- CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fecd5af43f4b984a4ab626e9832b3318715c0516
ms.sourcegitcommit: deb9225a55485a5a6e6c7914deb30ccfceb69d3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2019
ms.locfileid: "54058355"
---
# <a name="clrdebuggingversion-structure"></a><span data-ttu-id="175a1-102">CLR_DEBUGGING_VERSION 结构</span><span class="sxs-lookup"><span data-stu-id="175a1-102">CLR_DEBUGGING_VERSION Structure</span></span>
<span data-ttu-id="175a1-103">出于调试目的，定义公共语言运行时 (CLR) 的产品版本。</span><span class="sxs-lookup"><span data-stu-id="175a1-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="175a1-104">语法</span><span class="sxs-lookup"><span data-stu-id="175a1-104">Syntax</span></span>  
  
```  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a><span data-ttu-id="175a1-105">成员</span><span class="sxs-lookup"><span data-stu-id="175a1-105">Members</span></span>  
  
|<span data-ttu-id="175a1-106">成员</span><span class="sxs-lookup"><span data-stu-id="175a1-106">Member</span></span>|<span data-ttu-id="175a1-107">描述</span><span class="sxs-lookup"><span data-stu-id="175a1-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="175a1-108">结构版本数</span><span class="sxs-lookup"><span data-stu-id="175a1-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="175a1-109">主版本号。</span><span class="sxs-lookup"><span data-stu-id="175a1-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="175a1-110">次版本号。</span><span class="sxs-lookup"><span data-stu-id="175a1-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="175a1-111">内部版本号。</span><span class="sxs-lookup"><span data-stu-id="175a1-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="175a1-112">修订号。</span><span class="sxs-lookup"><span data-stu-id="175a1-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="175a1-113">备注</span><span class="sxs-lookup"><span data-stu-id="175a1-113">Remarks</span></span>  
 <span data-ttu-id="175a1-114">`CLR_DEBUGGING_VERSION`结构但是是 COR_VERSION 结构相同，则`CLR_DEBUGGING_VERSION`结构提供了其他结构版本字段 (`wStructVersion`)。</span><span class="sxs-lookup"><span data-stu-id="175a1-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="175a1-115">目前，此字段必须设置为零。</span><span class="sxs-lookup"><span data-stu-id="175a1-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="175a1-116">要求</span><span class="sxs-lookup"><span data-stu-id="175a1-116">Requirements</span></span>  
 <span data-ttu-id="175a1-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="175a1-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="175a1-118">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="175a1-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="175a1-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="175a1-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="175a1-120">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="175a1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="175a1-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="175a1-121">See Also</span></span>  
 [<span data-ttu-id="175a1-122">调试结构</span><span class="sxs-lookup"><span data-stu-id="175a1-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="175a1-123">调试</span><span class="sxs-lookup"><span data-stu-id="175a1-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
