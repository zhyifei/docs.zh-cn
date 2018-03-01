---
title: "CeeSectionAttr 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 212d9be02a3c4ca97a6a69391ff82edb1d013d93
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="2bdc2-102">CeeSectionAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="2bdc2-102">CeeSectionAttr Enumeration</span></span>
<span data-ttu-id="2bdc2-103">提供用于指定以供节特性值[ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="2bdc2-103">Provides values that specify attributes of a section for use by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bdc2-104">语法</span><span class="sxs-lookup"><span data-stu-id="2bdc2-104">Syntax</span></span>  
  
```  
typedef enum  {  
    sdNone      = 0,  
    sdReadOnly  = IMAGE_SCN_CNT_INITIALIZED_DATA |  
                  IMAGE_SCN_MEM_READ,  
    sdReadWrite = sdReadOnly | IMAGE_SCN_MEM_WRITE,  
    sdExecute   = IMAGE_SCN_MEM_READ | IMAGE_SCN_CNT_CODE |  
                  IMAGE_SCN_MEM_EXECUTE  
} CeeSectionAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="2bdc2-105">成员</span><span class="sxs-lookup"><span data-stu-id="2bdc2-105">Members</span></span>  
  
|<span data-ttu-id="2bdc2-106">成员</span><span class="sxs-lookup"><span data-stu-id="2bdc2-106">Member</span></span>|<span data-ttu-id="2bdc2-107">描述</span><span class="sxs-lookup"><span data-stu-id="2bdc2-107">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="2bdc2-108">部分包含任何属性。</span><span class="sxs-lookup"><span data-stu-id="2bdc2-108">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="2bdc2-109">部分包含初始化只能读取，未更新的数据。</span><span class="sxs-lookup"><span data-stu-id="2bdc2-109">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="2bdc2-110">部分包含可读取或更新的初始化的数据。</span><span class="sxs-lookup"><span data-stu-id="2bdc2-110">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="2bdc2-111">部分包含允许读取和执行的可执行代码。</span><span class="sxs-lookup"><span data-stu-id="2bdc2-111">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2bdc2-112">惠?</span><span class="sxs-lookup"><span data-stu-id="2bdc2-112">Requirements</span></span>  
 <span data-ttu-id="2bdc2-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2bdc2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bdc2-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2bdc2-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2bdc2-115">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2bdc2-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2bdc2-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bdc2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bdc2-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="2bdc2-117">See Also</span></span>  
 [<span data-ttu-id="2bdc2-118">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="2bdc2-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
