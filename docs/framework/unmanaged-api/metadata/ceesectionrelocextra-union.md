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
ms.openlocfilehash: 7becace679b62a635d8231c3d42213f247f44190
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444177"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="034e7-102">CeeSectionRelocExtra 联合</span><span class="sxs-lookup"><span data-stu-id="034e7-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="034e7-103">表示[ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)接口用于重定位节的地址偏移量。</span><span class="sxs-lookup"><span data-stu-id="034e7-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="034e7-104">语法</span><span class="sxs-lookup"><span data-stu-id="034e7-104">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="034e7-105">Members</span><span class="sxs-lookup"><span data-stu-id="034e7-105">Members</span></span>  
  
|<span data-ttu-id="034e7-106">成员</span><span class="sxs-lookup"><span data-stu-id="034e7-106">Member</span></span>|<span data-ttu-id="034e7-107">说明</span><span class="sxs-lookup"><span data-stu-id="034e7-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="034e7-108">部分的大小上限。</span><span class="sxs-lookup"><span data-stu-id="034e7-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="034e7-109">要求</span><span class="sxs-lookup"><span data-stu-id="034e7-109">Requirements</span></span>  
 <span data-ttu-id="034e7-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="034e7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="034e7-111">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="034e7-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="034e7-112">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="034e7-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="034e7-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="034e7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="034e7-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="034e7-114">See also</span></span>

- [<span data-ttu-id="034e7-115">元数据联合</span><span class="sxs-lookup"><span data-stu-id="034e7-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
