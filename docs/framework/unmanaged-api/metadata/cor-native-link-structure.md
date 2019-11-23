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
ms.openlocfilehash: d03c22c455f0e44ce32d4593d9eee50ceef94a22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443955"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="9b830-102">COR_NATIVE_LINK 结构</span><span class="sxs-lookup"><span data-stu-id="9b830-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="9b830-103">包含用于链接本机代码的信息。</span><span class="sxs-lookup"><span data-stu-id="9b830-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b830-104">语法</span><span class="sxs-lookup"><span data-stu-id="9b830-104">Syntax</span></span>  
  
```cpp  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="9b830-105">Members</span><span class="sxs-lookup"><span data-stu-id="9b830-105">Members</span></span>  
  
|<span data-ttu-id="9b830-106">成员</span><span class="sxs-lookup"><span data-stu-id="9b830-106">Member</span></span>|<span data-ttu-id="9b830-107">描述</span><span class="sxs-lookup"><span data-stu-id="9b830-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="9b830-108">The type to be linked in native code.</span><span class="sxs-lookup"><span data-stu-id="9b830-108">The type to be linked in native code.</span></span> <span data-ttu-id="9b830-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span><span class="sxs-lookup"><span data-stu-id="9b830-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="9b830-110">Flags used by the linker when linking native code.</span><span class="sxs-lookup"><span data-stu-id="9b830-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="9b830-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span><span class="sxs-lookup"><span data-stu-id="9b830-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="9b830-112">The MemberRef metadata token that represents the entry point.</span><span class="sxs-lookup"><span data-stu-id="9b830-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="9b830-113">The format is `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="9b830-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9b830-114">要求</span><span class="sxs-lookup"><span data-stu-id="9b830-114">Requirements</span></span>  
 <span data-ttu-id="9b830-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9b830-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b830-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9b830-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9b830-117">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9b830-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9b830-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b830-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b830-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b830-119">See also</span></span>

- [<span data-ttu-id="9b830-120">元数据结构</span><span class="sxs-lookup"><span data-stu-id="9b830-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="9b830-121">CorNativeLinkType 枚举</span><span class="sxs-lookup"><span data-stu-id="9b830-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [<span data-ttu-id="9b830-122">CorNativeLinkFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="9b830-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
