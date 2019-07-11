---
title: CorValidatorModuleType 枚举
ms.date: 03/30/2017
api_name:
- CorValidatorModuleType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorValidatorModuleType
helpviewer_keywords:
- CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 04bed418d96658e29328cf2ce6bba445639b437f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750758"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="54cfc-102">CorValidatorModuleType 枚举</span><span class="sxs-lookup"><span data-stu-id="54cfc-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="54cfc-103">指定模块的类型。</span><span class="sxs-lookup"><span data-stu-id="54cfc-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54cfc-104">语法</span><span class="sxs-lookup"><span data-stu-id="54cfc-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    ValidatorModuleTypeInvalid  = 0x0,  
    ValidatorModuleTypeMin      = 0x00000001,  
    ValidatorModuleTypePE       = 0x00000001,  
    ValidatorModuleTypeObj      = 0x00000002,  
    ValidatorModuleTypeEnc      = 0x00000003,  
    ValidatorModuleTypeIncr     = 0x00000004,  
    ValidatorModuleTypeMax      = 0x00000004  
} CorValidatorModuleType;  
```  
  
## <a name="members"></a><span data-ttu-id="54cfc-105">成员</span><span class="sxs-lookup"><span data-stu-id="54cfc-105">Members</span></span>  
  
|<span data-ttu-id="54cfc-106">成员</span><span class="sxs-lookup"><span data-stu-id="54cfc-106">Member</span></span>|<span data-ttu-id="54cfc-107">描述</span><span class="sxs-lookup"><span data-stu-id="54cfc-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="54cfc-108">该模块是无效的类型。</span><span class="sxs-lookup"><span data-stu-id="54cfc-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="54cfc-109">最小值`CorValidatorModuleType`枚举。</span><span class="sxs-lookup"><span data-stu-id="54cfc-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="54cfc-110">该模块是可移植可执行 (PE) 文件。</span><span class="sxs-lookup"><span data-stu-id="54cfc-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="54cfc-111">该模块是.obj 文件。</span><span class="sxs-lookup"><span data-stu-id="54cfc-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="54cfc-112">该模块是编辑并继续调试程序会话。</span><span class="sxs-lookup"><span data-stu-id="54cfc-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="54cfc-113">该模块是指以增量方式生成。</span><span class="sxs-lookup"><span data-stu-id="54cfc-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="54cfc-114">最大值`CorValidatorModuleType`枚举。</span><span class="sxs-lookup"><span data-stu-id="54cfc-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="54cfc-115">要求</span><span class="sxs-lookup"><span data-stu-id="54cfc-115">Requirements</span></span>  
 <span data-ttu-id="54cfc-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="54cfc-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54cfc-117">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="54cfc-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="54cfc-118">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="54cfc-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="54cfc-119">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54cfc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54cfc-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="54cfc-120">See also</span></span>

- [<span data-ttu-id="54cfc-121">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="54cfc-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
