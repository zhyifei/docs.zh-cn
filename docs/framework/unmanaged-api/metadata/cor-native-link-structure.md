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
ms.openlocfilehash: a11b7d5939c4c20504b1ff3dfb4613f85bca0db4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007970"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="0c59c-102">COR_NATIVE_LINK 结构</span><span class="sxs-lookup"><span data-stu-id="0c59c-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="0c59c-103">包含用于链接本机代码的信息。</span><span class="sxs-lookup"><span data-stu-id="0c59c-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c59c-104">语法</span><span class="sxs-lookup"><span data-stu-id="0c59c-104">Syntax</span></span>  
  
```cpp  
typedef struct
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="0c59c-105">成员</span><span class="sxs-lookup"><span data-stu-id="0c59c-105">Members</span></span>  
  
|<span data-ttu-id="0c59c-106">成员</span><span class="sxs-lookup"><span data-stu-id="0c59c-106">Member</span></span>|<span data-ttu-id="0c59c-107">描述</span><span class="sxs-lookup"><span data-stu-id="0c59c-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="0c59c-108">要在本机代码中链接的类型。</span><span class="sxs-lookup"><span data-stu-id="0c59c-108">The type to be linked in native code.</span></span> <span data-ttu-id="0c59c-109">此值为[CorNativeLinkType](cornativelinktype-enumeration.md)值之一。</span><span class="sxs-lookup"><span data-stu-id="0c59c-109">This value is one of the [CorNativeLinkType](cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="0c59c-110">链接本机代码时链接器使用的标志。</span><span class="sxs-lookup"><span data-stu-id="0c59c-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="0c59c-111">此值为[CorNativeLinkFlags](cornativelinkflags-enumeration.md)值之一。</span><span class="sxs-lookup"><span data-stu-id="0c59c-111">This value is one of the [CorNativeLinkFlags](cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="0c59c-112">表示入口点的 MemberRef 元数据标记。</span><span class="sxs-lookup"><span data-stu-id="0c59c-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="0c59c-113">格式为 `lib:entrypoint`。</span><span class="sxs-lookup"><span data-stu-id="0c59c-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c59c-114">要求</span><span class="sxs-lookup"><span data-stu-id="0c59c-114">Requirements</span></span>  
 <span data-ttu-id="0c59c-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0c59c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c59c-116">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="0c59c-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c59c-117">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0c59c-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0c59c-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c59c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c59c-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c59c-119">See also</span></span>

- [<span data-ttu-id="0c59c-120">元数据结构</span><span class="sxs-lookup"><span data-stu-id="0c59c-120">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="0c59c-121">CorNativeLinkType 枚举</span><span class="sxs-lookup"><span data-stu-id="0c59c-121">CorNativeLinkType Enumeration</span></span>](cornativelinktype-enumeration.md)
- [<span data-ttu-id="0c59c-122">CorNativeLinkFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="0c59c-122">CorNativeLinkFlags Enumeration</span></span>](cornativelinkflags-enumeration.md)
