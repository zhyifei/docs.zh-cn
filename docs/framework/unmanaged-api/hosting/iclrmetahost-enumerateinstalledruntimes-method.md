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
ms.openlocfilehash: 9415d5189edb901822abad9269e0150e7601a963
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140964"
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a><span data-ttu-id="708e4-102">ICLRMetaHost::EnumerateInstalledRuntimes 方法</span><span class="sxs-lookup"><span data-stu-id="708e4-102">ICLRMetaHost::EnumerateInstalledRuntimes Method</span></span>
<span data-ttu-id="708e4-103">返回一个枚举，该枚举包含计算机上安装的每个版本的公共语言运行时（CLR）的有效[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="708e4-103">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface for each version of the common language runtime (CLR) that is installed on a computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="708e4-104">语法</span><span class="sxs-lookup"><span data-stu-id="708e4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
## <a name="parameters"></a><span data-ttu-id="708e4-105">参数</span><span class="sxs-lookup"><span data-stu-id="708e4-105">Parameters</span></span>  
 `ppEnumerator`  
 <span data-ttu-id="708e4-106">弄与计算机上安装的每个 CLR 版本相对应的[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口的枚举。</span><span class="sxs-lookup"><span data-stu-id="708e4-106">[out] An enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each version of the CLR that is installed on the computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="708e4-107">返回值</span><span class="sxs-lookup"><span data-stu-id="708e4-107">Return Value</span></span>  
 <span data-ttu-id="708e4-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="708e4-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="708e4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="708e4-109">HRESULT</span></span>|<span data-ttu-id="708e4-110">描述</span><span class="sxs-lookup"><span data-stu-id="708e4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="708e4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="708e4-111">S_OK</span></span>|<span data-ttu-id="708e4-112">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="708e4-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="708e4-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="708e4-113">E_POINTER</span></span>|<span data-ttu-id="708e4-114">`ppEnumerator` 为 null。</span><span class="sxs-lookup"><span data-stu-id="708e4-114">`ppEnumerator` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="708e4-115">要求</span><span class="sxs-lookup"><span data-stu-id="708e4-115">Requirements</span></span>  
 <span data-ttu-id="708e4-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="708e4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="708e4-117">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="708e4-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="708e4-118">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="708e4-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="708e4-119">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="708e4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="708e4-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="708e4-120">See also</span></span>

- [<span data-ttu-id="708e4-121">ICLRMetaHost 接口</span><span class="sxs-lookup"><span data-stu-id="708e4-121">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="708e4-122">承载</span><span class="sxs-lookup"><span data-stu-id="708e4-122">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
