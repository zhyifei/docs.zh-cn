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
ms.openlocfilehash: 038e2ec20e5fd01edf9835080e0f7a15ec862fd9
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008932"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="b0221-102">CorValidatorModuleType 枚举</span><span class="sxs-lookup"><span data-stu-id="b0221-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="b0221-103">指定模块的类型。</span><span class="sxs-lookup"><span data-stu-id="b0221-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0221-104">语法</span><span class="sxs-lookup"><span data-stu-id="b0221-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b0221-105">成员</span><span class="sxs-lookup"><span data-stu-id="b0221-105">Members</span></span>  
  
|<span data-ttu-id="b0221-106">成员</span><span class="sxs-lookup"><span data-stu-id="b0221-106">Member</span></span>|<span data-ttu-id="b0221-107">描述</span><span class="sxs-lookup"><span data-stu-id="b0221-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="b0221-108">模块是无效类型。</span><span class="sxs-lookup"><span data-stu-id="b0221-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="b0221-109">枚举的最小值 `CorValidatorModuleType` 。</span><span class="sxs-lookup"><span data-stu-id="b0221-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="b0221-110">模块是可移植可执行（PE）文件。</span><span class="sxs-lookup"><span data-stu-id="b0221-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="b0221-111">模块是 .obj 文件。</span><span class="sxs-lookup"><span data-stu-id="b0221-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="b0221-112">模块是 "编辑并继续" 调试器会话。</span><span class="sxs-lookup"><span data-stu-id="b0221-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="b0221-113">模块是增量生成的模块。</span><span class="sxs-lookup"><span data-stu-id="b0221-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="b0221-114">枚举的最大值 `CorValidatorModuleType` 。</span><span class="sxs-lookup"><span data-stu-id="b0221-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b0221-115">要求</span><span class="sxs-lookup"><span data-stu-id="b0221-115">Requirements</span></span>  
 <span data-ttu-id="b0221-116">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b0221-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0221-117">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="b0221-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b0221-118">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b0221-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b0221-119">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0221-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0221-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0221-120">See also</span></span>

- [<span data-ttu-id="b0221-121">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="b0221-121">Metadata Enumerations</span></span>](metadata-enumerations.md)
