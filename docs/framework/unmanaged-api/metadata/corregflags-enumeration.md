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
ms.openlocfilehash: 79a9e4513a98a29edc11cc76c599f03c9c3a72b4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450110"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="354d9-102">CorRegFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="354d9-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="354d9-103">提供安装模块或复合图像时用于注册的标志值。</span><span class="sxs-lookup"><span data-stu-id="354d9-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="354d9-104">语法</span><span class="sxs-lookup"><span data-stu-id="354d9-104">Syntax</span></span>  
  
```cpp  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="354d9-105">Members</span><span class="sxs-lookup"><span data-stu-id="354d9-105">Members</span></span>  
  
|<span data-ttu-id="354d9-106">成员</span><span class="sxs-lookup"><span data-stu-id="354d9-106">Member</span></span>|<span data-ttu-id="354d9-107">说明</span><span class="sxs-lookup"><span data-stu-id="354d9-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="354d9-108">指定不应将文件复制到目标。</span><span class="sxs-lookup"><span data-stu-id="354d9-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="354d9-109">指定模块或复合为配置。</span><span class="sxs-lookup"><span data-stu-id="354d9-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="354d9-110">指定模块或复合具有类引用。</span><span class="sxs-lookup"><span data-stu-id="354d9-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="354d9-111">要求</span><span class="sxs-lookup"><span data-stu-id="354d9-111">Requirements</span></span>  
 <span data-ttu-id="354d9-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="354d9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="354d9-113">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="354d9-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="354d9-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="354d9-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="354d9-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="354d9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="354d9-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="354d9-116">See also</span></span>

- [<span data-ttu-id="354d9-117">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="354d9-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
