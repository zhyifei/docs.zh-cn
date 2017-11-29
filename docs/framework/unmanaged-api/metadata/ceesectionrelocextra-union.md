---
title: "CeeSectionRelocExtra 联合"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CeeSectionRelocExtra Union
api_location: mscoree.dll
api_type: COM
f1_keywords: CeeSectionRelocExtra
helpviewer_keywords: CeeSectionRelocExtra union [.NET Framework metadata]
ms.assetid: d9568cf6-7f98-4cd6-ab36-0a2bd509afcc
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c5b584ced996b31be6656082af3f64a19b1f223c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="36ab6-102">CeeSectionRelocExtra 联合</span><span class="sxs-lookup"><span data-stu-id="36ab6-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="36ab6-103">表示由地址偏移量[ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)接口来重定位节。</span><span class="sxs-lookup"><span data-stu-id="36ab6-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36ab6-104">语法</span><span class="sxs-lookup"><span data-stu-id="36ab6-104">Syntax</span></span>  
  
```  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="36ab6-105">成员</span><span class="sxs-lookup"><span data-stu-id="36ab6-105">Members</span></span>  
  
|<span data-ttu-id="36ab6-106">成员</span><span class="sxs-lookup"><span data-stu-id="36ab6-106">Member</span></span>|<span data-ttu-id="36ab6-107">描述</span><span class="sxs-lookup"><span data-stu-id="36ab6-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="36ab6-108">部分高位地址调整。</span><span class="sxs-lookup"><span data-stu-id="36ab6-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="36ab6-109">要求</span><span class="sxs-lookup"><span data-stu-id="36ab6-109">Requirements</span></span>  
 <span data-ttu-id="36ab6-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="36ab6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36ab6-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="36ab6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="36ab6-112">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="36ab6-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="36ab6-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36ab6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36ab6-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36ab6-114">See Also</span></span>  
 [<span data-ttu-id="36ab6-115">元数据联合</span><span class="sxs-lookup"><span data-stu-id="36ab6-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
