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
ms.openlocfilehash: 14eee096c25967d321e4693b260501827d944a80
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045170"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="245a1-102">CorValidatorModuleType 枚举</span><span class="sxs-lookup"><span data-stu-id="245a1-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="245a1-103">指定模块的类型。</span><span class="sxs-lookup"><span data-stu-id="245a1-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="245a1-104">语法</span><span class="sxs-lookup"><span data-stu-id="245a1-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="245a1-105">成员</span><span class="sxs-lookup"><span data-stu-id="245a1-105">Members</span></span>  
  
|<span data-ttu-id="245a1-106">成员</span><span class="sxs-lookup"><span data-stu-id="245a1-106">Member</span></span>|<span data-ttu-id="245a1-107">描述</span><span class="sxs-lookup"><span data-stu-id="245a1-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="245a1-108">该模块是无效的类型。</span><span class="sxs-lookup"><span data-stu-id="245a1-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="245a1-109">最小值`CorValidatorModuleType`枚举。</span><span class="sxs-lookup"><span data-stu-id="245a1-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="245a1-110">该模块是可移植可执行 (PE) 文件。</span><span class="sxs-lookup"><span data-stu-id="245a1-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="245a1-111">该模块是.obj 文件。</span><span class="sxs-lookup"><span data-stu-id="245a1-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="245a1-112">该模块是编辑并继续调试程序会话。</span><span class="sxs-lookup"><span data-stu-id="245a1-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="245a1-113">该模块是指以增量方式生成。</span><span class="sxs-lookup"><span data-stu-id="245a1-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="245a1-114">最大值`CorValidatorModuleType`枚举。</span><span class="sxs-lookup"><span data-stu-id="245a1-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="245a1-115">要求</span><span class="sxs-lookup"><span data-stu-id="245a1-115">Requirements</span></span>  
 <span data-ttu-id="245a1-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="245a1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="245a1-117">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="245a1-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="245a1-118">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="245a1-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="245a1-119">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="245a1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="245a1-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="245a1-120">See also</span></span>

- [<span data-ttu-id="245a1-121">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="245a1-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
