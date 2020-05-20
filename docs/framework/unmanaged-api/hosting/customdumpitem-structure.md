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
ms.openlocfilehash: 5c77a332593ba470d2e29b87cba182a770d5db7e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616432"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="3fc1a-102">CustomDumpItem 结构</span><span class="sxs-lookup"><span data-stu-id="3fc1a-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="3fc1a-103">描述要添加到错误报告中的自定义转储的项。</span><span class="sxs-lookup"><span data-stu-id="3fc1a-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fc1a-104">语法</span><span class="sxs-lookup"><span data-stu-id="3fc1a-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="3fc1a-105">成员</span><span class="sxs-lookup"><span data-stu-id="3fc1a-105">Members</span></span>  
  
|<span data-ttu-id="3fc1a-106">成员</span><span class="sxs-lookup"><span data-stu-id="3fc1a-106">Member</span></span>|<span data-ttu-id="3fc1a-107">描述</span><span class="sxs-lookup"><span data-stu-id="3fc1a-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="3fc1a-108">一个[ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md)值，指示要添加的项的类型。</span><span class="sxs-lookup"><span data-stu-id="3fc1a-108">An [ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="3fc1a-109">当前未使用。</span><span class="sxs-lookup"><span data-stu-id="3fc1a-109">Not currently used.</span></span> <span data-ttu-id="3fc1a-110">添加到联合的任何项都必须不大于指针大小。</span><span class="sxs-lookup"><span data-stu-id="3fc1a-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="3fc1a-111">如果 `struct` 需要，您必须单独分配并指向它。</span><span class="sxs-lookup"><span data-stu-id="3fc1a-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fc1a-112">备注</span><span class="sxs-lookup"><span data-stu-id="3fc1a-112">Remarks</span></span>  
 <span data-ttu-id="3fc1a-113">[ICLRErrorReportingManager：： BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md)采用类型为的参数 `CustomDumpItem` 。</span><span class="sxs-lookup"><span data-stu-id="3fc1a-113">[ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fc1a-114">要求</span><span class="sxs-lookup"><span data-stu-id="3fc1a-114">Requirements</span></span>  
 <span data-ttu-id="3fc1a-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3fc1a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fc1a-116">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3fc1a-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="3fc1a-117">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="3fc1a-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3fc1a-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fc1a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fc1a-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3fc1a-119">See also</span></span>

- [<span data-ttu-id="3fc1a-120">承载结构</span><span class="sxs-lookup"><span data-stu-id="3fc1a-120">Hosting Structures</span></span>](hosting-structures.md)
