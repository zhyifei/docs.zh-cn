---
title: "CorNativeLinkType 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorNativeLinkType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorNativeLinkType
helpviewer_keywords: CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f19a4366958249881c1f4c33919f239f33c21b21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="3bdc9-102">CorNativeLinkType 枚举</span><span class="sxs-lookup"><span data-stu-id="3bdc9-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="3bdc9-103">提供一些值，用于指示本机代码中链接的类型。</span><span class="sxs-lookup"><span data-stu-id="3bdc9-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bdc9-104">语法</span><span class="sxs-lookup"><span data-stu-id="3bdc9-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="3bdc9-105">成员</span><span class="sxs-lookup"><span data-stu-id="3bdc9-105">Members</span></span>  
  
|<span data-ttu-id="3bdc9-106">成员</span><span class="sxs-lookup"><span data-stu-id="3bdc9-106">Member</span></span>|<span data-ttu-id="3bdc9-107">描述</span><span class="sxs-lookup"><span data-stu-id="3bdc9-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="3bdc9-108">指示未指定任何关键字。</span><span class="sxs-lookup"><span data-stu-id="3bdc9-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="3bdc9-109">指示指定的 ANSI 关键字。</span><span class="sxs-lookup"><span data-stu-id="3bdc9-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="3bdc9-110">指示指定的 Unicode 关键字</span><span class="sxs-lookup"><span data-stu-id="3bdc9-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="3bdc9-111">指示指定了 auto 关键字。</span><span class="sxs-lookup"><span data-stu-id="3bdc9-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="3bdc9-112">指示指定的 OLE 关键字。</span><span class="sxs-lookup"><span data-stu-id="3bdc9-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="3bdc9-113">未使用。</span><span class="sxs-lookup"><span data-stu-id="3bdc9-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3bdc9-114">惠?</span><span class="sxs-lookup"><span data-stu-id="3bdc9-114">Requirements</span></span>  
 <span data-ttu-id="3bdc9-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3bdc9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bdc9-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3bdc9-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3bdc9-117">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3bdc9-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3bdc9-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bdc9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bdc9-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="3bdc9-119">See Also</span></span>  
 [<span data-ttu-id="3bdc9-120">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="3bdc9-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
