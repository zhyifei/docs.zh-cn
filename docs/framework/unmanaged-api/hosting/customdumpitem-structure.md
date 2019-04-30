---
title: CustomDumpItem 结构
ms.date: 03/30/2017
api_name:
- CustomDumpItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CustomDumpItem
helpviewer_keywords:
- CustomDumpItem structure [.NET Framework hosting]
ms.assetid: fd9085ff-7beb-4c38-97f0-037cd8ba4f65
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9000f35e9a8f7ecc6c40cf0ef9c220fc9f4f9c10
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985681"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="1f135-102">CustomDumpItem 结构</span><span class="sxs-lookup"><span data-stu-id="1f135-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="1f135-103">描述要添加到错误报告中的自定义转储的项。</span><span class="sxs-lookup"><span data-stu-id="1f135-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f135-104">语法</span><span class="sxs-lookup"><span data-stu-id="1f135-104">Syntax</span></span>  
  
```  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="1f135-105">成员</span><span class="sxs-lookup"><span data-stu-id="1f135-105">Members</span></span>  
  
|<span data-ttu-id="1f135-106">成员</span><span class="sxs-lookup"><span data-stu-id="1f135-106">Member</span></span>|<span data-ttu-id="1f135-107">描述</span><span class="sxs-lookup"><span data-stu-id="1f135-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="1f135-108">[ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)值，该值指示要添加项的类型。</span><span class="sxs-lookup"><span data-stu-id="1f135-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="1f135-109">当前未使用。</span><span class="sxs-lookup"><span data-stu-id="1f135-109">Not currently used.</span></span> <span data-ttu-id="1f135-110">添加要联合的任何项必须是不大于指针大小。</span><span class="sxs-lookup"><span data-stu-id="1f135-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="1f135-111">如果`struct`是必需的必须单独分配，并指向它。</span><span class="sxs-lookup"><span data-stu-id="1f135-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f135-112">备注</span><span class="sxs-lookup"><span data-stu-id="1f135-112">Remarks</span></span>  
 <span data-ttu-id="1f135-113">[Iclrerrorreportingmanager:: Begincustomdump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)采用的类型参数`CustomDumpItem`。</span><span class="sxs-lookup"><span data-stu-id="1f135-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f135-114">要求</span><span class="sxs-lookup"><span data-stu-id="1f135-114">Requirements</span></span>  
 <span data-ttu-id="1f135-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1f135-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f135-116">**标头：** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="1f135-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="1f135-117">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1f135-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1f135-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f135-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f135-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f135-119">See also</span></span>

- [<span data-ttu-id="1f135-120">承载结构</span><span class="sxs-lookup"><span data-stu-id="1f135-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
