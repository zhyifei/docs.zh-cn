---
title: CeeSectionRelocExtra 联合
ms.date: 03/30/2017
api_name:
- CeeSectionRelocExtra Union
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocExtra
helpviewer_keywords:
- CeeSectionRelocExtra union [.NET Framework metadata]
ms.assetid: d9568cf6-7f98-4cd6-ab36-0a2bd509afcc
topic_type:
- apiref
ms.openlocfilehash: d11fefe220fdb00457cc48a6cd166673350be049
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006021"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="33771-102">CeeSectionRelocExtra 联合</span><span class="sxs-lookup"><span data-stu-id="33771-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="33771-103">表示[ICeeGen](iceegen-interface.md)接口用于重定位节的地址偏移量。</span><span class="sxs-lookup"><span data-stu-id="33771-103">Represents an address offset that is used by the [ICeeGen](iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33771-104">语法</span><span class="sxs-lookup"><span data-stu-id="33771-104">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="33771-105">成员</span><span class="sxs-lookup"><span data-stu-id="33771-105">Members</span></span>  
  
|<span data-ttu-id="33771-106">成员</span><span class="sxs-lookup"><span data-stu-id="33771-106">Member</span></span>|<span data-ttu-id="33771-107">描述</span><span class="sxs-lookup"><span data-stu-id="33771-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="33771-108">部分的大小上限。</span><span class="sxs-lookup"><span data-stu-id="33771-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="33771-109">要求</span><span class="sxs-lookup"><span data-stu-id="33771-109">Requirements</span></span>  
 <span data-ttu-id="33771-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="33771-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33771-111">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="33771-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="33771-112">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="33771-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="33771-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33771-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33771-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33771-114">See also</span></span>

- [<span data-ttu-id="33771-115">元数据联合</span><span class="sxs-lookup"><span data-stu-id="33771-115">Metadata Unions</span></span>](metadata-unions.md)
