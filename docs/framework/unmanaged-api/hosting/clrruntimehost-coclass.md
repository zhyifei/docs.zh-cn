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
ms.openlocfilehash: 40766ce5837053493f2e3f1f25fe7d1d63ec695f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616795"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="43d55-102">CLRRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="43d55-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="43d55-103">提供用于管理运行时执行的代码的接口。</span><span class="sxs-lookup"><span data-stu-id="43d55-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43d55-104">语法</span><span class="sxs-lookup"><span data-stu-id="43d55-104">Syntax</span></span>  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="43d55-105">接口</span><span class="sxs-lookup"><span data-stu-id="43d55-105">Interfaces</span></span>  
  
|<span data-ttu-id="43d55-106">接口</span><span class="sxs-lookup"><span data-stu-id="43d55-106">Interface</span></span>|<span data-ttu-id="43d55-107">说明</span><span class="sxs-lookup"><span data-stu-id="43d55-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="43d55-108">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="43d55-108">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)|<span data-ttu-id="43d55-109">提供通过运行时控制应用程序执行的方法。</span><span class="sxs-lookup"><span data-stu-id="43d55-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="43d55-110">ICLRValidator 接口</span><span class="sxs-lookup"><span data-stu-id="43d55-110">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)|<span data-ttu-id="43d55-111">提供可移植可执行映像的验证方法，并提供验证错误的详细报告。</span><span class="sxs-lookup"><span data-stu-id="43d55-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="43d55-112">要求</span><span class="sxs-lookup"><span data-stu-id="43d55-112">Requirements</span></span>  
 <span data-ttu-id="43d55-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="43d55-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43d55-114">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="43d55-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="43d55-115">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="43d55-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43d55-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43d55-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43d55-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43d55-117">See also</span></span>

- [<span data-ttu-id="43d55-118">承载 Coclass</span><span class="sxs-lookup"><span data-stu-id="43d55-118">Hosting Coclasses</span></span>](hosting-coclasses.md)
