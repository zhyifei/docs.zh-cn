---
title: ECustomDumpFlavor 枚举
ms.date: 03/30/2017
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a416a51f5121f29d373fcfdfa6b0597d9b10ded5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779378"
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="fd5be-102">ECustomDumpFlavor 枚举</span><span class="sxs-lookup"><span data-stu-id="fd5be-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="fd5be-103">包含指示要包含堆的自定义子集中的项转储报告错误时的值。</span><span class="sxs-lookup"><span data-stu-id="fd5be-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd5be-104">语法</span><span class="sxs-lookup"><span data-stu-id="fd5be-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="fd5be-105">成员</span><span class="sxs-lookup"><span data-stu-id="fd5be-105">Members</span></span>  
  
|<span data-ttu-id="fd5be-106">成员</span><span class="sxs-lookup"><span data-stu-id="fd5be-106">Member</span></span>|<span data-ttu-id="fd5be-107">描述</span><span class="sxs-lookup"><span data-stu-id="fd5be-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="fd5be-108">指定应启动作为小型转储并包括指定的任何额外数据自定义堆转储[CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)实例传递给相同的方法。</span><span class="sxs-lookup"><span data-stu-id="fd5be-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="fd5be-109">指定自定义堆转储应收集不动态分配的所有运行时状态数据。</span><span class="sxs-lookup"><span data-stu-id="fd5be-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd5be-110">备注</span><span class="sxs-lookup"><span data-stu-id="fd5be-110">Remarks</span></span>  
 <span data-ttu-id="fd5be-111">类型的参数`ECustomDumpFlavor`传递给[iclrerrorreportingmanager:: Begincustomdump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="fd5be-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd5be-112">要求</span><span class="sxs-lookup"><span data-stu-id="fd5be-112">Requirements</span></span>  
 <span data-ttu-id="fd5be-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fd5be-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd5be-114">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fd5be-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd5be-115">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fd5be-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd5be-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd5be-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd5be-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd5be-117">See also</span></span>

- [<span data-ttu-id="fd5be-118">ECustomDumpItemKind 枚举</span><span class="sxs-lookup"><span data-stu-id="fd5be-118">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="fd5be-119">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="fd5be-119">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="fd5be-120">承载枚举</span><span class="sxs-lookup"><span data-stu-id="fd5be-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
