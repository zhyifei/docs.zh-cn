---
title: CorNativeLinkType 枚举
ms.date: 03/30/2017
api_name:
- CorNativeLinkType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkType
helpviewer_keywords:
- CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 944c641c39ddef7add0e9f382dc7d35068668455
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781717"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="68dae-102">CorNativeLinkType 枚举</span><span class="sxs-lookup"><span data-stu-id="68dae-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="68dae-103">提供一些值，用于指示本机代码中链接的类型。</span><span class="sxs-lookup"><span data-stu-id="68dae-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68dae-104">语法</span><span class="sxs-lookup"><span data-stu-id="68dae-104">Syntax</span></span>  
  
```cpp  
typedef enum   
{  
    nltNone       = 1,  
    nltAnsi       = 2,  
    nltUnicode    = 3,  
    nltAuto       = 4,  
    nltOle        = 5,  
    nltMaxValue   = 7  
} CorNativeLinkType;  
```  
  
## <a name="members"></a><span data-ttu-id="68dae-105">成员</span><span class="sxs-lookup"><span data-stu-id="68dae-105">Members</span></span>  
  
|<span data-ttu-id="68dae-106">成员</span><span class="sxs-lookup"><span data-stu-id="68dae-106">Member</span></span>|<span data-ttu-id="68dae-107">描述</span><span class="sxs-lookup"><span data-stu-id="68dae-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="68dae-108">指示未指定任何关键字。</span><span class="sxs-lookup"><span data-stu-id="68dae-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="68dae-109">指示指定的 ANSI 关键字。</span><span class="sxs-lookup"><span data-stu-id="68dae-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="68dae-110">指示指定的 Unicode 关键字</span><span class="sxs-lookup"><span data-stu-id="68dae-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="68dae-111">指示指定 auto 关键字。</span><span class="sxs-lookup"><span data-stu-id="68dae-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="68dae-112">指示指定的 OLE 关键字。</span><span class="sxs-lookup"><span data-stu-id="68dae-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="68dae-113">未使用。</span><span class="sxs-lookup"><span data-stu-id="68dae-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="68dae-114">要求</span><span class="sxs-lookup"><span data-stu-id="68dae-114">Requirements</span></span>  
 <span data-ttu-id="68dae-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="68dae-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68dae-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="68dae-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="68dae-117">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="68dae-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="68dae-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68dae-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68dae-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="68dae-119">See also</span></span>

- [<span data-ttu-id="68dae-120">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="68dae-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
