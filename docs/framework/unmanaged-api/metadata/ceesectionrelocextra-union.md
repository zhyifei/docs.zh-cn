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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8a78a4b82d0b2064c90c938a8614b0c7594f7856
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182268"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="a75e5-102">CeeSectionRelocExtra 联合</span><span class="sxs-lookup"><span data-stu-id="a75e5-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="a75e5-103">表示由地址偏移量[ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)接口来重定位节。</span><span class="sxs-lookup"><span data-stu-id="a75e5-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a75e5-104">语法</span><span class="sxs-lookup"><span data-stu-id="a75e5-104">Syntax</span></span>  
  
```  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="a75e5-105">成员</span><span class="sxs-lookup"><span data-stu-id="a75e5-105">Members</span></span>  
  
|<span data-ttu-id="a75e5-106">成员</span><span class="sxs-lookup"><span data-stu-id="a75e5-106">Member</span></span>|<span data-ttu-id="a75e5-107">描述</span><span class="sxs-lookup"><span data-stu-id="a75e5-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="a75e5-108">上部的地址进行调整的部分。</span><span class="sxs-lookup"><span data-stu-id="a75e5-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a75e5-109">要求</span><span class="sxs-lookup"><span data-stu-id="a75e5-109">Requirements</span></span>  
 <span data-ttu-id="a75e5-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a75e5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a75e5-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a75e5-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a75e5-112">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a75e5-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a75e5-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a75e5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a75e5-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a75e5-114">See also</span></span>

- [<span data-ttu-id="a75e5-115">元数据联合</span><span class="sxs-lookup"><span data-stu-id="a75e5-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
