---
title: "GetRealProcAddress 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetRealProcAddress
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetRealProcAddress
helpviewer_keywords: GetRealProcAddress function [.NET Framework hosting]
ms.assetid: f1f2fab1-400b-488f-95f2-d49c4fca3556
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 53e51bcf72f1a59f5c471564022d0d8c415381a6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="e111e-102">GetRealProcAddress 函数</span><span class="sxs-lookup"><span data-stu-id="e111e-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="e111e-103">获取指定从最新的安装公共语言运行时 (CLR) 版本导出的函数的地址。</span><span class="sxs-lookup"><span data-stu-id="e111e-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="e111e-104">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e111e-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e111e-105">语法</span><span class="sxs-lookup"><span data-stu-id="e111e-105">Syntax</span></span>  
  
```  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e111e-106">参数</span><span class="sxs-lookup"><span data-stu-id="e111e-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="e111e-107">[in]函数的名称。</span><span class="sxs-lookup"><span data-stu-id="e111e-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="e111e-108">[out]接收指向函数的地址的位置。</span><span class="sxs-lookup"><span data-stu-id="e111e-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e111e-109">返回值</span><span class="sxs-lookup"><span data-stu-id="e111e-109">Return Value</span></span>  
 <span data-ttu-id="e111e-110">定义在 WinError.h，除了 CorError.h 中定义的以下值时，此方法将返回标准组件对象模型 (COM) 错误代码。</span><span class="sxs-lookup"><span data-stu-id="e111e-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="e111e-111">返回代码</span><span class="sxs-lookup"><span data-stu-id="e111e-111">Return code</span></span>|<span data-ttu-id="e111e-112">描述</span><span class="sxs-lookup"><span data-stu-id="e111e-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="e111e-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="e111e-113">S_OK</span></span>|<span data-ttu-id="e111e-114">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="e111e-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="e111e-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="e111e-115">E_POINTER</span></span>|<span data-ttu-id="e111e-116">`ppv` 无效。</span><span class="sxs-lookup"><span data-stu-id="e111e-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="e111e-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="e111e-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="e111e-118">不会在运行时中导出函数。</span><span class="sxs-lookup"><span data-stu-id="e111e-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e111e-119">要求</span><span class="sxs-lookup"><span data-stu-id="e111e-119">Requirements</span></span>  
 <span data-ttu-id="e111e-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e111e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e111e-121">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e111e-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e111e-122">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e111e-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e111e-123">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e111e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e111e-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e111e-124">See Also</span></span>  
 [<span data-ttu-id="e111e-125">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="e111e-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
