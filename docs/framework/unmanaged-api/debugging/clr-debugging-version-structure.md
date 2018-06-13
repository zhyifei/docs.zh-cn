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
ms.openlocfilehash: 4be232ab557d582f3521b8775108c004b5a3dd78
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403300"
---
# <a name="clrdebuggingversion-structure"></a><span data-ttu-id="e5a21-102">CLR_DEBUGGING_VERSION 结构</span><span class="sxs-lookup"><span data-stu-id="e5a21-102">CLR_DEBUGGING_VERSION Structure</span></span>
<span data-ttu-id="e5a21-103">出于调试目的，定义公共语言运行时 (CLR) 的产品版本。</span><span class="sxs-lookup"><span data-stu-id="e5a21-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5a21-104">语法</span><span class="sxs-lookup"><span data-stu-id="e5a21-104">Syntax</span></span>  
  
```  
Typedef struct _CLR_DEBUGGING_VERSION  
{  
WORD wStructVersion;  
WORD wMajor;   
WORD wMinor;  
WORD wBuild;  
WORD wRevision;  
}  CLR_DEBUGGING_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="e5a21-105">成员</span><span class="sxs-lookup"><span data-stu-id="e5a21-105">Members</span></span>  
  
|<span data-ttu-id="e5a21-106">成员</span><span class="sxs-lookup"><span data-stu-id="e5a21-106">Member</span></span>|<span data-ttu-id="e5a21-107">描述</span><span class="sxs-lookup"><span data-stu-id="e5a21-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="e5a21-108">结构版本号</span><span class="sxs-lookup"><span data-stu-id="e5a21-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="e5a21-109">主版本号。</span><span class="sxs-lookup"><span data-stu-id="e5a21-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="e5a21-110">次版本号。</span><span class="sxs-lookup"><span data-stu-id="e5a21-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="e5a21-111">内部版本号。</span><span class="sxs-lookup"><span data-stu-id="e5a21-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="e5a21-112">修订号。</span><span class="sxs-lookup"><span data-stu-id="e5a21-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5a21-113">备注</span><span class="sxs-lookup"><span data-stu-id="e5a21-113">Remarks</span></span>  
 <span data-ttu-id="e5a21-114">`CLR_DEBUGGING_VERSION`结构等同于 COR_VERSION 结构，但是，`CLR_DEBUGGING_VERSION`结构可提供其他结构版本字段 (`wStructVersion`)。</span><span class="sxs-lookup"><span data-stu-id="e5a21-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="e5a21-115">目前，此字段必须设置为零。</span><span class="sxs-lookup"><span data-stu-id="e5a21-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5a21-116">要求</span><span class="sxs-lookup"><span data-stu-id="e5a21-116">Requirements</span></span>  
 <span data-ttu-id="e5a21-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e5a21-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5a21-118">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="e5a21-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="e5a21-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5a21-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5a21-120">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5a21-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5a21-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5a21-121">See Also</span></span>  
 [<span data-ttu-id="e5a21-122">调试结构</span><span class="sxs-lookup"><span data-stu-id="e5a21-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="e5a21-123">调试</span><span class="sxs-lookup"><span data-stu-id="e5a21-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
