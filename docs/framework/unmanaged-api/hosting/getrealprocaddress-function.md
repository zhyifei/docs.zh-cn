---
title: GetRealProcAddress 函数
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b31db6e6a8ecb3fa15f1a8690b007bdb536b97c0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506545"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="1e670-102">GetRealProcAddress 函数</span><span class="sxs-lookup"><span data-stu-id="1e670-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="1e670-103">获取指定从最新的安装公共语言运行时 (CLR) 版本导出的函数的地址。</span><span class="sxs-lookup"><span data-stu-id="1e670-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="1e670-104">此函数中不推荐[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1e670-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e670-105">语法</span><span class="sxs-lookup"><span data-stu-id="1e670-105">Syntax</span></span>  
  
```  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1e670-106">参数</span><span class="sxs-lookup"><span data-stu-id="1e670-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="1e670-107">[in]函数的名称。</span><span class="sxs-lookup"><span data-stu-id="1e670-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="1e670-108">[out]接收指向函数的地址的位置。</span><span class="sxs-lookup"><span data-stu-id="1e670-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e670-109">返回值</span><span class="sxs-lookup"><span data-stu-id="1e670-109">Return Value</span></span>  
 <span data-ttu-id="1e670-110">此方法返回标准的组件对象模型 (COM) 错误代码，定义在 WinError.h，除了 CorError.h 中定义的以下值。</span><span class="sxs-lookup"><span data-stu-id="1e670-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="1e670-111">返回代码</span><span class="sxs-lookup"><span data-stu-id="1e670-111">Return code</span></span>|<span data-ttu-id="1e670-112">描述</span><span class="sxs-lookup"><span data-stu-id="1e670-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="1e670-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1e670-113">S_OK</span></span>|<span data-ttu-id="1e670-114">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="1e670-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="1e670-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="1e670-115">E_POINTER</span></span>|<span data-ttu-id="1e670-116">`ppv` 无效。</span><span class="sxs-lookup"><span data-stu-id="1e670-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="1e670-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="1e670-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="1e670-118">不会在运行时中导出函数。</span><span class="sxs-lookup"><span data-stu-id="1e670-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e670-119">要求</span><span class="sxs-lookup"><span data-stu-id="1e670-119">Requirements</span></span>  
 <span data-ttu-id="1e670-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1e670-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e670-121">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1e670-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1e670-122">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1e670-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e670-123">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e670-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e670-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e670-124">See also</span></span>
- [<span data-ttu-id="1e670-125">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="1e670-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
