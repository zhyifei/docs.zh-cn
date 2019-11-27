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
ms.openlocfilehash: 0f870d9d7d1bc292b213d690df508a6c28bac2ab
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450095"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="58f41-102">CorSaveSize 枚举</span><span class="sxs-lookup"><span data-stu-id="58f41-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="58f41-103">包含一些值，用于指示查询保存操作的大小时所需的精度级别。</span><span class="sxs-lookup"><span data-stu-id="58f41-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58f41-104">语法</span><span class="sxs-lookup"><span data-stu-id="58f41-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="58f41-105">Members</span><span class="sxs-lookup"><span data-stu-id="58f41-105">Members</span></span>  
  
|<span data-ttu-id="58f41-106">成员</span><span class="sxs-lookup"><span data-stu-id="58f41-106">Member</span></span>|<span data-ttu-id="58f41-107">说明</span><span class="sxs-lookup"><span data-stu-id="58f41-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="58f41-108">指定返回值应是精确的。</span><span class="sxs-lookup"><span data-stu-id="58f41-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="58f41-109">指定应估算返回值。</span><span class="sxs-lookup"><span data-stu-id="58f41-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="58f41-110">指定应删除可放弃类型。</span><span class="sxs-lookup"><span data-stu-id="58f41-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="58f41-111">要求</span><span class="sxs-lookup"><span data-stu-id="58f41-111">Requirements</span></span>  
 <span data-ttu-id="58f41-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="58f41-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58f41-113">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="58f41-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="58f41-114">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="58f41-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="58f41-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58f41-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58f41-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58f41-116">See also</span></span>

- [<span data-ttu-id="58f41-117">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="58f41-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
