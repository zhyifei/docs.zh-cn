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
ms.openlocfilehash: b1e595e1a4f1b462437f47207b998829a8bd774d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129452"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="8f89c-102">CLRRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="8f89c-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="8f89c-103">提供用于管理运行时执行的代码的接口。</span><span class="sxs-lookup"><span data-stu-id="8f89c-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f89c-104">语法</span><span class="sxs-lookup"><span data-stu-id="8f89c-104">Syntax</span></span>  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="8f89c-105">接口</span><span class="sxs-lookup"><span data-stu-id="8f89c-105">Interfaces</span></span>  
  
|<span data-ttu-id="8f89c-106">接口</span><span class="sxs-lookup"><span data-stu-id="8f89c-106">Interface</span></span>|<span data-ttu-id="8f89c-107">描述</span><span class="sxs-lookup"><span data-stu-id="8f89c-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="8f89c-108">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="8f89c-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="8f89c-109">提供通过运行时控制应用程序执行的方法。</span><span class="sxs-lookup"><span data-stu-id="8f89c-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="8f89c-110">ICLRValidator 接口</span><span class="sxs-lookup"><span data-stu-id="8f89c-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="8f89c-111">提供可移植可执行映像的验证方法，并提供验证错误的详细报告。</span><span class="sxs-lookup"><span data-stu-id="8f89c-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8f89c-112">要求</span><span class="sxs-lookup"><span data-stu-id="8f89c-112">Requirements</span></span>  
 <span data-ttu-id="8f89c-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8f89c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f89c-114">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8f89c-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="8f89c-115">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8f89c-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f89c-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f89c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f89c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f89c-117">See also</span></span>

- [<span data-ttu-id="8f89c-118">承载组件类</span><span class="sxs-lookup"><span data-stu-id="8f89c-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
