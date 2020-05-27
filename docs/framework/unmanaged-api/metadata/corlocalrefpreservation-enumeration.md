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
ms.openlocfilehash: 42cb4e76bb77aebcee3b28035635a877513cdc04
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008984"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="d28c2-102">CorLocalRefPreservation 枚举</span><span class="sxs-lookup"><span data-stu-id="d28c2-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="d28c2-103">包含用于处理本地引用的标志值。</span><span class="sxs-lookup"><span data-stu-id="d28c2-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d28c2-104">语法</span><span class="sxs-lookup"><span data-stu-id="d28c2-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="d28c2-105">成员</span><span class="sxs-lookup"><span data-stu-id="d28c2-105">Members</span></span>  
  
|<span data-ttu-id="d28c2-106">成员</span><span class="sxs-lookup"><span data-stu-id="d28c2-106">Member</span></span>|<span data-ttu-id="d28c2-107">描述</span><span class="sxs-lookup"><span data-stu-id="d28c2-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="d28c2-108">不保留本地引用。</span><span class="sxs-lookup"><span data-stu-id="d28c2-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="d28c2-109">保留本地类型引用。</span><span class="sxs-lookup"><span data-stu-id="d28c2-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="d28c2-110">保留局部成员引用。</span><span class="sxs-lookup"><span data-stu-id="d28c2-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d28c2-111">要求</span><span class="sxs-lookup"><span data-stu-id="d28c2-111">Requirements</span></span>  
 <span data-ttu-id="d28c2-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d28c2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d28c2-113">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="d28c2-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d28c2-114">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d28c2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d28c2-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d28c2-115">See also</span></span>

- [<span data-ttu-id="d28c2-116">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="d28c2-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
