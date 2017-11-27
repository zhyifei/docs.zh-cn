---
title: "CLRRuntimeHost 组件类"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLRRuntimeHost Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CLRRuntimeHost
helpviewer_keywords: CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 372b2466baaa76ba47a6710447d93f9fa6bb967f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="a3823-102">CLRRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="a3823-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="a3823-103">用于管理代码执行的运行时提供的接口。</span><span class="sxs-lookup"><span data-stu-id="a3823-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3823-104">语法</span><span class="sxs-lookup"><span data-stu-id="a3823-104">Syntax</span></span>  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="a3823-105">接口</span><span class="sxs-lookup"><span data-stu-id="a3823-105">Interfaces</span></span>  
  
|<span data-ttu-id="a3823-106">接口</span><span class="sxs-lookup"><span data-stu-id="a3823-106">Interface</span></span>|<span data-ttu-id="a3823-107">描述</span><span class="sxs-lookup"><span data-stu-id="a3823-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="a3823-108">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="a3823-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="a3823-109">提供由运行时控制应用程序的执行的方法。</span><span class="sxs-lookup"><span data-stu-id="a3823-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="a3823-110">ICLRValidator 接口</span><span class="sxs-lookup"><span data-stu-id="a3823-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="a3823-111">提供一些方法的可移植可执行映像的验证和验证错误的详细报告。</span><span class="sxs-lookup"><span data-stu-id="a3823-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a3823-112">要求</span><span class="sxs-lookup"><span data-stu-id="a3823-112">Requirements</span></span>  
 <span data-ttu-id="a3823-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a3823-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3823-114">**标头：** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="a3823-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="a3823-115">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a3823-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3823-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3823-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3823-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3823-117">See Also</span></span>  
 [<span data-ttu-id="a3823-118">承载组件类</span><span class="sxs-lookup"><span data-stu-id="a3823-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
