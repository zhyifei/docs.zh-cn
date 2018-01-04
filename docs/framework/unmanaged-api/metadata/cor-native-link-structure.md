---
title: "COR_NATIVE_LINK 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_NATIVE_LINK
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_NATIVE_LINK
helpviewer_keywords: COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 63e5946e98e7c862a2502a71a02e605a38086618
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cornativelink-structure"></a><span data-ttu-id="5dc06-102">COR_NATIVE_LINK 结构</span><span class="sxs-lookup"><span data-stu-id="5dc06-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="5dc06-103">包含用于链接本机代码的信息。</span><span class="sxs-lookup"><span data-stu-id="5dc06-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dc06-104">语法</span><span class="sxs-lookup"><span data-stu-id="5dc06-104">Syntax</span></span>  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="5dc06-105">成员</span><span class="sxs-lookup"><span data-stu-id="5dc06-105">Members</span></span>  
  
|<span data-ttu-id="5dc06-106">成员</span><span class="sxs-lookup"><span data-stu-id="5dc06-106">Member</span></span>|<span data-ttu-id="5dc06-107">描述</span><span class="sxs-lookup"><span data-stu-id="5dc06-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="5dc06-108">要本机代码中链接的类型。</span><span class="sxs-lookup"><span data-stu-id="5dc06-108">The type to be linked in native code.</span></span> <span data-ttu-id="5dc06-109">此值是之一[CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="5dc06-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="5dc06-110">链接本机代码时使用的链接器的标志。</span><span class="sxs-lookup"><span data-stu-id="5dc06-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="5dc06-111">此值是之一[CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="5dc06-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="5dc06-112">MemberRef 元数据标记表示的入口点。</span><span class="sxs-lookup"><span data-stu-id="5dc06-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="5dc06-113">格式是`lib:entrypoint`。</span><span class="sxs-lookup"><span data-stu-id="5dc06-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5dc06-114">惠?</span><span class="sxs-lookup"><span data-stu-id="5dc06-114">Requirements</span></span>  
 <span data-ttu-id="5dc06-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5dc06-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dc06-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5dc06-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5dc06-117">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5dc06-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5dc06-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dc06-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dc06-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="5dc06-119">See Also</span></span>  
 [<span data-ttu-id="5dc06-120">元数据结构</span><span class="sxs-lookup"><span data-stu-id="5dc06-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="5dc06-121">CorNativeLinkType 枚举</span><span class="sxs-lookup"><span data-stu-id="5dc06-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)  
 [<span data-ttu-id="5dc06-122">CorNativeLinkFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="5dc06-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
