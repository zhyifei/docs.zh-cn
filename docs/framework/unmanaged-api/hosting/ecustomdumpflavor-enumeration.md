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
ms.openlocfilehash: b6d0ba3f722f63650a3db6a8f633189993db0716
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431403"
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="cc5a0-102">ECustomDumpFlavor 枚举</span><span class="sxs-lookup"><span data-stu-id="cc5a0-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="cc5a0-103">包含值，用于指示哪些项目应包含自定义子集中的堆转储时报告错误。</span><span class="sxs-lookup"><span data-stu-id="cc5a0-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc5a0-104">语法</span><span class="sxs-lookup"><span data-stu-id="cc5a0-104">Syntax</span></span>  
  
```  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="cc5a0-105">成员</span><span class="sxs-lookup"><span data-stu-id="cc5a0-105">Members</span></span>  
  
|<span data-ttu-id="cc5a0-106">成员</span><span class="sxs-lookup"><span data-stu-id="cc5a0-106">Member</span></span>|<span data-ttu-id="cc5a0-107">描述</span><span class="sxs-lookup"><span data-stu-id="cc5a0-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="cc5a0-108">指定自定义的堆转储应该以小型转储启动并包含指定的任何额外数据[CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)实例传递给相同的方法。</span><span class="sxs-lookup"><span data-stu-id="cc5a0-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="cc5a0-109">指定自定义的堆转储应收集未动态分配的所有运行时状态数据。</span><span class="sxs-lookup"><span data-stu-id="cc5a0-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc5a0-110">备注</span><span class="sxs-lookup"><span data-stu-id="cc5a0-110">Remarks</span></span>  
 <span data-ttu-id="cc5a0-111">类型的参数`ECustomDumpFlavor`传递给[iclrerrorreportingmanager:: Begincustomdump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="cc5a0-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc5a0-112">要求</span><span class="sxs-lookup"><span data-stu-id="cc5a0-112">Requirements</span></span>  
 <span data-ttu-id="cc5a0-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cc5a0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc5a0-114">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cc5a0-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cc5a0-115">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cc5a0-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc5a0-116">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc5a0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc5a0-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc5a0-117">See Also</span></span>  
 [<span data-ttu-id="cc5a0-118">ECustomDumpItemKind 枚举</span><span class="sxs-lookup"><span data-stu-id="cc5a0-118">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [<span data-ttu-id="cc5a0-119">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="cc5a0-119">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [<span data-ttu-id="cc5a0-120">承载枚举</span><span class="sxs-lookup"><span data-stu-id="cc5a0-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
