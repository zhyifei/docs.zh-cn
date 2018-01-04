---
title: "CorValidatorModuleType 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorValidatorModuleType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorValidatorModuleType
helpviewer_keywords: CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3367f6928b5d7378b2686185ee3e03d0279cc11d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="b929f-102">CorValidatorModuleType 枚举</span><span class="sxs-lookup"><span data-stu-id="b929f-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="b929f-103">指定模块的类型。</span><span class="sxs-lookup"><span data-stu-id="b929f-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b929f-104">语法</span><span class="sxs-lookup"><span data-stu-id="b929f-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b929f-105">成员</span><span class="sxs-lookup"><span data-stu-id="b929f-105">Members</span></span>  
  
|<span data-ttu-id="b929f-106">成员</span><span class="sxs-lookup"><span data-stu-id="b929f-106">Member</span></span>|<span data-ttu-id="b929f-107">描述</span><span class="sxs-lookup"><span data-stu-id="b929f-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="b929f-108">该模块是无效的类型。</span><span class="sxs-lookup"><span data-stu-id="b929f-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="b929f-109">最小值`CorValidatorModuleType`枚举。</span><span class="sxs-lookup"><span data-stu-id="b929f-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="b929f-110">模块是一个可移植可执行 (PE) 文件。</span><span class="sxs-lookup"><span data-stu-id="b929f-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="b929f-111">模块是一个.obj 文件。</span><span class="sxs-lookup"><span data-stu-id="b929f-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="b929f-112">该模块是编辑并继续调试器会话。</span><span class="sxs-lookup"><span data-stu-id="b929f-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="b929f-113">该模块是指以增量方式生成。</span><span class="sxs-lookup"><span data-stu-id="b929f-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="b929f-114">最大值`CorValidatorModuleType`枚举。</span><span class="sxs-lookup"><span data-stu-id="b929f-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b929f-115">惠?</span><span class="sxs-lookup"><span data-stu-id="b929f-115">Requirements</span></span>  
 <span data-ttu-id="b929f-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b929f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b929f-117">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b929f-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b929f-118">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b929f-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b929f-119">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b929f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b929f-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="b929f-120">See Also</span></span>  
 [<span data-ttu-id="b929f-121">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="b929f-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
