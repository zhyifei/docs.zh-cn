---
title: ICLRRuntimeInfo::GetRuntimeDirectory 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetRuntimeDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c09f57ad805b4ba17b4bdafd3ced533199277a0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196679"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="7883b-102">ICLRRuntimeInfo::GetRuntimeDirectory 方法</span><span class="sxs-lookup"><span data-stu-id="7883b-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="7883b-103">获取与此接口关联的公共语言运行时 (CLR) 的安装目录。</span><span class="sxs-lookup"><span data-stu-id="7883b-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="7883b-104">此方法取代[GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)在.NET Framework 版本 2.0、 3.0 和 3.5 中提供的函数。</span><span class="sxs-lookup"><span data-stu-id="7883b-104">This method supersedes the [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7883b-105">语法</span><span class="sxs-lookup"><span data-stu-id="7883b-105">Syntax</span></span>  
  
```  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7883b-106">参数</span><span class="sxs-lookup"><span data-stu-id="7883b-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="7883b-107">[out]返回 CLR 安装目录。</span><span class="sxs-lookup"><span data-stu-id="7883b-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="7883b-108">安装路径是完全限定的;例如，"c:\windows\microsoft.net\framework\v1.0.3705\\"。</span><span class="sxs-lookup"><span data-stu-id="7883b-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="7883b-109">[in、 out]指定的大小`pwzBuffer`以避免缓冲区溢出。</span><span class="sxs-lookup"><span data-stu-id="7883b-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="7883b-110">如果`pwzBuffer`为 null，`pchBuffer`返回的所需的大小`pwzBuffer`。</span><span class="sxs-lookup"><span data-stu-id="7883b-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7883b-111">返回值</span><span class="sxs-lookup"><span data-stu-id="7883b-111">Return Value</span></span>  
 <span data-ttu-id="7883b-112">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="7883b-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7883b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7883b-113">HRESULT</span></span>|<span data-ttu-id="7883b-114">描述</span><span class="sxs-lookup"><span data-stu-id="7883b-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7883b-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="7883b-115">S_OK</span></span>|<span data-ttu-id="7883b-116">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="7883b-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="7883b-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="7883b-117">E_POINTER</span></span>|`pwzBuffer` <span data-ttu-id="7883b-118">或`pchBuffer`为 null。</span><span class="sxs-lookup"><span data-stu-id="7883b-118">or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7883b-119">备注</span><span class="sxs-lookup"><span data-stu-id="7883b-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7883b-120">要求</span><span class="sxs-lookup"><span data-stu-id="7883b-120">Requirements</span></span>  
 <span data-ttu-id="7883b-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7883b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7883b-122">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7883b-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7883b-123">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7883b-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="7883b-124">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="7883b-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7883b-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="7883b-125">See also</span></span>

- [<span data-ttu-id="7883b-126">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="7883b-126">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="7883b-127">宿主</span><span class="sxs-lookup"><span data-stu-id="7883b-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
