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
ms.openlocfilehash: 29f2401e2e3faccae05ca5249fcd7d9e89aacb46
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007606"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="87e7b-102">CorNativeLinkType 枚举</span><span class="sxs-lookup"><span data-stu-id="87e7b-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="87e7b-103">提供一些值，用于指示本机代码中链接的类型。</span><span class="sxs-lookup"><span data-stu-id="87e7b-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87e7b-104">语法</span><span class="sxs-lookup"><span data-stu-id="87e7b-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="87e7b-105">成员</span><span class="sxs-lookup"><span data-stu-id="87e7b-105">Members</span></span>  
  
|<span data-ttu-id="87e7b-106">成员</span><span class="sxs-lookup"><span data-stu-id="87e7b-106">Member</span></span>|<span data-ttu-id="87e7b-107">描述</span><span class="sxs-lookup"><span data-stu-id="87e7b-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="87e7b-108">指示未指定任何关键字。</span><span class="sxs-lookup"><span data-stu-id="87e7b-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="87e7b-109">指示指定了 ANSI 关键字。</span><span class="sxs-lookup"><span data-stu-id="87e7b-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="87e7b-110">指示指定了 Unicode 关键字</span><span class="sxs-lookup"><span data-stu-id="87e7b-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="87e7b-111">指示指定了 auto 关键字。</span><span class="sxs-lookup"><span data-stu-id="87e7b-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="87e7b-112">指示指定了 OLE 关键字。</span><span class="sxs-lookup"><span data-stu-id="87e7b-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="87e7b-113">未使用。</span><span class="sxs-lookup"><span data-stu-id="87e7b-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="87e7b-114">要求</span><span class="sxs-lookup"><span data-stu-id="87e7b-114">Requirements</span></span>  
 <span data-ttu-id="87e7b-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="87e7b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87e7b-116">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="87e7b-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="87e7b-117">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="87e7b-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="87e7b-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87e7b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87e7b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87e7b-119">See also</span></span>

- [<span data-ttu-id="87e7b-120">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="87e7b-120">Metadata Enumerations</span></span>](metadata-enumerations.md)
