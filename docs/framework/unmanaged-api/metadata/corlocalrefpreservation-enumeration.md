---
title: "CorLocalRefPreservation 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c35bbfef62f65a9a401d00f9ae56e2f4c00bb0b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="f5e4c-102">CorLocalRefPreservation 枚举</span><span class="sxs-lookup"><span data-stu-id="f5e4c-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="f5e4c-103">包含用于处理本地引用的标志值。</span><span class="sxs-lookup"><span data-stu-id="f5e4c-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5e4c-104">语法</span><span class="sxs-lookup"><span data-stu-id="f5e4c-104">Syntax</span></span>  
  
```  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="f5e4c-105">成员</span><span class="sxs-lookup"><span data-stu-id="f5e4c-105">Members</span></span>  
  
|<span data-ttu-id="f5e4c-106">成员</span><span class="sxs-lookup"><span data-stu-id="f5e4c-106">Member</span></span>|<span data-ttu-id="f5e4c-107">描述</span><span class="sxs-lookup"><span data-stu-id="f5e4c-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="f5e4c-108">保留任何本地引用。</span><span class="sxs-lookup"><span data-stu-id="f5e4c-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="f5e4c-109">保留本地类型引用。</span><span class="sxs-lookup"><span data-stu-id="f5e4c-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="f5e4c-110">保留本地成员引用。</span><span class="sxs-lookup"><span data-stu-id="f5e4c-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f5e4c-111">惠?</span><span class="sxs-lookup"><span data-stu-id="f5e4c-111">Requirements</span></span>  
 <span data-ttu-id="f5e4c-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f5e4c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5e4c-113">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="f5e4c-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f5e4c-114">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5e4c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5e4c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5e4c-115">See Also</span></span>  
 [<span data-ttu-id="f5e4c-116">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="f5e4c-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
