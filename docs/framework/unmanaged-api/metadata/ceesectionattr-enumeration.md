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
ms.openlocfilehash: 6da8a111f716906e403d85bc0b1a29eba7238100
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006059"
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="6a20c-102">CeeSectionAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="6a20c-102">CeeSectionAttr Enumeration</span></span>
<span data-ttu-id="6a20c-103">提供指定节的属性的值，供[ICeeGen](iceegen-interface.md)接口使用。</span><span class="sxs-lookup"><span data-stu-id="6a20c-103">Provides values that specify attributes of a section for use by the [ICeeGen](iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a20c-104">语法</span><span class="sxs-lookup"><span data-stu-id="6a20c-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="6a20c-105">成员</span><span class="sxs-lookup"><span data-stu-id="6a20c-105">Members</span></span>  
  
|<span data-ttu-id="6a20c-106">成员</span><span class="sxs-lookup"><span data-stu-id="6a20c-106">Member</span></span>|<span data-ttu-id="6a20c-107">描述</span><span class="sxs-lookup"><span data-stu-id="6a20c-107">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="6a20c-108">节没有特性。</span><span class="sxs-lookup"><span data-stu-id="6a20c-108">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="6a20c-109">部分包含初始化的数据，该数据只能读取，而不是更新。</span><span class="sxs-lookup"><span data-stu-id="6a20c-109">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="6a20c-110">节包含可读取或更新的初始化数据。</span><span class="sxs-lookup"><span data-stu-id="6a20c-110">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="6a20c-111">部分包含允许读取和执行的可执行代码。</span><span class="sxs-lookup"><span data-stu-id="6a20c-111">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6a20c-112">要求</span><span class="sxs-lookup"><span data-stu-id="6a20c-112">Requirements</span></span>  
 <span data-ttu-id="6a20c-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6a20c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a20c-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="6a20c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6a20c-115">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="6a20c-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6a20c-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a20c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a20c-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a20c-117">See also</span></span>

- [<span data-ttu-id="6a20c-118">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="6a20c-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
