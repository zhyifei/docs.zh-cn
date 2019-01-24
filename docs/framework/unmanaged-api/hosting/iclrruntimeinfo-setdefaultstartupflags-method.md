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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d021eb2d8da8c85fe538f0c73527876482429718
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656877"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="207b4-102">ICLRRuntimeInfo::SetDefaultStartupFlags 方法</span><span class="sxs-lookup"><span data-stu-id="207b4-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="207b4-103">设置启动标志和将用于启动运行时主机配置文件。</span><span class="sxs-lookup"><span data-stu-id="207b4-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="207b4-104">此方法会使用取代`startupFlags`中的参数[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)并[CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="207b4-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="207b4-105">语法</span><span class="sxs-lookup"><span data-stu-id="207b4-105">Syntax</span></span>  
  
```  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="207b4-106">参数</span><span class="sxs-lookup"><span data-stu-id="207b4-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="207b4-107">[in]要设置的主机启动标志。</span><span class="sxs-lookup"><span data-stu-id="207b4-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="207b4-108">使用具有相同标记作为[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)并[CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="207b4-108">Use the same flags as with the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="207b4-109">[in]要设置的主机配置文件的目录路径。</span><span class="sxs-lookup"><span data-stu-id="207b4-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="207b4-110">返回值</span><span class="sxs-lookup"><span data-stu-id="207b4-110">Return Value</span></span>  
 <span data-ttu-id="207b4-111">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="207b4-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="207b4-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="207b4-112">HRESULT</span></span>|<span data-ttu-id="207b4-113">描述</span><span class="sxs-lookup"><span data-stu-id="207b4-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="207b4-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="207b4-114">S_OK</span></span>|<span data-ttu-id="207b4-115">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="207b4-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="207b4-116">备注</span><span class="sxs-lookup"><span data-stu-id="207b4-116">Remarks</span></span>  
 <span data-ttu-id="207b4-117">多线程的主机应该同步对此方法的调用。</span><span class="sxs-lookup"><span data-stu-id="207b4-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="207b4-118">否则，调用线程 A 可能`SetStartupFlags`方法后完成的线程 B 调用`SetStartupFlags`和线程 B 开始运行时之前。</span><span class="sxs-lookup"><span data-stu-id="207b4-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="207b4-119">要求</span><span class="sxs-lookup"><span data-stu-id="207b4-119">Requirements</span></span>  
 <span data-ttu-id="207b4-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="207b4-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="207b4-121">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="207b4-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="207b4-122">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="207b4-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="207b4-123">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="207b4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="207b4-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="207b4-124">See also</span></span>
- [<span data-ttu-id="207b4-125">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="207b4-125">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="207b4-126">承载接口</span><span class="sxs-lookup"><span data-stu-id="207b4-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="207b4-127">承载</span><span class="sxs-lookup"><span data-stu-id="207b4-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
