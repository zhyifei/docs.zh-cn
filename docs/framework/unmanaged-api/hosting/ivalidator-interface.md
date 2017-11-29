---
title: "IValidator 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IValidator
api_location: mscoree.dll
api_type: COM
f1_keywords: IValidator
helpviewer_keywords: IValidator interface [.NET Framework hosting]
ms.assetid: b297e3b0-20f9-478f-b707-5e2eecb2b5b2
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7d88bfa0a3e71f34a7439e97f4347a06aa2c4058
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ivalidator-interface"></a><span data-ttu-id="a80f3-102">IValidator 接口</span><span class="sxs-lookup"><span data-stu-id="a80f3-102">IValidator Interface</span></span>
<span data-ttu-id="a80f3-103">提供用于验证可移植可执行 (PE) 映像和报告验证错误的方法。</span><span class="sxs-lookup"><span data-stu-id="a80f3-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a80f3-104">方法</span><span class="sxs-lookup"><span data-stu-id="a80f3-104">Methods</span></span>  
  
|<span data-ttu-id="a80f3-105">方法</span><span class="sxs-lookup"><span data-stu-id="a80f3-105">Method</span></span>|<span data-ttu-id="a80f3-106">描述</span><span class="sxs-lookup"><span data-stu-id="a80f3-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a80f3-107">Validate</span><span class="sxs-lookup"><span data-stu-id="a80f3-107">Validate</span></span>|<span data-ttu-id="a80f3-108">验证指定的 PE 或 Microsoft 中间语言 (MSIL) 文件。</span><span class="sxs-lookup"><span data-stu-id="a80f3-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="a80f3-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="a80f3-109">FormatEventInfo</span></span>|<span data-ttu-id="a80f3-110">获取对应于指定的验证错误的错误消息。</span><span class="sxs-lookup"><span data-stu-id="a80f3-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a80f3-111">要求</span><span class="sxs-lookup"><span data-stu-id="a80f3-111">Requirements</span></span>  
 <span data-ttu-id="a80f3-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a80f3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a80f3-113">**标头：** IValidator.idl、 IValidator.h</span><span class="sxs-lookup"><span data-stu-id="a80f3-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="a80f3-114">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a80f3-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a80f3-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a80f3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a80f3-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a80f3-116">See Also</span></span>  
 [<span data-ttu-id="a80f3-117">承载接口</span><span class="sxs-lookup"><span data-stu-id="a80f3-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="a80f3-118">CorRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="a80f3-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
