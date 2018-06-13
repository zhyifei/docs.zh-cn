---
title: ICLRMetaHost::EnumerateInstalledRuntimes 方法
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateInstalledRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes
helpviewer_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes method [.NET Framework hosting]
- EnumerateInstalledRuntimes method [.NET Framework hosting]
ms.assetid: 9e359384-0d3d-451c-807e-5d7fcebf2be7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ed4c09d910db6fa2e61d44e4ac777f9b6095a20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434276"
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a><span data-ttu-id="ca65f-102">ICLRMetaHost::EnumerateInstalledRuntimes 方法</span><span class="sxs-lookup"><span data-stu-id="ca65f-102">ICLRMetaHost::EnumerateInstalledRuntimes Method</span></span>
<span data-ttu-id="ca65f-103">返回一个包含有效的枚举[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)每个版本的计算机安装公共语言运行时 (CLR) 的接口。</span><span class="sxs-lookup"><span data-stu-id="ca65f-103">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface for each version of the common language runtime (CLR) that is installed on a computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca65f-104">语法</span><span class="sxs-lookup"><span data-stu-id="ca65f-104">Syntax</span></span>  
  
```  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca65f-105">参数</span><span class="sxs-lookup"><span data-stu-id="ca65f-105">Parameters</span></span>  
 `ppEnumerator`  
 <span data-ttu-id="ca65f-106">[out]枚举[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)对应于每个版本的计算机安装的 CLR 的接口。</span><span class="sxs-lookup"><span data-stu-id="ca65f-106">[out] An enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each version of the CLR that is installed on the computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca65f-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ca65f-107">Return Value</span></span>  
 <span data-ttu-id="ca65f-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="ca65f-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ca65f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ca65f-109">HRESULT</span></span>|<span data-ttu-id="ca65f-110">描述</span><span class="sxs-lookup"><span data-stu-id="ca65f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ca65f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ca65f-111">S_OK</span></span>|<span data-ttu-id="ca65f-112">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="ca65f-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="ca65f-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ca65f-113">E_POINTER</span></span>|<span data-ttu-id="ca65f-114">`ppEnumerator` 为 null。</span><span class="sxs-lookup"><span data-stu-id="ca65f-114">`ppEnumerator` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ca65f-115">要求</span><span class="sxs-lookup"><span data-stu-id="ca65f-115">Requirements</span></span>  
 <span data-ttu-id="ca65f-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ca65f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca65f-117">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ca65f-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ca65f-118">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ca65f-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca65f-119">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca65f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca65f-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca65f-120">See Also</span></span>  
 [<span data-ttu-id="ca65f-121">ICLRMetaHost 接口</span><span class="sxs-lookup"><span data-stu-id="ca65f-121">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="ca65f-122">承载</span><span class="sxs-lookup"><span data-stu-id="ca65f-122">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
