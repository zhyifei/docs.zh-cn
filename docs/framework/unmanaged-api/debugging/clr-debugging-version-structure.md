---
title: "CLR_DEBUGGING_VERSION 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLR_DEBUGGING_VERSION
api_location: mscordbi.dll
api_type: COM
f1_keywords: CLR_DEBUGGING_VERSION
helpviewer_keywords: CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 98124b7b9efb2c92ebee6b6e99f73edc6cf173a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="clrdebuggingversion-structure"></a><span data-ttu-id="35536-102">CLR_DEBUGGING_VERSION 结构</span><span class="sxs-lookup"><span data-stu-id="35536-102">CLR_DEBUGGING_VERSION Structure</span></span>
<span data-ttu-id="35536-103">出于调试目的，定义公共语言运行时 (CLR) 的产品版本。</span><span class="sxs-lookup"><span data-stu-id="35536-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35536-104">语法</span><span class="sxs-lookup"><span data-stu-id="35536-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="35536-105">成员</span><span class="sxs-lookup"><span data-stu-id="35536-105">Members</span></span>  
  
|<span data-ttu-id="35536-106">成员</span><span class="sxs-lookup"><span data-stu-id="35536-106">Member</span></span>|<span data-ttu-id="35536-107">描述</span><span class="sxs-lookup"><span data-stu-id="35536-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="35536-108">结构版本号</span><span class="sxs-lookup"><span data-stu-id="35536-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="35536-109">主版本号。</span><span class="sxs-lookup"><span data-stu-id="35536-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="35536-110">次版本号。</span><span class="sxs-lookup"><span data-stu-id="35536-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="35536-111">内部版本号。</span><span class="sxs-lookup"><span data-stu-id="35536-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="35536-112">修订号。</span><span class="sxs-lookup"><span data-stu-id="35536-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35536-113">备注</span><span class="sxs-lookup"><span data-stu-id="35536-113">Remarks</span></span>  
 <span data-ttu-id="35536-114">`CLR_DEBUGGING_VERSION`结构等同于 COR_VERSION 结构，但是，`CLR_DEBUGGING_VERSION`结构可提供其他结构版本字段 (`wStructVersion`)。</span><span class="sxs-lookup"><span data-stu-id="35536-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="35536-115">目前，此字段必须设置为零。</span><span class="sxs-lookup"><span data-stu-id="35536-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35536-116">要求</span><span class="sxs-lookup"><span data-stu-id="35536-116">Requirements</span></span>  
 <span data-ttu-id="35536-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="35536-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35536-118">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="35536-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="35536-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35536-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35536-120">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35536-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35536-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35536-121">See Also</span></span>  
 [<span data-ttu-id="35536-122">调试结构</span><span class="sxs-lookup"><span data-stu-id="35536-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="35536-123">调试</span><span class="sxs-lookup"><span data-stu-id="35536-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
