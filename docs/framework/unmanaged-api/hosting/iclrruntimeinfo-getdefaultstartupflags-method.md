---
title: ICLRRuntimeInfo::GetDefaultStartupFlags 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
ms.openlocfilehash: 8513787f48ae89632816face386bbcda20555dac
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703883"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a><span data-ttu-id="8a78a-102">ICLRRuntimeInfo::GetDefaultStartupFlags 方法</span><span class="sxs-lookup"><span data-stu-id="8a78a-102">ICLRRuntimeInfo::GetDefaultStartupFlags Method</span></span>
<span data-ttu-id="8a78a-103">获取启动标志和主机配置文件，该文件将用于启动运行时。</span><span class="sxs-lookup"><span data-stu-id="8a78a-103">Gets the startup flags and host configuration file that will be used to start the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a78a-104">语法</span><span class="sxs-lookup"><span data-stu-id="8a78a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a78a-105">参数</span><span class="sxs-lookup"><span data-stu-id="8a78a-105">Parameters</span></span>  
 `pdwStartupFlags`  
 <span data-ttu-id="8a78a-106">弄指向当前设置的主机启动标志的指针。</span><span class="sxs-lookup"><span data-stu-id="8a78a-106">[out] A pointer to the host startup flags that are currently set.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="8a78a-107">弄一个指针，指向当前宿主配置文件的目录路径。</span><span class="sxs-lookup"><span data-stu-id="8a78a-107">[out] A pointer to the directory path of the current host configuration file.</span></span>  
  
 `pcchHostConfigFile`  
 <span data-ttu-id="8a78a-108">[in，out]输入时， `pwzHostConfigFile` 为避免缓冲区溢出。</span><span class="sxs-lookup"><span data-stu-id="8a78a-108">[in, out] On input, the size of `pwzHostConfigFile`, to avoid buffer overruns.</span></span> <span data-ttu-id="8a78a-109">如果 `pwzHostConfigFile` 为 null，则该方法为预分配返回所需的大小 `pwzHostConfigFile` 。</span><span class="sxs-lookup"><span data-stu-id="8a78a-109">If `pwzHostConfigFile` is null, the method returns the required size of `pwzHostConfigFile` for pre-allocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a78a-110">返回值</span><span class="sxs-lookup"><span data-stu-id="8a78a-110">Return Value</span></span>  
 <span data-ttu-id="8a78a-111">此方法返回以下特定的 HRESULT 以及指示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="8a78a-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8a78a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a78a-112">HRESULT</span></span>|<span data-ttu-id="8a78a-113">说明</span><span class="sxs-lookup"><span data-stu-id="8a78a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8a78a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="8a78a-114">S_OK</span></span>|<span data-ttu-id="8a78a-115">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="8a78a-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a78a-116">备注</span><span class="sxs-lookup"><span data-stu-id="8a78a-116">Remarks</span></span>  
 <span data-ttu-id="8a78a-117">此方法返回默认标志值（ `STARTUP_CONCURRENT_GC` 和 `NULL` ），或由以前对[ICLRRuntimeInfo：： SetDefaultStartupFlags 方法](iclrruntimeinfo-setdefaultstartupflags-method.md)的调用提供的值; 或者， `CorBind*` 如果绑定到此运行时，则为任何方法设置的值。</span><span class="sxs-lookup"><span data-stu-id="8a78a-117">This method returns the default flag values (`STARTUP_CONCURRENT_GC` and `NULL`), or the values provided by a previous call to the [ICLRRuntimeInfo::SetDefaultStartupFlags method](iclrruntimeinfo-setdefaultstartupflags-method.md), or the values set by any of the `CorBind*` methods if they are bound to this runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a78a-118">要求</span><span class="sxs-lookup"><span data-stu-id="8a78a-118">Requirements</span></span>  
 <span data-ttu-id="8a78a-119">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8a78a-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a78a-120">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="8a78a-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8a78a-121">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8a78a-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a78a-122">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a78a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a78a-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a78a-123">See also</span></span>

- [<span data-ttu-id="8a78a-124">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="8a78a-124">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="8a78a-125">承载接口</span><span class="sxs-lookup"><span data-stu-id="8a78a-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="8a78a-126">承载</span><span class="sxs-lookup"><span data-stu-id="8a78a-126">Hosting</span></span>](index.md)
