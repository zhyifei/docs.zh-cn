---
title: CorBindToRuntimeByCfg 函数
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeByCfg
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeByCfg
helpviewer_keywords:
- CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d59506b522e1c225912da4bc3bd62ca19d32eb8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556072"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="ed050-102">CorBindToRuntimeByCfg 函数</span><span class="sxs-lookup"><span data-stu-id="ed050-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="ed050-103">通过使用从 XML 文件中读取的版本信息将公共语言运行时 (CLR) 加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="ed050-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="ed050-104">此函数中不推荐[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ed050-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed050-105">语法</span><span class="sxs-lookup"><span data-stu-id="ed050-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="ed050-106">参数</span><span class="sxs-lookup"><span data-stu-id="ed050-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="ed050-107">[in]一个指向`IStream`对象，它读取 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="ed050-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="ed050-108">[in]保留供将来使用。</span><span class="sxs-lookup"><span data-stu-id="ed050-108">[in] Reserved for future use.</span></span> <span data-ttu-id="ed050-109">使用作为值 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="ed050-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="ed050-110">[in]值为[STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)枚举，用于指定 CLR 的启动行为。</span><span class="sxs-lookup"><span data-stu-id="ed050-110">[in] A value of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="ed050-111">[in]`CLSID`的实现的组件类[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="ed050-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="ed050-112">支持的值为 CLSID_CorRuntimeHost 或 CLSID_CLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="ed050-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="ed050-113">[in]`IID`的任一`ICorRuntimeHost`或`ICLRRuntimeHost`接口。</span><span class="sxs-lookup"><span data-stu-id="ed050-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="ed050-114">支持的值为 IID_ICorRuntimeHost 或 IID_ICLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="ed050-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="ed050-115">[out]指向返回的接口的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="ed050-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed050-116">备注</span><span class="sxs-lookup"><span data-stu-id="ed050-116">Remarks</span></span>  
 <span data-ttu-id="ed050-117">XML 文件的格式只被现代性的标准应用程序配置文件。</span><span class="sxs-lookup"><span data-stu-id="ed050-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="ed050-118">有关 XML 文件的详细信息，请参阅[配置文件架构](../../../../docs/framework/configure-apps/file-schema/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ed050-118">For more information about XML files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed050-119">要求</span><span class="sxs-lookup"><span data-stu-id="ed050-119">Requirements</span></span>  
 <span data-ttu-id="ed050-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ed050-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed050-121">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ed050-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed050-122">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ed050-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed050-123">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed050-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed050-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed050-124">See also</span></span>
- [<span data-ttu-id="ed050-125">CorBindToCurrentRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="ed050-125">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="ed050-126">CorBindToRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="ed050-126">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="ed050-127">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="ed050-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="ed050-128">CorBindToRuntimeHost 函数</span><span class="sxs-lookup"><span data-stu-id="ed050-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="ed050-129">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="ed050-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="ed050-130">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="ed050-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
