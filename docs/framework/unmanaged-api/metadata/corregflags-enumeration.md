---
title: CorRegFlags 枚举
ms.date: 03/30/2017
api_name:
- CorRegFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRegFlags
helpviewer_keywords:
- CorRegFlags enumeration [.NET Framework metadata]
ms.assetid: 8d3080ee-39fe-4c57-8950-51323632d045
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7b935b8f59e434c9da364be1986dbed654a1efd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445804"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="8992c-102">CorRegFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="8992c-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="8992c-103">提供在安装模块或复合图像时用于注册的标志值。</span><span class="sxs-lookup"><span data-stu-id="8992c-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8992c-104">语法</span><span class="sxs-lookup"><span data-stu-id="8992c-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="8992c-105">成员</span><span class="sxs-lookup"><span data-stu-id="8992c-105">Members</span></span>  
  
|<span data-ttu-id="8992c-106">成员</span><span class="sxs-lookup"><span data-stu-id="8992c-106">Member</span></span>|<span data-ttu-id="8992c-107">描述</span><span class="sxs-lookup"><span data-stu-id="8992c-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="8992c-108">指定不应将文件复制到目标。</span><span class="sxs-lookup"><span data-stu-id="8992c-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="8992c-109">指定模块或复合是一种配置。</span><span class="sxs-lookup"><span data-stu-id="8992c-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="8992c-110">指定该模块或复合具有类引用。</span><span class="sxs-lookup"><span data-stu-id="8992c-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8992c-111">要求</span><span class="sxs-lookup"><span data-stu-id="8992c-111">Requirements</span></span>  
 <span data-ttu-id="8992c-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8992c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8992c-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8992c-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8992c-114">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8992c-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8992c-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8992c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8992c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="8992c-116">See Also</span></span>  
 [<span data-ttu-id="8992c-117">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="8992c-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
