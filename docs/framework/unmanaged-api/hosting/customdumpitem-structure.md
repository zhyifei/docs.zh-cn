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
ms.openlocfilehash: ae64edd8a3a628100d4c51d0b78be1bc8d49fc17
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138282"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="6d661-102">CustomDumpItem 结构</span><span class="sxs-lookup"><span data-stu-id="6d661-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="6d661-103">描述要添加到错误报告中的自定义转储的项。</span><span class="sxs-lookup"><span data-stu-id="6d661-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d661-104">语法</span><span class="sxs-lookup"><span data-stu-id="6d661-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="6d661-105">Members</span><span class="sxs-lookup"><span data-stu-id="6d661-105">Members</span></span>  
  
|<span data-ttu-id="6d661-106">成员</span><span class="sxs-lookup"><span data-stu-id="6d661-106">Member</span></span>|<span data-ttu-id="6d661-107">描述</span><span class="sxs-lookup"><span data-stu-id="6d661-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="6d661-108">一个[ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)值，指示要添加的项的类型。</span><span class="sxs-lookup"><span data-stu-id="6d661-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="6d661-109">当前未使用。</span><span class="sxs-lookup"><span data-stu-id="6d661-109">Not currently used.</span></span> <span data-ttu-id="6d661-110">添加到联合的任何项都必须不大于指针大小。</span><span class="sxs-lookup"><span data-stu-id="6d661-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="6d661-111">如果 `struct` 是必需的，则必须单独分配，并指向该。</span><span class="sxs-lookup"><span data-stu-id="6d661-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d661-112">备注</span><span class="sxs-lookup"><span data-stu-id="6d661-112">Remarks</span></span>  
 <span data-ttu-id="6d661-113">[ICLRErrorReportingManager：： BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)使用 `CustomDumpItem`类型的参数。</span><span class="sxs-lookup"><span data-stu-id="6d661-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d661-114">要求</span><span class="sxs-lookup"><span data-stu-id="6d661-114">Requirements</span></span>  
 <span data-ttu-id="6d661-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6d661-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d661-116">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6d661-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="6d661-117">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="6d661-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d661-118">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d661-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d661-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d661-119">See also</span></span>

- [<span data-ttu-id="6d661-120">承载结构</span><span class="sxs-lookup"><span data-stu-id="6d661-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
