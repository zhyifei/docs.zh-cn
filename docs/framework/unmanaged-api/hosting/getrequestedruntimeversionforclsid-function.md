---
title: GetRequestedRuntimeVersionForCLSID 函数
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersionForCLSID
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersionForCLSID
helpviewer_keywords:
- GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4b4ac1a37c2b3506216499ed0c9f8194949b768
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985642"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="2be46-102">GetRequestedRuntimeVersionForCLSID 函数</span><span class="sxs-lookup"><span data-stu-id="2be46-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="2be46-103">获取相应的公共语言运行时 (CLR) 版本信息，为具有指定类`CLSID`。</span><span class="sxs-lookup"><span data-stu-id="2be46-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="2be46-104">此函数中不推荐[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2be46-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2be46-105">语法</span><span class="sxs-lookup"><span data-stu-id="2be46-105">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2be46-106">参数</span><span class="sxs-lookup"><span data-stu-id="2be46-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="2be46-107">[in] `CLSID`的组件。</span><span class="sxs-lookup"><span data-stu-id="2be46-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="2be46-108">[out] 包含成功完成后的版本字符串的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2be46-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="2be46-109">[in] 大小，以宽字符为单位的`pVersion`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2be46-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="2be46-110">[out]返回的缓冲区长度 （字节）。</span><span class="sxs-lookup"><span data-stu-id="2be46-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="2be46-111">[in] CLSID_RESOLUTION_FLAGS 值之一。</span><span class="sxs-lookup"><span data-stu-id="2be46-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="2be46-112">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="2be46-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="2be46-113">CLSID_RESOLUTION_DEFAULT:(0x0) 指定应使用默认互操作行为。</span><span class="sxs-lookup"><span data-stu-id="2be46-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
- <span data-ttu-id="2be46-114">CLSID_RESOLUTION_REGISTERED:(0x1) 指定应搜索注册表和应应用填充程序策略。</span><span class="sxs-lookup"><span data-stu-id="2be46-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2be46-115">返回值</span><span class="sxs-lookup"><span data-stu-id="2be46-115">Return Value</span></span>  
  
|<span data-ttu-id="2be46-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2be46-116">HRESULT</span></span>|<span data-ttu-id="2be46-117">描述</span><span class="sxs-lookup"><span data-stu-id="2be46-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2be46-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="2be46-118">S_OK</span></span>|<span data-ttu-id="2be46-119">该函数返回成功。</span><span class="sxs-lookup"><span data-stu-id="2be46-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="2be46-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2be46-120">E_INVALIDARG</span></span>|<span data-ttu-id="2be46-121">参数之一具有无效的类型或格式。</span><span class="sxs-lookup"><span data-stu-id="2be46-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="2be46-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="2be46-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="2be46-123">`pVersion`缓冲区不是大到足以保留完整版本字符串。</span><span class="sxs-lookup"><span data-stu-id="2be46-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="2be46-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="2be46-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="2be46-125">没有与指定注册类`CLSID`。</span><span class="sxs-lookup"><span data-stu-id="2be46-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="2be46-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="2be46-126">E_POINTER</span></span>|<span data-ttu-id="2be46-127">`dwLength` 为 null，或`cchBuffer`足够大以保存的版本字符串，但`pVersion`为 null。</span><span class="sxs-lookup"><span data-stu-id="2be46-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2be46-128">要求</span><span class="sxs-lookup"><span data-stu-id="2be46-128">Requirements</span></span>  
 <span data-ttu-id="2be46-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2be46-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2be46-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2be46-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2be46-131">**.NET Framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2be46-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2be46-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="2be46-132">See also</span></span>

- [<span data-ttu-id="2be46-133">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="2be46-133">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
