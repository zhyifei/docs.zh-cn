---
title: CorLinkerOptions 枚举
ms.date: 03/30/2017
api_name:
- CorLinkerOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLinkerOptions
helpviewer_keywords:
- CorLinkerOptions enumeration [.NET Framework metadata]
ms.assetid: a656aad6-cc7e-4994-8251-004a6a45e18f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc0554ed89d21607978d059b26c4ad69e59a2d4c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166629"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="00578-102">CorLinkerOptions 枚举</span><span class="sxs-lookup"><span data-stu-id="00578-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="00578-103">指定用于选择元数据链接器的选项的标志。</span><span class="sxs-lookup"><span data-stu-id="00578-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00578-104">语法</span><span class="sxs-lookup"><span data-stu-id="00578-104">Syntax</span></span>  
  
```  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="00578-105">成员</span><span class="sxs-lookup"><span data-stu-id="00578-105">Members</span></span>  
  
|<span data-ttu-id="00578-106">成员</span><span class="sxs-lookup"><span data-stu-id="00578-106">Member</span></span>|<span data-ttu-id="00578-107">描述</span><span class="sxs-lookup"><span data-stu-id="00578-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="00578-108">不保留的专用类型和全局函数。</span><span class="sxs-lookup"><span data-stu-id="00578-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="00578-109">保留的专用类型和全局函数。</span><span class="sxs-lookup"><span data-stu-id="00578-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="00578-110">要求</span><span class="sxs-lookup"><span data-stu-id="00578-110">Requirements</span></span>  
 <span data-ttu-id="00578-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="00578-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00578-112">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="00578-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="00578-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00578-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00578-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="00578-114">See also</span></span>

- [<span data-ttu-id="00578-115">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="00578-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
