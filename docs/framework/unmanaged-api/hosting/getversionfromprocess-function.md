---
title: GetVersionFromProcess 函数
ms.date: 03/30/2017
api_name:
- GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetVersionFromProcess
helpviewer_keywords:
- GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b57d04a8a49371872c679a331b5ae9c45dce797
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433068"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="71380-102">GetVersionFromProcess 函数</span><span class="sxs-lookup"><span data-stu-id="71380-102">GetVersionFromProcess Function</span></span>
<span data-ttu-id="71380-103">获取与指定的进程句柄关联公共语言运行时 (CLR) 的版本号。</span><span class="sxs-lookup"><span data-stu-id="71380-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="71380-104">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="71380-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71380-105">语法</span><span class="sxs-lookup"><span data-stu-id="71380-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71380-106">参数</span><span class="sxs-lookup"><span data-stu-id="71380-106">Parameters</span></span>  
 `hProcess`  
 <span data-ttu-id="71380-107">[in]进程的句柄。</span><span class="sxs-lookup"><span data-stu-id="71380-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="71380-108">[out]包含的方法的成功完成后的版本号字符串的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="71380-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="71380-109">[in]版本缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="71380-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="71380-110">[out]指向的版本号字符串的长度的指针。</span><span class="sxs-lookup"><span data-stu-id="71380-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71380-111">返回值</span><span class="sxs-lookup"><span data-stu-id="71380-111">Return Value</span></span>  
 <span data-ttu-id="71380-112">此方法返回标准的组件对象模型 (COM) 错误代码，除了以下值中 WinError.h，定义。</span><span class="sxs-lookup"><span data-stu-id="71380-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="71380-113">返回代码</span><span class="sxs-lookup"><span data-stu-id="71380-113">Return code</span></span>|<span data-ttu-id="71380-114">描述</span><span class="sxs-lookup"><span data-stu-id="71380-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="71380-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="71380-115">S_OK</span></span>|<span data-ttu-id="71380-116">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="71380-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="71380-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="71380-117">E_INVALIDARG</span></span>|<span data-ttu-id="71380-118">`pVersion` 为 null 和`cchBuffer`不为 null，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="71380-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="71380-119">-或-</span><span class="sxs-lookup"><span data-stu-id="71380-119">-or-</span></span><br /><br /> <span data-ttu-id="71380-120">`hProcess` 不是有效的句柄到进程。</span><span class="sxs-lookup"><span data-stu-id="71380-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="71380-121">-或-</span><span class="sxs-lookup"><span data-stu-id="71380-121">-or-</span></span><br /><br /> <span data-ttu-id="71380-122">CLR 不会加载。</span><span class="sxs-lookup"><span data-stu-id="71380-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="71380-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="71380-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="71380-124">`cchBuffer` 为 null 或小于版本字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="71380-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="71380-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="71380-125">E_NOTIMPL</span></span>|<span data-ttu-id="71380-126">此方法不是在 Microsoft Windows 95、 Microsoft Windows 98、 或 Microsoft Windows Millennium Edition 操作系统上可用的。</span><span class="sxs-lookup"><span data-stu-id="71380-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71380-127">要求</span><span class="sxs-lookup"><span data-stu-id="71380-127">Requirements</span></span>  
 <span data-ttu-id="71380-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="71380-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71380-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="71380-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71380-130">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="71380-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71380-131">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71380-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71380-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="71380-132">See Also</span></span>  
 [<span data-ttu-id="71380-133">GetRequestedRuntimeInfo 函数</span><span class="sxs-lookup"><span data-stu-id="71380-133">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 [<span data-ttu-id="71380-134">GetRequestedRuntimeVersion 函数</span><span class="sxs-lookup"><span data-stu-id="71380-134">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 [<span data-ttu-id="71380-135">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="71380-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
