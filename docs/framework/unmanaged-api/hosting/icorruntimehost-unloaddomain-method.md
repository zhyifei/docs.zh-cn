---
title: ICorRuntimeHost::UnloadDomain 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.UnloadDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type:
- apiref
ms.openlocfilehash: 558b6e4c6ac369e33be3d45b7241e8b11db8bfae
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760389"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="889b5-102">ICorRuntimeHost::UnloadDomain 方法</span><span class="sxs-lookup"><span data-stu-id="889b5-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="889b5-103">从当前进程中卸载指定的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="889b5-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="889b5-104">语法</span><span class="sxs-lookup"><span data-stu-id="889b5-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="889b5-105">参数</span><span class="sxs-lookup"><span data-stu-id="889b5-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="889b5-106">中表示要卸载的域的类型的指针 <xref:System._AppDomain?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="889b5-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="889b5-107">返回值</span><span class="sxs-lookup"><span data-stu-id="889b5-107">Return Value</span></span>  
  
|<span data-ttu-id="889b5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="889b5-108">HRESULT</span></span>|<span data-ttu-id="889b5-109">说明</span><span class="sxs-lookup"><span data-stu-id="889b5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="889b5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="889b5-110">S_OK</span></span>|<span data-ttu-id="889b5-111">操作成功。</span><span class="sxs-lookup"><span data-stu-id="889b5-111">The operation was successful.</span></span>|  
|<span data-ttu-id="889b5-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="889b5-112">S_FALSE</span></span>|<span data-ttu-id="889b5-113">操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="889b5-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="889b5-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="889b5-114">E_FAIL</span></span>|<span data-ttu-id="889b5-115">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="889b5-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="889b5-116">如果方法返回 E_FAIL，则公共语言运行时（CLR）在该过程中将不再可用。</span><span class="sxs-lookup"><span data-stu-id="889b5-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="889b5-117">对任何宿主 Api 的后续调用都会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="889b5-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="889b5-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="889b5-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="889b5-119">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="889b5-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="889b5-120">要求</span><span class="sxs-lookup"><span data-stu-id="889b5-120">Requirements</span></span>  
 <span data-ttu-id="889b5-121">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="889b5-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="889b5-122">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="889b5-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="889b5-123">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="889b5-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="889b5-124">**.NET Framework 版本：** 1.0、1。1</span><span class="sxs-lookup"><span data-stu-id="889b5-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="889b5-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="889b5-125">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="889b5-126">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="889b5-126">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
