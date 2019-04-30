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
ms.openlocfilehash: bc36468a2016822e884ec3a36a23c75477a00a2d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045378"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="ce40e-102">CorSaveSize 枚举</span><span class="sxs-lookup"><span data-stu-id="ce40e-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="ce40e-103">包含一些值，用于指示查询保存操作的大小时所需的精度级别。</span><span class="sxs-lookup"><span data-stu-id="ce40e-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce40e-104">语法</span><span class="sxs-lookup"><span data-stu-id="ce40e-104">Syntax</span></span>  
  
```  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="ce40e-105">成员</span><span class="sxs-lookup"><span data-stu-id="ce40e-105">Members</span></span>  
  
|<span data-ttu-id="ce40e-106">成员</span><span class="sxs-lookup"><span data-stu-id="ce40e-106">Member</span></span>|<span data-ttu-id="ce40e-107">描述</span><span class="sxs-lookup"><span data-stu-id="ce40e-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="ce40e-108">指定返回值应为完全。</span><span class="sxs-lookup"><span data-stu-id="ce40e-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="ce40e-109">指定应估计的返回值。</span><span class="sxs-lookup"><span data-stu-id="ce40e-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="ce40e-110">指定应删除丢弃的类型。</span><span class="sxs-lookup"><span data-stu-id="ce40e-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ce40e-111">要求</span><span class="sxs-lookup"><span data-stu-id="ce40e-111">Requirements</span></span>  
 <span data-ttu-id="ce40e-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ce40e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce40e-113">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ce40e-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ce40e-114">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ce40e-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ce40e-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce40e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce40e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce40e-116">See also</span></span>

- [<span data-ttu-id="ce40e-117">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="ce40e-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
