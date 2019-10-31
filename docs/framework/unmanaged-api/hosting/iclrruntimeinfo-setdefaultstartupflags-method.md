---
title: ICLRRuntimeInfo::SetDefaultStartupFlags 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.SetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type:
- apiref
ms.openlocfilehash: 36851ac4573d0d65caffaa3f82a1f6fc8440a2d0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092744"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="ca0b7-102">ICLRRuntimeInfo::SetDefaultStartupFlags 方法</span><span class="sxs-lookup"><span data-stu-id="ca0b7-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="ca0b7-103">设置启动标志和将用于启动运行时的主机配置文件。</span><span class="sxs-lookup"><span data-stu-id="ca0b7-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="ca0b7-104">此方法取代了[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)和[CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)函数中的 `startupFlags` 参数的用法。</span><span class="sxs-lookup"><span data-stu-id="ca0b7-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca0b7-105">语法</span><span class="sxs-lookup"><span data-stu-id="ca0b7-105">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca0b7-106">参数</span><span class="sxs-lookup"><span data-stu-id="ca0b7-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="ca0b7-107">中要设置的主机启动标志。</span><span class="sxs-lookup"><span data-stu-id="ca0b7-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="ca0b7-108">使用与[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)和[CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)函数相同的标志。</span><span class="sxs-lookup"><span data-stu-id="ca0b7-108">Use the same flags as with the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="ca0b7-109">中要设置的主机配置文件的目录路径。</span><span class="sxs-lookup"><span data-stu-id="ca0b7-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca0b7-110">返回值</span><span class="sxs-lookup"><span data-stu-id="ca0b7-110">Return Value</span></span>  
 <span data-ttu-id="ca0b7-111">此方法返回以下特定的 HRESULT 以及指示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="ca0b7-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ca0b7-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ca0b7-112">HRESULT</span></span>|<span data-ttu-id="ca0b7-113">描述</span><span class="sxs-lookup"><span data-stu-id="ca0b7-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ca0b7-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ca0b7-114">S_OK</span></span>|<span data-ttu-id="ca0b7-115">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="ca0b7-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca0b7-116">备注</span><span class="sxs-lookup"><span data-stu-id="ca0b7-116">Remarks</span></span>  
 <span data-ttu-id="ca0b7-117">多线程主机应同步对此方法的调用。</span><span class="sxs-lookup"><span data-stu-id="ca0b7-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="ca0b7-118">否则，线程 A 可能会在线程 B 完成对 `SetStartupFlags` 的调用并在线程 B 启动运行时之前调用 `SetStartupFlags` 方法。</span><span class="sxs-lookup"><span data-stu-id="ca0b7-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca0b7-119">要求</span><span class="sxs-lookup"><span data-stu-id="ca0b7-119">Requirements</span></span>  
 <span data-ttu-id="ca0b7-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ca0b7-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca0b7-121">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="ca0b7-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ca0b7-122">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="ca0b7-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca0b7-123">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca0b7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca0b7-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca0b7-124">See also</span></span>

- [<span data-ttu-id="ca0b7-125">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="ca0b7-125">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="ca0b7-126">承载接口</span><span class="sxs-lookup"><span data-stu-id="ca0b7-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="ca0b7-127">承载</span><span class="sxs-lookup"><span data-stu-id="ca0b7-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
