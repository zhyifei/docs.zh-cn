---
title: CorNotificationForTokenMovement 枚举
ms.date: 03/30/2017
api_name:
- CorNotificationForTokenMovement
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNotificationForTokenMovement
helpviewer_keywords:
- CorNotificationForTokenMovement enumeration [.NET Framework metadata]
ms.assetid: 1edd1670-976a-4fc8-bef7-7c41e60ad989
topic_type:
- apiref
ms.openlocfilehash: 411fad0accb59431f776c5bd66e8bd3027ddd907
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450157"
---
# <a name="cornotificationfortokenmovement-enumeration"></a><span data-ttu-id="68d53-102">CorNotificationForTokenMovement 枚举</span><span class="sxs-lookup"><span data-stu-id="68d53-102">CorNotificationForTokenMovement Enumeration</span></span>
<span data-ttu-id="68d53-103">指定在进行标记重新映射时将发送到元数据 API 客户端的通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-103">Specifies the notifications that will be sent to the metadata API client when a token remap occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68d53-104">语法</span><span class="sxs-lookup"><span data-stu-id="68d53-104">Syntax</span></span>  
  
```cpp  
typedef enum CorNotificationForTokenMovement {  
  
    MDNotifyDefault             = 0x0000000f,  
    MDNotifyAll                 = 0xffffffff,  
    MDNotifyNone                = 0x00000000,  
    MDNotifyMethodDef           = 0x00000001,  
    MDNotifyMemberRef           = 0x00000002,  
    MDNotifyFieldDef            = 0x00000004,  
    MDNotifyTypeRef             = 0x00000008,  
  
    MDNotifyTypeDef             = 0x00000010,  
    MDNotifyParamDef            = 0x00000020,  
    MDNotifyInterfaceImpl       = 0x00000040,  
    MDNotifyProperty            = 0x00000080,  
    MDNotifyEvent               = 0x00000100,  
    MDNotifySignature           = 0x00000200,  
    MDNotifyTypeSpec            = 0x00000400,  
    MDNotifyCustomAttribute     = 0x00000800,  
    MDNotifySecurityValue       = 0x00001000,  
    MDNotifyPermission          = 0x00002000,  
    MDNotifyModuleRef           = 0x00004000,  
  
    MDNotifyNameSpace           = 0x00008000,  
  
    MDNotifyAssemblyRef         = 0x01000000,  
    MDNotifyFile                = 0x02000000,  
    MDNotifyExportedType        = 0x04000000,  
    MDNotifyResource            = 0x08000000  
  
} CorNotificationForTokenMovement;  
```  
  
## <a name="members"></a><span data-ttu-id="68d53-105">Members</span><span class="sxs-lookup"><span data-stu-id="68d53-105">Members</span></span>  
  
|<span data-ttu-id="68d53-106">成员</span><span class="sxs-lookup"><span data-stu-id="68d53-106">Member</span></span>|<span data-ttu-id="68d53-107">说明</span><span class="sxs-lookup"><span data-stu-id="68d53-107">Description</span></span>|  
|------------|-----------------|  
|`MDNotifyDefault`|<span data-ttu-id="68d53-108">`mdTypeRef`、`mdMethodDef`、`mdMemberRef`或 `mdFieldDef` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-108">Notify when `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, or `mdFieldDef` tokens move.</span></span>|  
|`MDNotifyAll`|<span data-ttu-id="68d53-109">任何标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-109">Notify when any token moves.</span></span>|  
|`MDNotifyNone`|<span data-ttu-id="68d53-110">标记移动时不发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-110">Do not notify when tokens move.</span></span>|  
|`MDNotifyMethodDef`|<span data-ttu-id="68d53-111">`mdMethodDef` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-111">Notify when an `mdMethodDef` token moves.</span></span>|  
|`MDNotifyMemberRef`|<span data-ttu-id="68d53-112">`mdMemberRef` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-112">Notify when an `mdMemberRef` token moves.</span></span>|  
|`MDNotifyFieldDef`|<span data-ttu-id="68d53-113">`mdFieldDef` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-113">Notify when an `mdFieldDef` token moves.</span></span>|  
|`MDNotifyTypeRef`|<span data-ttu-id="68d53-114">`mdTypeRef` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-114">Notify when an `mdTypeRef` token moves.</span></span>|  
|`MDNotifyTypeDef`|<span data-ttu-id="68d53-115">`mdTypeDef` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-115">Notify when an `mdTypeDef` token moves.</span></span>|  
|`MDNotifyParamDef`|<span data-ttu-id="68d53-116">`mdParamDef` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-116">Notify when an `mdParamDef` token moves.</span></span>|  
|`MDNotifyInterfaceImpl`|<span data-ttu-id="68d53-117">`mdInterfaceImpl` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-117">Notify when an `mdInterfaceImpl` token moves.</span></span>|  
|`MDNotifyProperty`|<span data-ttu-id="68d53-118">`mdProperty` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-118">Notify when an `mdProperty` token moves.</span></span>|  
|`MDNotifyEvent`|<span data-ttu-id="68d53-119">`mdEvent` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-119">Notify when an `mdEvent` token moves.</span></span>|  
|`MDNotifySignature`|<span data-ttu-id="68d53-120">`mdSignature` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-120">Notify when an `mdSignature` token moves.</span></span>|  
|`MDNotifyTypeSpec`|<span data-ttu-id="68d53-121">`mdTypeSpec` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-121">Notify when an `mdTypeSpec` token moves.</span></span>|  
|`MDNotifyCustomAttribute`|<span data-ttu-id="68d53-122">`mdCustomAttribute` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-122">Notify when an `mdCustomAttribute` token moves.</span></span>|  
|`MDNotifySecurityValue`|<span data-ttu-id="68d53-123">`mdSecurityValue` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-123">Notify when an `mdSecurityValue` token moves.</span></span>|  
|`MDNotifyPermission`|<span data-ttu-id="68d53-124">`mdPermission` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-124">Notify when an `mdPermission` token moves.</span></span>|  
|`MDNotifyModuleRef`|<span data-ttu-id="68d53-125">`mdModuleRef` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-125">Notify when an `mdModuleRef` token moves.</span></span>|  
|`MDNotifyNameSpace`|<span data-ttu-id="68d53-126">`mdNameSpace` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-126">Notify when an `mdNameSpace` token moves.</span></span>|  
|`MDNotifyAssemblyRef`|<span data-ttu-id="68d53-127">`mdAssemblyRef` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-127">Notify when an `mdAssemblyRef` token moves.</span></span>|  
|`MDNotifyFile`|<span data-ttu-id="68d53-128">`mdFile` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-128">Notify when an `mdFile` token moves.</span></span>|  
|`MDNotifyExportedType`|<span data-ttu-id="68d53-129">`mdExportedType` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-129">Notify when an `mdExportedType` token moves.</span></span>|  
|`MDNotifyResource`|<span data-ttu-id="68d53-130">`mdManifestResource` 标记移动时发出通知。</span><span class="sxs-lookup"><span data-stu-id="68d53-130">Notify when an `mdManifestResource` token moves.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68d53-131">备注</span><span class="sxs-lookup"><span data-stu-id="68d53-131">Remarks</span></span>  
 <span data-ttu-id="68d53-132">可在元数据合并期间重新映射（即，移动）标记。</span><span class="sxs-lookup"><span data-stu-id="68d53-132">A token may be re-mapped (that is, moved) during a metadata merge.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68d53-133">要求</span><span class="sxs-lookup"><span data-stu-id="68d53-133">Requirements</span></span>  
 <span data-ttu-id="68d53-134">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="68d53-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68d53-135">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="68d53-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="68d53-136">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68d53-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68d53-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68d53-137">See also</span></span>

- [<span data-ttu-id="68d53-138">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="68d53-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
