---
title: "COR_VERSION 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_VERSION
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_VERSION
helpviewer_keywords: COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bd4a878b51685befb39eb486097be2e2f2c1d409
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="corversion-structure"></a><span data-ttu-id="b0da5-102">COR_VERSION 结构</span><span class="sxs-lookup"><span data-stu-id="b0da5-102">COR_VERSION Structure</span></span>
<span data-ttu-id="b0da5-103">存储由四个部分组成的公共语言运行时标准版本号。</span><span class="sxs-lookup"><span data-stu-id="b0da5-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0da5-104">语法</span><span class="sxs-lookup"><span data-stu-id="b0da5-104">Syntax</span></span>  
  
```  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="b0da5-105">成员</span><span class="sxs-lookup"><span data-stu-id="b0da5-105">Members</span></span>  
  
|<span data-ttu-id="b0da5-106">成员</span><span class="sxs-lookup"><span data-stu-id="b0da5-106">Member</span></span>|<span data-ttu-id="b0da5-107">描述</span><span class="sxs-lookup"><span data-stu-id="b0da5-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="b0da5-108">主版本号。</span><span class="sxs-lookup"><span data-stu-id="b0da5-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="b0da5-109">次版本号。</span><span class="sxs-lookup"><span data-stu-id="b0da5-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="b0da5-110">内部版本号。</span><span class="sxs-lookup"><span data-stu-id="b0da5-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="b0da5-111">子内部版本号。</span><span class="sxs-lookup"><span data-stu-id="b0da5-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0da5-112">备注</span><span class="sxs-lookup"><span data-stu-id="b0da5-112">Remarks</span></span>  
 <span data-ttu-id="b0da5-113">版本号是否 1.0.3705.288，1 是主版本号、 0 是次要版本号，、 3705 为内部版本号，和 288 为子内部版本号。</span><span class="sxs-lookup"><span data-stu-id="b0da5-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0da5-114">要求</span><span class="sxs-lookup"><span data-stu-id="b0da5-114">Requirements</span></span>  
 <span data-ttu-id="b0da5-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b0da5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0da5-116">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="b0da5-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="b0da5-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0da5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0da5-118">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0da5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0da5-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0da5-119">See Also</span></span>  
 [<span data-ttu-id="b0da5-120">调试结构</span><span class="sxs-lookup"><span data-stu-id="b0da5-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="b0da5-121">调试</span><span class="sxs-lookup"><span data-stu-id="b0da5-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
