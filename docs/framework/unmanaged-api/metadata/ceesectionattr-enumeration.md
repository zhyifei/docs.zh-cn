---
title: CeeSectionAttr 枚举
ms.date: 03/30/2017
api_name:
- CeeSectionAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionAttr
helpviewer_keywords:
- CeeSectionAttr enumeration [.NET Framework metadata]
ms.assetid: 0db51881-b869-4677-a715-1726a9216489
topic_type:
- apiref
ms.openlocfilehash: 97b28c961f43388679615ac0d5b19c4c69df1e3d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444251"
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="f280a-102">CeeSectionAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="f280a-102">CeeSectionAttr Enumeration</span></span>
<span data-ttu-id="f280a-103">Provides values that specify attributes of a section for use by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="f280a-103">Provides values that specify attributes of a section for use by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f280a-104">语法</span><span class="sxs-lookup"><span data-stu-id="f280a-104">Syntax</span></span>  
  
```cpp  
typedef enum  {  
    sdNone      = 0,  
    sdReadOnly  = IMAGE_SCN_CNT_INITIALIZED_DATA |  
                  IMAGE_SCN_MEM_READ,  
    sdReadWrite = sdReadOnly | IMAGE_SCN_MEM_WRITE,  
    sdExecute   = IMAGE_SCN_MEM_READ | IMAGE_SCN_CNT_CODE |  
                  IMAGE_SCN_MEM_EXECUTE  
} CeeSectionAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="f280a-105">Members</span><span class="sxs-lookup"><span data-stu-id="f280a-105">Members</span></span>  
  
|<span data-ttu-id="f280a-106">成员</span><span class="sxs-lookup"><span data-stu-id="f280a-106">Member</span></span>|<span data-ttu-id="f280a-107">描述</span><span class="sxs-lookup"><span data-stu-id="f280a-107">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="f280a-108">Section has no attributes.</span><span class="sxs-lookup"><span data-stu-id="f280a-108">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="f280a-109">Section contains initialized data that can be only read, not updated.</span><span class="sxs-lookup"><span data-stu-id="f280a-109">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="f280a-110">Section contains initialized data that can be read or updated.</span><span class="sxs-lookup"><span data-stu-id="f280a-110">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="f280a-111">Section contains executable code that is allowed to be read and executed.</span><span class="sxs-lookup"><span data-stu-id="f280a-111">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f280a-112">要求</span><span class="sxs-lookup"><span data-stu-id="f280a-112">Requirements</span></span>  
 <span data-ttu-id="f280a-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f280a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f280a-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f280a-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f280a-115">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f280a-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f280a-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f280a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f280a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="f280a-117">See also</span></span>

- [<span data-ttu-id="f280a-118">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="f280a-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
