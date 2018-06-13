---
title: CorNativeLinkFlags 枚举
ms.date: 03/30/2017
api_name:
- CorNativeLinkFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkFlags
helpviewer_keywords:
- CorNativeLinkFlags enumeration [.NET Framework metadata]
ms.assetid: 8027df7c-cfad-4724-bda0-7538d9519070
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98a83a64a692955d5627e891e7fb3a3ef6f53476
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442564"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="263f7-102">CorNativeLinkFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="263f7-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="263f7-103">提供链接本机代码时链接器使用的标志值。</span><span class="sxs-lookup"><span data-stu-id="263f7-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="263f7-104">语法</span><span class="sxs-lookup"><span data-stu-id="263f7-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="263f7-105">成员</span><span class="sxs-lookup"><span data-stu-id="263f7-105">Members</span></span>  
  
|<span data-ttu-id="263f7-106">成员</span><span class="sxs-lookup"><span data-stu-id="263f7-106">Member</span></span>|<span data-ttu-id="263f7-107">描述</span><span class="sxs-lookup"><span data-stu-id="263f7-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="263f7-108">不指示任何标志。</span><span class="sxs-lookup"><span data-stu-id="263f7-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="263f7-109">指示`setLastError`关键字。</span><span class="sxs-lookup"><span data-stu-id="263f7-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="263f7-110">指示`nomangle`关键字。</span><span class="sxs-lookup"><span data-stu-id="263f7-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="263f7-111">未使用。</span><span class="sxs-lookup"><span data-stu-id="263f7-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="263f7-112">要求</span><span class="sxs-lookup"><span data-stu-id="263f7-112">Requirements</span></span>  
 <span data-ttu-id="263f7-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="263f7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="263f7-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="263f7-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="263f7-115">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="263f7-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="263f7-116">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="263f7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="263f7-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="263f7-117">See Also</span></span>  
 [<span data-ttu-id="263f7-118">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="263f7-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
