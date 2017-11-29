---
title: "CorBindToRuntimeByCfg 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorBindToRuntimeByCfg
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CorBindToRuntimeByCfg
helpviewer_keywords: CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bbf5a486246d1fb596c08f1510e6d5d89b03df62
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="2be4d-102">CorBindToRuntimeByCfg 函数</span><span class="sxs-lookup"><span data-stu-id="2be4d-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="2be4d-103">通过使用版本信息从 XML 文件读取到的进程中加载公共语言运行时 (CLR)。</span><span class="sxs-lookup"><span data-stu-id="2be4d-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="2be4d-104">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2be4d-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2be4d-105">语法</span><span class="sxs-lookup"><span data-stu-id="2be4d-105">Syntax</span></span>  
  
```  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,   
    [out] LPVOID FAR*  ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2be4d-106">参数</span><span class="sxs-lookup"><span data-stu-id="2be4d-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="2be4d-107">[in]指向的指针`IStream`读取 XML 文件的对象。</span><span class="sxs-lookup"><span data-stu-id="2be4d-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="2be4d-108">[in]留待将来使用。</span><span class="sxs-lookup"><span data-stu-id="2be4d-108">[in] Reserved for future use.</span></span> <span data-ttu-id="2be4d-109">使用作为值 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="2be4d-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="2be4d-110">[in]值为[STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)指定 CLR 的启动行为的枚举。</span><span class="sxs-lookup"><span data-stu-id="2be4d-110">[in] A value of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="2be4d-111">[in]`CLSID`实现的组件类的[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="2be4d-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="2be4d-112">支持的值为 CLSID_CorRuntimeHost 或 CLSID_CLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="2be4d-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="2be4d-113">[in]`IID`任一`ICorRuntimeHost`或`ICLRRuntimeHost`接口。</span><span class="sxs-lookup"><span data-stu-id="2be4d-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="2be4d-114">支持的值为 IID_ICorRuntimeHost 或 IID_ICLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="2be4d-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="2be4d-115">[out]指向的地址返回的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="2be4d-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2be4d-116">备注</span><span class="sxs-lookup"><span data-stu-id="2be4d-116">Remarks</span></span>  
 <span data-ttu-id="2be4d-117">XML 文件的格式是标准的应用程序配置文件之后制定的。</span><span class="sxs-lookup"><span data-stu-id="2be4d-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="2be4d-118">有关 XML 文件的详细信息，请参阅[配置文件架构](../../../../docs/framework/configure-apps/file-schema/index.md)。</span><span class="sxs-lookup"><span data-stu-id="2be4d-118">For more information about XML files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2be4d-119">要求</span><span class="sxs-lookup"><span data-stu-id="2be4d-119">Requirements</span></span>  
 <span data-ttu-id="2be4d-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2be4d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2be4d-121">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2be4d-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2be4d-122">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2be4d-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2be4d-123">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2be4d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2be4d-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2be4d-124">See Also</span></span>  
 [<span data-ttu-id="2be4d-125">CorBindToCurrentRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="2be4d-125">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [<span data-ttu-id="2be4d-126">CorBindToRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="2be4d-126">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [<span data-ttu-id="2be4d-127">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="2be4d-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="2be4d-128">CorBindToRuntimeHost 函数</span><span class="sxs-lookup"><span data-stu-id="2be4d-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [<span data-ttu-id="2be4d-129">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="2be4d-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="2be4d-130">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="2be4d-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
