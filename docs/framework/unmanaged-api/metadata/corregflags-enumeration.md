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
ms.openlocfilehash: 8fe6216e11a64ea182d796247d888b862b1e8377
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177929"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="1e9a2-102">CorRegFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="1e9a2-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="1e9a2-103">提供安装模块或复合映像时用于注册的标志值。</span><span class="sxs-lookup"><span data-stu-id="1e9a2-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e9a2-104">语法</span><span class="sxs-lookup"><span data-stu-id="1e9a2-104">Syntax</span></span>  
  
```cpp  
typedef enum
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="1e9a2-105">成员</span><span class="sxs-lookup"><span data-stu-id="1e9a2-105">Members</span></span>  
  
|<span data-ttu-id="1e9a2-106">成员</span><span class="sxs-lookup"><span data-stu-id="1e9a2-106">Member</span></span>|<span data-ttu-id="1e9a2-107">说明</span><span class="sxs-lookup"><span data-stu-id="1e9a2-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="1e9a2-108">指定不应将文件复制到目标。</span><span class="sxs-lookup"><span data-stu-id="1e9a2-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="1e9a2-109">指定模块或复合是配置。</span><span class="sxs-lookup"><span data-stu-id="1e9a2-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="1e9a2-110">指定模块或复合具有类引用。</span><span class="sxs-lookup"><span data-stu-id="1e9a2-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e9a2-111">要求</span><span class="sxs-lookup"><span data-stu-id="1e9a2-111">Requirements</span></span>  
 <span data-ttu-id="1e9a2-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1e9a2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e9a2-113">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="1e9a2-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1e9a2-114">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="1e9a2-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1e9a2-115">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e9a2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e9a2-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e9a2-116">See also</span></span>

- [<span data-ttu-id="1e9a2-117">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="1e9a2-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
