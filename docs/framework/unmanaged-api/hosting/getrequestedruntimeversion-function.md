---
title: GetRequestedRuntimeVersion 函数
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersion
helpviewer_keywords:
- GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type:
- apiref
ms.openlocfilehash: 6be0bc5d08f612dcb8ed7d256711e0c4367b9274
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178142"
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="2a9a3-102">GetRequestedRuntimeVersion 函数</span><span class="sxs-lookup"><span data-stu-id="2a9a3-102">GetRequestedRuntimeVersion Function</span></span>
<span data-ttu-id="2a9a3-103">获取指定应用程序请求的通用语言运行时 （CLR） 的版本号。</span><span class="sxs-lookup"><span data-stu-id="2a9a3-103">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="2a9a3-104">如果未安装该版本，请获取在请求的版本之前安装的最新版本。</span><span class="sxs-lookup"><span data-stu-id="2a9a3-104">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="2a9a3-105">此功能已在 .NET 框架 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="2a9a3-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a9a3-106">语法</span><span class="sxs-lookup"><span data-stu-id="2a9a3-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a9a3-107">parameters</span><span class="sxs-lookup"><span data-stu-id="2a9a3-107">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="2a9a3-108">[在]应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="2a9a3-108">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="2a9a3-109">[出]成功完成后包含版本号字符串的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2a9a3-109">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="2a9a3-110">[在]版本缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="2a9a3-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="2a9a3-111">[出]指向版本号字符串长度的指针。</span><span class="sxs-lookup"><span data-stu-id="2a9a3-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a9a3-112">返回值</span><span class="sxs-lookup"><span data-stu-id="2a9a3-112">Return Value</span></span>  
 <span data-ttu-id="2a9a3-113">此方法返回 WinError.h 中定义的标准组件对象模型 （COM） 错误代码，以及以下值。</span><span class="sxs-lookup"><span data-stu-id="2a9a3-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="2a9a3-114">返回代码</span><span class="sxs-lookup"><span data-stu-id="2a9a3-114">Return code</span></span>|<span data-ttu-id="2a9a3-115">说明</span><span class="sxs-lookup"><span data-stu-id="2a9a3-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="2a9a3-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="2a9a3-116">S_OK</span></span>|<span data-ttu-id="2a9a3-117">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="2a9a3-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="2a9a3-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="2a9a3-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="2a9a3-119">版本缓冲区不够大，无法存储版本字符串。</span><span class="sxs-lookup"><span data-stu-id="2a9a3-119">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="2a9a3-120">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="2a9a3-120">E_POINTER</span></span>|<span data-ttu-id="2a9a3-121">`pdwLength` 为 null。</span><span class="sxs-lookup"><span data-stu-id="2a9a3-121">`pdwLength` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2a9a3-122">要求</span><span class="sxs-lookup"><span data-stu-id="2a9a3-122">Requirements</span></span>  
 <span data-ttu-id="2a9a3-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2a9a3-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a9a3-124">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2a9a3-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a9a3-125">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2a9a3-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a9a3-126">**.NET 框架版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a9a3-126">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a9a3-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a9a3-127">See also</span></span>

- [<span data-ttu-id="2a9a3-128">GetRequestedRuntimeInfo 函数</span><span class="sxs-lookup"><span data-stu-id="2a9a3-128">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="2a9a3-129">GetVersionFromProcess 函数</span><span class="sxs-lookup"><span data-stu-id="2a9a3-129">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="2a9a3-130">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="2a9a3-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
