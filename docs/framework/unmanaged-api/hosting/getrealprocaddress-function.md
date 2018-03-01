---
title: "GetRealProcAddress 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- GetRealProcAddress
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRealProcAddress
helpviewer_keywords:
- GetRealProcAddress function [.NET Framework hosting]
ms.assetid: f1f2fab1-400b-488f-95f2-d49c4fca3556
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5ade1c902d00e991612406041ef0a0b2c1bb884e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="b9125-102">GetRealProcAddress 函数</span><span class="sxs-lookup"><span data-stu-id="b9125-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="b9125-103">获取指定从最新的安装公共语言运行时 (CLR) 版本导出的函数的地址。</span><span class="sxs-lookup"><span data-stu-id="b9125-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="b9125-104">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b9125-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9125-105">语法</span><span class="sxs-lookup"><span data-stu-id="b9125-105">Syntax</span></span>  
  
```  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9125-106">参数</span><span class="sxs-lookup"><span data-stu-id="b9125-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="b9125-107">[in]函数的名称。</span><span class="sxs-lookup"><span data-stu-id="b9125-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="b9125-108">[out]接收指向函数的地址的位置。</span><span class="sxs-lookup"><span data-stu-id="b9125-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9125-109">返回值</span><span class="sxs-lookup"><span data-stu-id="b9125-109">Return Value</span></span>  
 <span data-ttu-id="b9125-110">定义在 WinError.h，除了 CorError.h 中定义的以下值时，此方法将返回标准组件对象模型 (COM) 错误代码。</span><span class="sxs-lookup"><span data-stu-id="b9125-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="b9125-111">返回代码</span><span class="sxs-lookup"><span data-stu-id="b9125-111">Return code</span></span>|<span data-ttu-id="b9125-112">描述</span><span class="sxs-lookup"><span data-stu-id="b9125-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="b9125-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b9125-113">S_OK</span></span>|<span data-ttu-id="b9125-114">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="b9125-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="b9125-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b9125-115">E_POINTER</span></span>|<span data-ttu-id="b9125-116">`ppv` 无效。</span><span class="sxs-lookup"><span data-stu-id="b9125-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="b9125-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="b9125-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="b9125-118">不会在运行时中导出函数。</span><span class="sxs-lookup"><span data-stu-id="b9125-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b9125-119">惠?</span><span class="sxs-lookup"><span data-stu-id="b9125-119">Requirements</span></span>  
 <span data-ttu-id="b9125-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b9125-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9125-121">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b9125-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b9125-122">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b9125-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9125-123">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9125-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9125-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9125-124">See Also</span></span>  
 [<span data-ttu-id="b9125-125">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="b9125-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
