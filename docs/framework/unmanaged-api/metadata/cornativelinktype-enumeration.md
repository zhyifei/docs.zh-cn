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
ms.openlocfilehash: 0b613ebacdff82a29fdbc3f4caa0f2b8bb5d3f6a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176157"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="ef89c-102">CorNativeLinkType 枚举</span><span class="sxs-lookup"><span data-stu-id="ef89c-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="ef89c-103">提供一些值，用于指示本机代码中链接的类型。</span><span class="sxs-lookup"><span data-stu-id="ef89c-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef89c-104">语法</span><span class="sxs-lookup"><span data-stu-id="ef89c-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ef89c-105">成员</span><span class="sxs-lookup"><span data-stu-id="ef89c-105">Members</span></span>  
  
|<span data-ttu-id="ef89c-106">成员</span><span class="sxs-lookup"><span data-stu-id="ef89c-106">Member</span></span>|<span data-ttu-id="ef89c-107">说明</span><span class="sxs-lookup"><span data-stu-id="ef89c-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="ef89c-108">指示未指定任何关键字。</span><span class="sxs-lookup"><span data-stu-id="ef89c-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="ef89c-109">指示指定了 ANSI 关键字。</span><span class="sxs-lookup"><span data-stu-id="ef89c-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="ef89c-110">指示指定了 Unicode 关键字</span><span class="sxs-lookup"><span data-stu-id="ef89c-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="ef89c-111">指示指定了自动关键字。</span><span class="sxs-lookup"><span data-stu-id="ef89c-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="ef89c-112">指示指定了 OLE 关键字。</span><span class="sxs-lookup"><span data-stu-id="ef89c-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="ef89c-113">未使用。</span><span class="sxs-lookup"><span data-stu-id="ef89c-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ef89c-114">要求</span><span class="sxs-lookup"><span data-stu-id="ef89c-114">Requirements</span></span>  
 <span data-ttu-id="ef89c-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ef89c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef89c-116">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="ef89c-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ef89c-117">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="ef89c-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ef89c-118">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef89c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef89c-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef89c-119">See also</span></span>

- [<span data-ttu-id="ef89c-120">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="ef89c-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
