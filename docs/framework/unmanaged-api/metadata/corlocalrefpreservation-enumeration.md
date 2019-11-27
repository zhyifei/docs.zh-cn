---
title: CorLocalRefPreservation 枚举
ms.date: 03/30/2017
api_name:
- CorLocalRefPreservation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLocalRefPreservation
helpviewer_keywords:
- CorLocalRefPreservation enumeration [.NET Framework metadata]
ms.assetid: 44757163-1228-4213-a4c4-d4de503cc75d
topic_type:
- apiref
ms.openlocfilehash: 706ea37101f9f961e92d8cef2cf508c1dd0d56c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450239"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="73006-102">CorLocalRefPreservation 枚举</span><span class="sxs-lookup"><span data-stu-id="73006-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="73006-103">包含用于处理本地引用的标志值。</span><span class="sxs-lookup"><span data-stu-id="73006-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73006-104">语法</span><span class="sxs-lookup"><span data-stu-id="73006-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="73006-105">Members</span><span class="sxs-lookup"><span data-stu-id="73006-105">Members</span></span>  
  
|<span data-ttu-id="73006-106">成员</span><span class="sxs-lookup"><span data-stu-id="73006-106">Member</span></span>|<span data-ttu-id="73006-107">说明</span><span class="sxs-lookup"><span data-stu-id="73006-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="73006-108">不保留本地引用。</span><span class="sxs-lookup"><span data-stu-id="73006-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="73006-109">保留本地类型引用。</span><span class="sxs-lookup"><span data-stu-id="73006-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="73006-110">保留局部成员引用。</span><span class="sxs-lookup"><span data-stu-id="73006-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73006-111">要求</span><span class="sxs-lookup"><span data-stu-id="73006-111">Requirements</span></span>  
 <span data-ttu-id="73006-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="73006-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73006-113">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="73006-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="73006-114">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73006-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73006-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73006-115">See also</span></span>

- [<span data-ttu-id="73006-116">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="73006-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
