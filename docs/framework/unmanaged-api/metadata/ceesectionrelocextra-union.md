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
ms.openlocfilehash: c2e73caa3c69090bca30c8d4a907ddb619bd0ed4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776331"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="131ed-102">CeeSectionRelocExtra 联合</span><span class="sxs-lookup"><span data-stu-id="131ed-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="131ed-103">表示由地址偏移量[ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)接口来重定位节。</span><span class="sxs-lookup"><span data-stu-id="131ed-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="131ed-104">语法</span><span class="sxs-lookup"><span data-stu-id="131ed-104">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="131ed-105">成员</span><span class="sxs-lookup"><span data-stu-id="131ed-105">Members</span></span>  
  
|<span data-ttu-id="131ed-106">成员</span><span class="sxs-lookup"><span data-stu-id="131ed-106">Member</span></span>|<span data-ttu-id="131ed-107">描述</span><span class="sxs-lookup"><span data-stu-id="131ed-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="131ed-108">上部的地址进行调整的部分。</span><span class="sxs-lookup"><span data-stu-id="131ed-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="131ed-109">要求</span><span class="sxs-lookup"><span data-stu-id="131ed-109">Requirements</span></span>  
 <span data-ttu-id="131ed-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="131ed-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="131ed-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="131ed-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="131ed-112">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="131ed-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="131ed-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="131ed-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="131ed-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="131ed-114">See also</span></span>

- [<span data-ttu-id="131ed-115">元数据联合</span><span class="sxs-lookup"><span data-stu-id="131ed-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
