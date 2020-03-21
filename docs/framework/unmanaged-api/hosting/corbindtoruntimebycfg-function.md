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
ms.openlocfilehash: 4fbc6e7ea531f65a6b1cd0ec93f4847ab8e4fe83
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178244"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="a7ec6-102">CorBindToRuntimeByCfg 函数</span><span class="sxs-lookup"><span data-stu-id="a7ec6-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="a7ec6-103">通过使用从 XML 文件读取的版本信息将通用语言运行时 （CLR） 加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="a7ec6-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="a7ec6-104">此功能已在 .NET 框架 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="a7ec6-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7ec6-105">语法</span><span class="sxs-lookup"><span data-stu-id="a7ec6-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,
    [out] LPVOID FAR*  ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7ec6-106">parameters</span><span class="sxs-lookup"><span data-stu-id="a7ec6-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="a7ec6-107">[在]指向读取 XML`IStream`文件的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="a7ec6-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="a7ec6-108">[在]保留以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="a7ec6-108">[in] Reserved for future use.</span></span> <span data-ttu-id="a7ec6-109">使用 0（零）作为值。</span><span class="sxs-lookup"><span data-stu-id="a7ec6-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="a7ec6-110">[在]指定 CLR 的启动行为的[STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)枚举的值。</span><span class="sxs-lookup"><span data-stu-id="a7ec6-110">[in] A value of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="a7ec6-111">[在]`CLSID`实现[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口的共类。</span><span class="sxs-lookup"><span data-stu-id="a7ec6-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="a7ec6-112">支持的值CLSID_CorRuntimeHost或CLSID_CLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="a7ec6-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="a7ec6-113">[在]或`IID``ICorRuntimeHost`接口 的`ICLRRuntimeHost`。</span><span class="sxs-lookup"><span data-stu-id="a7ec6-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="a7ec6-114">支持的值IID_ICorRuntimeHost或IID_ICLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="a7ec6-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="a7ec6-115">[出]指向返回接口地址的指针。</span><span class="sxs-lookup"><span data-stu-id="a7ec6-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7ec6-116">备注</span><span class="sxs-lookup"><span data-stu-id="a7ec6-116">Remarks</span></span>  
 <span data-ttu-id="a7ec6-117">XML 文件的格式以标准应用程序配置文件建模。</span><span class="sxs-lookup"><span data-stu-id="a7ec6-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="a7ec6-118">有关 XML 文件的详细信息，请参阅[配置文件架构](../../../../docs/framework/configure-apps/file-schema/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a7ec6-118">For more information about XML files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7ec6-119">要求</span><span class="sxs-lookup"><span data-stu-id="a7ec6-119">Requirements</span></span>  
 <span data-ttu-id="a7ec6-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a7ec6-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7ec6-121">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a7ec6-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7ec6-122">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7ec6-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7ec6-123">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7ec6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7ec6-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7ec6-124">See also</span></span>

- [<span data-ttu-id="a7ec6-125">CorBindToCurrentRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="a7ec6-125">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="a7ec6-126">CorBindToRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="a7ec6-126">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="a7ec6-127">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="a7ec6-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="a7ec6-128">CorBindToRuntimeHost 函数</span><span class="sxs-lookup"><span data-stu-id="a7ec6-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="a7ec6-129">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="a7ec6-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="a7ec6-130">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="a7ec6-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
