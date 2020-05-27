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
ms.openlocfilehash: 9211af4726617598f3dd8772383cade6368e6c08
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007619"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="c17bb-102">CorNativeLinkFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="c17bb-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="c17bb-103">提供链接本机代码时链接器使用的标志值。</span><span class="sxs-lookup"><span data-stu-id="c17bb-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c17bb-104">语法</span><span class="sxs-lookup"><span data-stu-id="c17bb-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c17bb-105">成员</span><span class="sxs-lookup"><span data-stu-id="c17bb-105">Members</span></span>  
  
|<span data-ttu-id="c17bb-106">成员</span><span class="sxs-lookup"><span data-stu-id="c17bb-106">Member</span></span>|<span data-ttu-id="c17bb-107">描述</span><span class="sxs-lookup"><span data-stu-id="c17bb-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="c17bb-108">指示无标志。</span><span class="sxs-lookup"><span data-stu-id="c17bb-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="c17bb-109">指示 `setLastError` 关键字。</span><span class="sxs-lookup"><span data-stu-id="c17bb-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="c17bb-110">指示 `nomangle` 关键字。</span><span class="sxs-lookup"><span data-stu-id="c17bb-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="c17bb-111">未使用。</span><span class="sxs-lookup"><span data-stu-id="c17bb-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c17bb-112">要求</span><span class="sxs-lookup"><span data-stu-id="c17bb-112">Requirements</span></span>  
 <span data-ttu-id="c17bb-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c17bb-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c17bb-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="c17bb-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c17bb-115">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c17bb-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c17bb-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c17bb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c17bb-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c17bb-117">See also</span></span>

- [<span data-ttu-id="c17bb-118">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="c17bb-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
