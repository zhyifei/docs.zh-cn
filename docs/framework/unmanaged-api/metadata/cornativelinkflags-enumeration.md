---
title: "CorNativeLinkFlags 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorNativeLinkFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorNativeLinkFlags
helpviewer_keywords: CorNativeLinkFlags enumeration [.NET Framework metadata]
ms.assetid: 8027df7c-cfad-4724-bda0-7538d9519070
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09afda63959d974af71e0264ad116c20d3af1923
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="c4635-102">CorNativeLinkFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="c4635-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="c4635-103">提供链接本机代码时链接器使用的标志值。</span><span class="sxs-lookup"><span data-stu-id="c4635-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4635-104">语法</span><span class="sxs-lookup"><span data-stu-id="c4635-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c4635-105">成员</span><span class="sxs-lookup"><span data-stu-id="c4635-105">Members</span></span>  
  
|<span data-ttu-id="c4635-106">成员</span><span class="sxs-lookup"><span data-stu-id="c4635-106">Member</span></span>|<span data-ttu-id="c4635-107">描述</span><span class="sxs-lookup"><span data-stu-id="c4635-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="c4635-108">不指示任何标志。</span><span class="sxs-lookup"><span data-stu-id="c4635-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="c4635-109">指示`setLastError`关键字。</span><span class="sxs-lookup"><span data-stu-id="c4635-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="c4635-110">指示`nomangle`关键字。</span><span class="sxs-lookup"><span data-stu-id="c4635-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="c4635-111">未使用。</span><span class="sxs-lookup"><span data-stu-id="c4635-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c4635-112">要求</span><span class="sxs-lookup"><span data-stu-id="c4635-112">Requirements</span></span>  
 <span data-ttu-id="c4635-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c4635-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4635-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c4635-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c4635-115">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c4635-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c4635-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4635-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4635-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4635-117">See Also</span></span>  
 [<span data-ttu-id="c4635-118">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="c4635-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
