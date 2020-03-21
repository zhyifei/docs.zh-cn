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
ms.openlocfilehash: 154beef9398029f31dcb4d081019b9f292238af4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176469"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="6955e-102">CustomDumpItem 结构</span><span class="sxs-lookup"><span data-stu-id="6955e-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="6955e-103">描述要在错误报告中添加到自定义转储的项。</span><span class="sxs-lookup"><span data-stu-id="6955e-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6955e-104">语法</span><span class="sxs-lookup"><span data-stu-id="6955e-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="6955e-105">成员</span><span class="sxs-lookup"><span data-stu-id="6955e-105">Members</span></span>  
  
|<span data-ttu-id="6955e-106">成员</span><span class="sxs-lookup"><span data-stu-id="6955e-106">Member</span></span>|<span data-ttu-id="6955e-107">说明</span><span class="sxs-lookup"><span data-stu-id="6955e-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="6955e-108">[ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)值，指示要添加的项类型。</span><span class="sxs-lookup"><span data-stu-id="6955e-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="6955e-109">当前未使用。</span><span class="sxs-lookup"><span data-stu-id="6955e-109">Not currently used.</span></span> <span data-ttu-id="6955e-110">添加到联合的任何项必须不大于指针大小。</span><span class="sxs-lookup"><span data-stu-id="6955e-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="6955e-111">如果需要`struct`， 必须单独分配并指向它。</span><span class="sxs-lookup"><span data-stu-id="6955e-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6955e-112">备注</span><span class="sxs-lookup"><span data-stu-id="6955e-112">Remarks</span></span>  
 <span data-ttu-id="6955e-113">[ICLR错误报告管理器：开始自定义转储](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)采用类型的`CustomDumpItem`参数。</span><span class="sxs-lookup"><span data-stu-id="6955e-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6955e-114">要求</span><span class="sxs-lookup"><span data-stu-id="6955e-114">Requirements</span></span>  
 <span data-ttu-id="6955e-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6955e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6955e-116">**标题：** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="6955e-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="6955e-117">**库：** 作为资源包含在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="6955e-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6955e-118">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6955e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6955e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6955e-119">See also</span></span>

- [<span data-ttu-id="6955e-120">承载结构</span><span class="sxs-lookup"><span data-stu-id="6955e-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
