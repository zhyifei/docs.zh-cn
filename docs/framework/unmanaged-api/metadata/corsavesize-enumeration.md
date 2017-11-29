---
title: "CorSaveSize 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSaveSize
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSaveSize
helpviewer_keywords: CorSaveSize enumeration [.NET Framework metadata]
ms.assetid: eb95ce39-5688-43c1-a34d-578794b32faa
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 34d4d42c7cf385bca77de37dce52689778aa5b1f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="6cb66-102">CorSaveSize 枚举</span><span class="sxs-lookup"><span data-stu-id="6cb66-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="6cb66-103">包含一些值，用于指示查询保存操作的大小时所需的精度级别。</span><span class="sxs-lookup"><span data-stu-id="6cb66-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cb66-104">语法</span><span class="sxs-lookup"><span data-stu-id="6cb66-104">Syntax</span></span>  
  
```  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="6cb66-105">成员</span><span class="sxs-lookup"><span data-stu-id="6cb66-105">Members</span></span>  
  
|<span data-ttu-id="6cb66-106">成员</span><span class="sxs-lookup"><span data-stu-id="6cb66-106">Member</span></span>|<span data-ttu-id="6cb66-107">描述</span><span class="sxs-lookup"><span data-stu-id="6cb66-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="6cb66-108">指定返回值应是准确。</span><span class="sxs-lookup"><span data-stu-id="6cb66-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="6cb66-109">指定应估计的返回值。</span><span class="sxs-lookup"><span data-stu-id="6cb66-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="6cb66-110">指定应删除丢弃的类型。</span><span class="sxs-lookup"><span data-stu-id="6cb66-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6cb66-111">要求</span><span class="sxs-lookup"><span data-stu-id="6cb66-111">Requirements</span></span>  
 <span data-ttu-id="6cb66-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6cb66-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cb66-113">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="6cb66-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6cb66-114">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6cb66-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6cb66-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cb66-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cb66-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6cb66-116">See Also</span></span>  
 [<span data-ttu-id="6cb66-117">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="6cb66-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
