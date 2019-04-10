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
ms.openlocfilehash: 66d650adb39a9c7dade0936ec671ae5a8b4aeecd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170053"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="6deb1-102">CorNativeLinkType 枚举</span><span class="sxs-lookup"><span data-stu-id="6deb1-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="6deb1-103">提供一些值，用于指示本机代码中链接的类型。</span><span class="sxs-lookup"><span data-stu-id="6deb1-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6deb1-104">语法</span><span class="sxs-lookup"><span data-stu-id="6deb1-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="6deb1-105">成员</span><span class="sxs-lookup"><span data-stu-id="6deb1-105">Members</span></span>  
  
|<span data-ttu-id="6deb1-106">成员</span><span class="sxs-lookup"><span data-stu-id="6deb1-106">Member</span></span>|<span data-ttu-id="6deb1-107">描述</span><span class="sxs-lookup"><span data-stu-id="6deb1-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="6deb1-108">指示未指定任何关键字。</span><span class="sxs-lookup"><span data-stu-id="6deb1-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="6deb1-109">指示指定的 ANSI 关键字。</span><span class="sxs-lookup"><span data-stu-id="6deb1-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="6deb1-110">指示指定的 Unicode 关键字</span><span class="sxs-lookup"><span data-stu-id="6deb1-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="6deb1-111">指示指定 auto 关键字。</span><span class="sxs-lookup"><span data-stu-id="6deb1-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="6deb1-112">指示指定的 OLE 关键字。</span><span class="sxs-lookup"><span data-stu-id="6deb1-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="6deb1-113">未使用。</span><span class="sxs-lookup"><span data-stu-id="6deb1-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6deb1-114">要求</span><span class="sxs-lookup"><span data-stu-id="6deb1-114">Requirements</span></span>  
 <span data-ttu-id="6deb1-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6deb1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6deb1-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6deb1-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6deb1-117">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6deb1-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="6deb1-118">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="6deb1-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6deb1-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="6deb1-119">See also</span></span>

- [<span data-ttu-id="6deb1-120">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="6deb1-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
