---
title: "ECustomDumpFlavor 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ECustomDumpFlavor
api_location: mscoree.dll
api_type: COM
f1_keywords: ECustomDumpFlavor
helpviewer_keywords: ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a7317a3a12acef2a16deebab9a1e1b10205ebf6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="f9cf8-102">ECustomDumpFlavor 枚举</span><span class="sxs-lookup"><span data-stu-id="f9cf8-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="f9cf8-103">包含值，用于指示哪些项目应包含自定义子集中的堆转储时报告错误。</span><span class="sxs-lookup"><span data-stu-id="f9cf8-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9cf8-104">语法</span><span class="sxs-lookup"><span data-stu-id="f9cf8-104">Syntax</span></span>  
  
```  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="f9cf8-105">成员</span><span class="sxs-lookup"><span data-stu-id="f9cf8-105">Members</span></span>  
  
|<span data-ttu-id="f9cf8-106">成员</span><span class="sxs-lookup"><span data-stu-id="f9cf8-106">Member</span></span>|<span data-ttu-id="f9cf8-107">描述</span><span class="sxs-lookup"><span data-stu-id="f9cf8-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="f9cf8-108">指定自定义的堆转储应该以小型转储启动并包含指定的任何额外数据[CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)实例传递给相同的方法。</span><span class="sxs-lookup"><span data-stu-id="f9cf8-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="f9cf8-109">指定自定义的堆转储应收集未动态分配的所有运行时状态数据。</span><span class="sxs-lookup"><span data-stu-id="f9cf8-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9cf8-110">备注</span><span class="sxs-lookup"><span data-stu-id="f9cf8-110">Remarks</span></span>  
 <span data-ttu-id="f9cf8-111">类型的参数`ECustomDumpFlavor`传递给[iclrerrorreportingmanager:: Begincustomdump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="f9cf8-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9cf8-112">要求</span><span class="sxs-lookup"><span data-stu-id="f9cf8-112">Requirements</span></span>  
 <span data-ttu-id="f9cf8-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f9cf8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9cf8-114">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f9cf8-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f9cf8-115">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f9cf8-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f9cf8-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9cf8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9cf8-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9cf8-117">See Also</span></span>  
 [<span data-ttu-id="f9cf8-118">ECustomDumpItemKind 枚举</span><span class="sxs-lookup"><span data-stu-id="f9cf8-118">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [<span data-ttu-id="f9cf8-119">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="f9cf8-119">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [<span data-ttu-id="f9cf8-120">承载枚举</span><span class="sxs-lookup"><span data-stu-id="f9cf8-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
