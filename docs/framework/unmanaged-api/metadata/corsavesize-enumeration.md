---
title: CorSaveSize 枚举
ms.date: 03/30/2017
api_name:
- CorSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSaveSize
helpviewer_keywords:
- CorSaveSize enumeration [.NET Framework metadata]
ms.assetid: eb95ce39-5688-43c1-a34d-578794b32faa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66f9f95b0cf19acb677daf7f7401d21cc81864a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447602"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="0a058-102">CorSaveSize 枚举</span><span class="sxs-lookup"><span data-stu-id="0a058-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="0a058-103">包含一些值，用于指示查询保存操作的大小时所需的精度级别。</span><span class="sxs-lookup"><span data-stu-id="0a058-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a058-104">语法</span><span class="sxs-lookup"><span data-stu-id="0a058-104">Syntax</span></span>  
  
```  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="0a058-105">成员</span><span class="sxs-lookup"><span data-stu-id="0a058-105">Members</span></span>  
  
|<span data-ttu-id="0a058-106">成员</span><span class="sxs-lookup"><span data-stu-id="0a058-106">Member</span></span>|<span data-ttu-id="0a058-107">描述</span><span class="sxs-lookup"><span data-stu-id="0a058-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="0a058-108">指定返回值应是准确。</span><span class="sxs-lookup"><span data-stu-id="0a058-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="0a058-109">指定应估计的返回值。</span><span class="sxs-lookup"><span data-stu-id="0a058-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="0a058-110">指定应删除丢弃的类型。</span><span class="sxs-lookup"><span data-stu-id="0a058-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0a058-111">要求</span><span class="sxs-lookup"><span data-stu-id="0a058-111">Requirements</span></span>  
 <span data-ttu-id="0a058-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0a058-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a058-113">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="0a058-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="0a058-114">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0a058-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0a058-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a058-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a058-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a058-116">See Also</span></span>  
 [<span data-ttu-id="0a058-117">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="0a058-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
