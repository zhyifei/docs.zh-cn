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
ms.openlocfilehash: d8d7a43848929e49a8cb48fb957f37213ac78f2e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007346"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="b0824-102">CorRegFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="b0824-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="b0824-103">提供安装模块或复合图像时用于注册的标志值。</span><span class="sxs-lookup"><span data-stu-id="b0824-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0824-104">语法</span><span class="sxs-lookup"><span data-stu-id="b0824-104">Syntax</span></span>  
  
```cpp  
typedef enum
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="b0824-105">成员</span><span class="sxs-lookup"><span data-stu-id="b0824-105">Members</span></span>  
  
|<span data-ttu-id="b0824-106">成员</span><span class="sxs-lookup"><span data-stu-id="b0824-106">Member</span></span>|<span data-ttu-id="b0824-107">描述</span><span class="sxs-lookup"><span data-stu-id="b0824-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="b0824-108">指定不应将文件复制到目标。</span><span class="sxs-lookup"><span data-stu-id="b0824-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="b0824-109">指定模块或复合为配置。</span><span class="sxs-lookup"><span data-stu-id="b0824-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="b0824-110">指定模块或复合具有类引用。</span><span class="sxs-lookup"><span data-stu-id="b0824-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b0824-111">要求</span><span class="sxs-lookup"><span data-stu-id="b0824-111">Requirements</span></span>  
 <span data-ttu-id="b0824-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b0824-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0824-113">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="b0824-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b0824-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b0824-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b0824-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0824-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0824-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0824-116">See also</span></span>

- [<span data-ttu-id="b0824-117">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="b0824-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
