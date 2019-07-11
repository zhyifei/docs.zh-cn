---
title: COR_NATIVE_LINK 结构
ms.date: 03/30/2017
api_name:
- COR_NATIVE_LINK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_NATIVE_LINK
helpviewer_keywords:
- COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ae518e5a736a78a261dc3821d53d93afee95a271
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779999"
---
# <a name="cornativelink-structure"></a><span data-ttu-id="e2a79-102">COR_NATIVE_LINK 结构</span><span class="sxs-lookup"><span data-stu-id="e2a79-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="e2a79-103">包含用于链接本机代码的信息。</span><span class="sxs-lookup"><span data-stu-id="e2a79-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2a79-104">语法</span><span class="sxs-lookup"><span data-stu-id="e2a79-104">Syntax</span></span>  
  
```cpp  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="e2a79-105">成员</span><span class="sxs-lookup"><span data-stu-id="e2a79-105">Members</span></span>  
  
|<span data-ttu-id="e2a79-106">成员</span><span class="sxs-lookup"><span data-stu-id="e2a79-106">Member</span></span>|<span data-ttu-id="e2a79-107">描述</span><span class="sxs-lookup"><span data-stu-id="e2a79-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="e2a79-108">要在本机代码中链接的类型。</span><span class="sxs-lookup"><span data-stu-id="e2a79-108">The type to be linked in native code.</span></span> <span data-ttu-id="e2a79-109">此值是之一[CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="e2a79-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="e2a79-110">链接器链接本机代码时使用的标志。</span><span class="sxs-lookup"><span data-stu-id="e2a79-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="e2a79-111">此值是之一[CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="e2a79-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="e2a79-112">MemberRef 元数据标记，用于表示入口点。</span><span class="sxs-lookup"><span data-stu-id="e2a79-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="e2a79-113">格式是`lib:entrypoint`。</span><span class="sxs-lookup"><span data-stu-id="e2a79-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e2a79-114">要求</span><span class="sxs-lookup"><span data-stu-id="e2a79-114">Requirements</span></span>  
 <span data-ttu-id="e2a79-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e2a79-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2a79-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e2a79-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e2a79-117">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e2a79-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e2a79-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2a79-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2a79-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2a79-119">See also</span></span>

- [<span data-ttu-id="e2a79-120">元数据结构</span><span class="sxs-lookup"><span data-stu-id="e2a79-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="e2a79-121">CorNativeLinkType 枚举</span><span class="sxs-lookup"><span data-stu-id="e2a79-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [<span data-ttu-id="e2a79-122">CorNativeLinkFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="e2a79-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
