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
ms.openlocfilehash: 87f938a7119abe4a88da65bd779a5f4a02499516
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117113"
---
# <a name="clrdebuggingversion-structure"></a><span data-ttu-id="d3563-102">CLR_DEBUGGING_VERSION 结构</span><span class="sxs-lookup"><span data-stu-id="d3563-102">CLR_DEBUGGING_VERSION Structure</span></span>
<span data-ttu-id="d3563-103">出于调试目的，定义公共语言运行时 (CLR) 的产品版本。</span><span class="sxs-lookup"><span data-stu-id="d3563-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3563-104">语法</span><span class="sxs-lookup"><span data-stu-id="d3563-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="d3563-105">成员</span><span class="sxs-lookup"><span data-stu-id="d3563-105">Members</span></span>  
  
|<span data-ttu-id="d3563-106">成员</span><span class="sxs-lookup"><span data-stu-id="d3563-106">Member</span></span>|<span data-ttu-id="d3563-107">描述</span><span class="sxs-lookup"><span data-stu-id="d3563-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="d3563-108">结构版本数</span><span class="sxs-lookup"><span data-stu-id="d3563-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="d3563-109">主版本号。</span><span class="sxs-lookup"><span data-stu-id="d3563-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="d3563-110">次版本号。</span><span class="sxs-lookup"><span data-stu-id="d3563-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="d3563-111">内部版本号。</span><span class="sxs-lookup"><span data-stu-id="d3563-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="d3563-112">修订号。</span><span class="sxs-lookup"><span data-stu-id="d3563-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3563-113">备注</span><span class="sxs-lookup"><span data-stu-id="d3563-113">Remarks</span></span>  
 <span data-ttu-id="d3563-114">`CLR_DEBUGGING_VERSION`结构但是是 COR_VERSION 结构相同，则`CLR_DEBUGGING_VERSION`结构提供了其他结构版本字段 (`wStructVersion`)。</span><span class="sxs-lookup"><span data-stu-id="d3563-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="d3563-115">目前，此字段必须设置为零。</span><span class="sxs-lookup"><span data-stu-id="d3563-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3563-116">要求</span><span class="sxs-lookup"><span data-stu-id="d3563-116">Requirements</span></span>  
 <span data-ttu-id="d3563-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d3563-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3563-118">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="d3563-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="d3563-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3563-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d3563-120">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="d3563-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d3563-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3563-121">See also</span></span>

- [<span data-ttu-id="d3563-122">调试结构</span><span class="sxs-lookup"><span data-stu-id="d3563-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="d3563-123">调试</span><span class="sxs-lookup"><span data-stu-id="d3563-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
