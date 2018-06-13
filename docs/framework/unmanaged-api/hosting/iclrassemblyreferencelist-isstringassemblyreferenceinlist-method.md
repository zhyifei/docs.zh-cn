---
title: ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList 方法
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsStringAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList method [.NET Framework hosting]
- IsStringAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: e6121cc3-2f11-42c7-bdae-47808581ff71
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad7230731775cbc56dd0f1eaed72df19512d3733
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432591"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="4cda4-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList 方法</span><span class="sxs-lookup"><span data-stu-id="4cda4-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="4cda4-103">获取一个值，该值指示所提供的名称是否与列表中的程序集的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="4cda4-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cda4-104">语法</span><span class="sxs-lookup"><span data-stu-id="4cda4-104">Syntax</span></span>  
  
```  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4cda4-105">参数</span><span class="sxs-lookup"><span data-stu-id="4cda4-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="4cda4-106">[in]要搜索程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="4cda4-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4cda4-107">返回值</span><span class="sxs-lookup"><span data-stu-id="4cda4-107">Return Value</span></span>  
  
|<span data-ttu-id="4cda4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4cda4-108">HRESULT</span></span>|<span data-ttu-id="4cda4-109">描述</span><span class="sxs-lookup"><span data-stu-id="4cda4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4cda4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4cda4-110">S_OK</span></span>|<span data-ttu-id="4cda4-111">在列表中显示字符串。</span><span class="sxs-lookup"><span data-stu-id="4cda4-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="4cda4-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4cda4-112">S_FALSE</span></span>|<span data-ttu-id="4cda4-113">列表中不显示字符串。</span><span class="sxs-lookup"><span data-stu-id="4cda4-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="4cda4-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4cda4-114">E_FAIL</span></span>|<span data-ttu-id="4cda4-115">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="4cda4-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4cda4-116">方法返回 E_FAIL 后，公共语言运行时不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="4cda4-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="4cda4-117">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="4cda4-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4cda4-118">要求</span><span class="sxs-lookup"><span data-stu-id="4cda4-118">Requirements</span></span>  
 <span data-ttu-id="4cda4-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4cda4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cda4-120">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4cda4-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4cda4-121">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4cda4-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4cda4-122">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cda4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cda4-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cda4-123">See Also</span></span>  
 [<span data-ttu-id="4cda4-124">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="4cda4-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="4cda4-125">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="4cda4-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="4cda4-126">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="4cda4-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="4cda4-127">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="4cda4-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
