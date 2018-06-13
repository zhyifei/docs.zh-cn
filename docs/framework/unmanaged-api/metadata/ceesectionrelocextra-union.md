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
ms.openlocfilehash: c7634ec801a30aa7ba07954c1df0c3d37ec279eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440296"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="c4b54-102">CeeSectionRelocExtra 联合</span><span class="sxs-lookup"><span data-stu-id="c4b54-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="c4b54-103">表示由地址偏移量[ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)接口来重定位节。</span><span class="sxs-lookup"><span data-stu-id="c4b54-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4b54-104">语法</span><span class="sxs-lookup"><span data-stu-id="c4b54-104">Syntax</span></span>  
  
```  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="c4b54-105">成员</span><span class="sxs-lookup"><span data-stu-id="c4b54-105">Members</span></span>  
  
|<span data-ttu-id="c4b54-106">成员</span><span class="sxs-lookup"><span data-stu-id="c4b54-106">Member</span></span>|<span data-ttu-id="c4b54-107">描述</span><span class="sxs-lookup"><span data-stu-id="c4b54-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="c4b54-108">部分高位地址调整。</span><span class="sxs-lookup"><span data-stu-id="c4b54-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c4b54-109">要求</span><span class="sxs-lookup"><span data-stu-id="c4b54-109">Requirements</span></span>  
 <span data-ttu-id="c4b54-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b54-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4b54-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c4b54-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c4b54-112">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c4b54-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c4b54-113">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4b54-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4b54-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4b54-114">See Also</span></span>  
 [<span data-ttu-id="c4b54-115">元数据联合</span><span class="sxs-lookup"><span data-stu-id="c4b54-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
