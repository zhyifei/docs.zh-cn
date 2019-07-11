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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6338034d6714e8770e06ff61994fdf4433eb1684
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781793"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="65f18-102">CorLocalRefPreservation 枚举</span><span class="sxs-lookup"><span data-stu-id="65f18-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="65f18-103">包含用于处理本地引用的标志值。</span><span class="sxs-lookup"><span data-stu-id="65f18-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65f18-104">语法</span><span class="sxs-lookup"><span data-stu-id="65f18-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="65f18-105">成员</span><span class="sxs-lookup"><span data-stu-id="65f18-105">Members</span></span>  
  
|<span data-ttu-id="65f18-106">成员</span><span class="sxs-lookup"><span data-stu-id="65f18-106">Member</span></span>|<span data-ttu-id="65f18-107">描述</span><span class="sxs-lookup"><span data-stu-id="65f18-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="65f18-108">保留任何本地引用。</span><span class="sxs-lookup"><span data-stu-id="65f18-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="65f18-109">保留本地类型引用。</span><span class="sxs-lookup"><span data-stu-id="65f18-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="65f18-110">保留本地成员引用。</span><span class="sxs-lookup"><span data-stu-id="65f18-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="65f18-111">要求</span><span class="sxs-lookup"><span data-stu-id="65f18-111">Requirements</span></span>  
 <span data-ttu-id="65f18-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="65f18-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65f18-113">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="65f18-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="65f18-114">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65f18-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65f18-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="65f18-115">See also</span></span>

- [<span data-ttu-id="65f18-116">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="65f18-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
