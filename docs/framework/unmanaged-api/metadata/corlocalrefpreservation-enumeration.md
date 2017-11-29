---
title: "CorLocalRefPreservation 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorLocalRefPreservation
api_location: mscoree.dll
api_type: COM
f1_keywords: CorLocalRefPreservation
helpviewer_keywords: CorLocalRefPreservation enumeration [.NET Framework metadata]
ms.assetid: 44757163-1228-4213-a4c4-d4de503cc75d
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: eac01ce31e850eb02af84c0b84e58c1f0142242d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="19a84-102">CorLocalRefPreservation 枚举</span><span class="sxs-lookup"><span data-stu-id="19a84-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="19a84-103">包含用于处理本地引用的标志值。</span><span class="sxs-lookup"><span data-stu-id="19a84-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19a84-104">语法</span><span class="sxs-lookup"><span data-stu-id="19a84-104">Syntax</span></span>  
  
```  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="19a84-105">成员</span><span class="sxs-lookup"><span data-stu-id="19a84-105">Members</span></span>  
  
|<span data-ttu-id="19a84-106">成员</span><span class="sxs-lookup"><span data-stu-id="19a84-106">Member</span></span>|<span data-ttu-id="19a84-107">描述</span><span class="sxs-lookup"><span data-stu-id="19a84-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="19a84-108">保留任何本地引用。</span><span class="sxs-lookup"><span data-stu-id="19a84-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="19a84-109">保留本地类型引用。</span><span class="sxs-lookup"><span data-stu-id="19a84-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="19a84-110">保留本地成员引用。</span><span class="sxs-lookup"><span data-stu-id="19a84-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="19a84-111">要求</span><span class="sxs-lookup"><span data-stu-id="19a84-111">Requirements</span></span>  
 <span data-ttu-id="19a84-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="19a84-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19a84-113">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="19a84-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="19a84-114">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19a84-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19a84-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19a84-115">See Also</span></span>  
 [<span data-ttu-id="19a84-116">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="19a84-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
