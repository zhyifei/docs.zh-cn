---
title: CLRRuntimeHost 组件类
ms.date: 03/30/2017
api_name:
- CLRRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLRRuntimeHost
helpviewer_keywords:
- CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bae2d134c412023d0f126453b5285662d994c78
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207755"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="6d81a-102">CLRRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="6d81a-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="6d81a-103">提供用于管理由运行时执行代码的接口。</span><span class="sxs-lookup"><span data-stu-id="6d81a-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d81a-104">语法</span><span class="sxs-lookup"><span data-stu-id="6d81a-104">Syntax</span></span>  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="6d81a-105">接口</span><span class="sxs-lookup"><span data-stu-id="6d81a-105">Interfaces</span></span>  
  
|<span data-ttu-id="6d81a-106">接口</span><span class="sxs-lookup"><span data-stu-id="6d81a-106">Interface</span></span>|<span data-ttu-id="6d81a-107">描述</span><span class="sxs-lookup"><span data-stu-id="6d81a-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="6d81a-108">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="6d81a-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="6d81a-109">提供由运行时控制的应用程序执行的方法。</span><span class="sxs-lookup"><span data-stu-id="6d81a-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="6d81a-110">ICLRValidator 接口</span><span class="sxs-lookup"><span data-stu-id="6d81a-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="6d81a-111">提供了用于验证的可移植可执行映像和详细报告验证错误的方法。</span><span class="sxs-lookup"><span data-stu-id="6d81a-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6d81a-112">要求</span><span class="sxs-lookup"><span data-stu-id="6d81a-112">Requirements</span></span>  
 <span data-ttu-id="6d81a-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6d81a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d81a-114">**标头：** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="6d81a-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="6d81a-115">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6d81a-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d81a-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d81a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d81a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d81a-117">See also</span></span>

- [<span data-ttu-id="6d81a-118">承载组件类</span><span class="sxs-lookup"><span data-stu-id="6d81a-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
