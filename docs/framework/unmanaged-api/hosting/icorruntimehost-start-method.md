---
title: ICorRuntimeHost::Start 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Start
helpviewer_keywords:
- Start method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Start method [.NET Framework hosting]
ms.assetid: c66f3ac5-6489-484a-9bed-c31b711cee01
topic_type:
- apiref
ms.openlocfilehash: ccad76e1c8a49222d4f527f8b7b18d4e40ff8cae
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760402"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="093df-102">ICorRuntimeHost::Start 方法</span><span class="sxs-lookup"><span data-stu-id="093df-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="093df-103">启动公共语言运行时（CLR）。</span><span class="sxs-lookup"><span data-stu-id="093df-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="093df-104">语法</span><span class="sxs-lookup"><span data-stu-id="093df-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="093df-105">返回值</span><span class="sxs-lookup"><span data-stu-id="093df-105">Return Value</span></span>  
  
|<span data-ttu-id="093df-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="093df-106">HRESULT</span></span>|<span data-ttu-id="093df-107">说明</span><span class="sxs-lookup"><span data-stu-id="093df-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="093df-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="093df-108">S_OK</span></span>|<span data-ttu-id="093df-109">操作成功。</span><span class="sxs-lookup"><span data-stu-id="093df-109">The operation was successful.</span></span>|  
|<span data-ttu-id="093df-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="093df-110">S_FALSE</span></span>|<span data-ttu-id="093df-111">操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="093df-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="093df-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="093df-112">E_FAIL</span></span>|<span data-ttu-id="093df-113">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="093df-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="093df-114">如果某个方法返回 E_FAIL，则 CLR 将无法再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="093df-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="093df-115">对任何宿主 Api 的后续调用都会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="093df-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="093df-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="093df-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="093df-117">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="093df-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="093df-118">注解</span><span class="sxs-lookup"><span data-stu-id="093df-118">Remarks</span></span>  
 <span data-ttu-id="093df-119">通常不需要调用 `Start` 方法，因为 CLR 会在首次运行托管代码请求时自动启动。</span><span class="sxs-lookup"><span data-stu-id="093df-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="093df-120">要求</span><span class="sxs-lookup"><span data-stu-id="093df-120">Requirements</span></span>  
 <span data-ttu-id="093df-121">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="093df-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="093df-122">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="093df-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="093df-123">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="093df-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="093df-124">**.NET Framework 版本：** 1.0、1。1</span><span class="sxs-lookup"><span data-stu-id="093df-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="093df-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="093df-125">See also</span></span>

- [<span data-ttu-id="093df-126">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="093df-126">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
