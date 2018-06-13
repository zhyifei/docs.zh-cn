---
title: CorBindToCurrentRuntime 函数
ms.date: 03/30/2017
api_name:
- CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- HeaderDef
f1_keywords:
- CorBindToCurrentRuntime
helpviewer_keywords:
- CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3667ac5a19664507b767ee6c5421a5e93f6cdfe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433251"
---
# <a name="corbindtocurrentruntime-function"></a><span data-ttu-id="bb901-102">CorBindToCurrentRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="bb901-102">CorBindToCurrentRuntime Function</span></span>
<span data-ttu-id="bb901-103">通过使用版本信息存储在 XML 文件中，到的进程中加载公共语言运行时 (CLR)。</span><span class="sxs-lookup"><span data-stu-id="bb901-103">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span> <span data-ttu-id="bb901-104">XML 文件的格式是标准的应用程序配置文件之后制定的。</span><span class="sxs-lookup"><span data-stu-id="bb901-104">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="bb901-105">有关配置文件的详细信息，请参阅[配置文件架构](../../../../docs/framework/configure-apps/file-schema/index.md)。</span><span class="sxs-lookup"><span data-stu-id="bb901-105">For more information about configuration files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="bb901-106">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bb901-106">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="bb901-107">请参阅[公共语言运行时加载到进程中](http://msdn.microsoft.com/library/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f)。</span><span class="sxs-lookup"><span data-stu-id="bb901-107">See [Loading the Common Language Runtime into a Process](http://msdn.microsoft.com/library/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb901-108">语法</span><span class="sxs-lookup"><span data-stu-id="bb901-108">Syntax</span></span>  
  
```  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb901-109">参数</span><span class="sxs-lookup"><span data-stu-id="bb901-109">Parameters</span></span>  
 `pwszFileName`  
 <span data-ttu-id="bb901-110">[in]指定要加载的 clr 版本的应用程序配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="bb901-110">[in] The name of an application configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="bb901-111">如果不完全限定的文件名，则假定在进行调用的可执行文件所在的目录。</span><span class="sxs-lookup"><span data-stu-id="bb901-111">If the file name is not fully qualified, it is assumed to be in the same directory as the executable making the call.</span></span>  
  
 <span data-ttu-id="bb901-112">中的版本属性描述要加载的运行时版本[ \<requiredRuntime >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)配置文件元素。</span><span class="sxs-lookup"><span data-stu-id="bb901-112">The version of the runtime to be loaded is described by the version attribute in the [\<requiredRuntime>](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) element of the configuration file.</span></span>  
  
 <span data-ttu-id="bb901-113">如果没有指定版本，或如果`<requiredRuntime>`找不到元素，加载计算机安装的 CLR 的最新版本。</span><span class="sxs-lookup"><span data-stu-id="bb901-113">If no version is specified, or if the `<requiredRuntime>` element cannot be found, the latest version of the CLR that is installed on the machine is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="bb901-114">[in]`CLSID`实现的组件类的[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="bb901-114">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="bb901-115">支持的值为 CLSID_CorRuntimeHost 或 CLSID_CLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="bb901-115">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="bb901-116">[in]`IID`您请求的接口。</span><span class="sxs-lookup"><span data-stu-id="bb901-116">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="bb901-117">支持的值为 IID_ICorRuntimeHost 或 IID_ICLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="bb901-117">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="bb901-118">[out]返回的接口指针。</span><span class="sxs-lookup"><span data-stu-id="bb901-118">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb901-119">要求</span><span class="sxs-lookup"><span data-stu-id="bb901-119">Requirements</span></span>  
 <span data-ttu-id="bb901-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bb901-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb901-121">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bb901-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bb901-122">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bb901-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb901-123">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb901-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb901-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb901-124">See Also</span></span>  
 [<span data-ttu-id="bb901-125">CorBindToRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="bb901-125">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [<span data-ttu-id="bb901-126">CorBindToRuntimeByCfg 函数</span><span class="sxs-lookup"><span data-stu-id="bb901-126">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [<span data-ttu-id="bb901-127">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="bb901-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="bb901-128">CorBindToRuntimeHost 函数</span><span class="sxs-lookup"><span data-stu-id="bb901-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [<span data-ttu-id="bb901-129">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="bb901-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="bb901-130">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="bb901-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
