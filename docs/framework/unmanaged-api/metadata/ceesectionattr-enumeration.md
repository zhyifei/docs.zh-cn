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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c317524cefd7ed654e76bdd7051cdcd7653062db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905887"
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="ef9f6-102">CeeSectionAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="ef9f6-102">CeeSectionAttr Enumeration</span></span>
<span data-ttu-id="ef9f6-103">提供用于指定以供节的特性值[ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="ef9f6-103">Provides values that specify attributes of a section for use by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef9f6-104">语法</span><span class="sxs-lookup"><span data-stu-id="ef9f6-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ef9f6-105">成员</span><span class="sxs-lookup"><span data-stu-id="ef9f6-105">Members</span></span>  
  
|<span data-ttu-id="ef9f6-106">成员</span><span class="sxs-lookup"><span data-stu-id="ef9f6-106">Member</span></span>|<span data-ttu-id="ef9f6-107">描述</span><span class="sxs-lookup"><span data-stu-id="ef9f6-107">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="ef9f6-108">部分没有任何属性。</span><span class="sxs-lookup"><span data-stu-id="ef9f6-108">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="ef9f6-109">部分包含初始化的数据，可以仅读取，不会更新。</span><span class="sxs-lookup"><span data-stu-id="ef9f6-109">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="ef9f6-110">部分包含初始化的数据可读取或更新。</span><span class="sxs-lookup"><span data-stu-id="ef9f6-110">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="ef9f6-111">部分包含可执行代码，允许读取和执行。</span><span class="sxs-lookup"><span data-stu-id="ef9f6-111">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ef9f6-112">要求</span><span class="sxs-lookup"><span data-stu-id="ef9f6-112">Requirements</span></span>  
 <span data-ttu-id="ef9f6-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ef9f6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef9f6-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ef9f6-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ef9f6-115">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ef9f6-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ef9f6-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef9f6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef9f6-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef9f6-117">See also</span></span>

- [<span data-ttu-id="ef9f6-118">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="ef9f6-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
