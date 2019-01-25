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
ms.openlocfilehash: 0f946179fc31adebc8e8fc67c394e0b55a876f49
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54641325"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="ad23a-102">CorNativeLinkType 枚举</span><span class="sxs-lookup"><span data-stu-id="ad23a-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="ad23a-103">提供一些值，用于指示本机代码中链接的类型。</span><span class="sxs-lookup"><span data-stu-id="ad23a-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad23a-104">语法</span><span class="sxs-lookup"><span data-stu-id="ad23a-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="ad23a-105">成员</span><span class="sxs-lookup"><span data-stu-id="ad23a-105">Members</span></span>  
  
|<span data-ttu-id="ad23a-106">成员</span><span class="sxs-lookup"><span data-stu-id="ad23a-106">Member</span></span>|<span data-ttu-id="ad23a-107">描述</span><span class="sxs-lookup"><span data-stu-id="ad23a-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="ad23a-108">指示未指定任何关键字。</span><span class="sxs-lookup"><span data-stu-id="ad23a-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="ad23a-109">指示指定的 ANSI 关键字。</span><span class="sxs-lookup"><span data-stu-id="ad23a-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="ad23a-110">指示指定的 Unicode 关键字</span><span class="sxs-lookup"><span data-stu-id="ad23a-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="ad23a-111">指示指定 auto 关键字。</span><span class="sxs-lookup"><span data-stu-id="ad23a-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="ad23a-112">指示指定的 OLE 关键字。</span><span class="sxs-lookup"><span data-stu-id="ad23a-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="ad23a-113">未使用。</span><span class="sxs-lookup"><span data-stu-id="ad23a-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ad23a-114">要求</span><span class="sxs-lookup"><span data-stu-id="ad23a-114">Requirements</span></span>  
 <span data-ttu-id="ad23a-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ad23a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad23a-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ad23a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ad23a-117">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ad23a-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ad23a-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad23a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad23a-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad23a-119">See also</span></span>
- [<span data-ttu-id="ad23a-120">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="ad23a-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
