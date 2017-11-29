---
title: "ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyReferenceList.IsStringAssemblyReferenceInList
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList method [.NET Framework hosting]
- IsStringAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: e6121cc3-2f11-42c7-bdae-47808581ff71
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ff0e51327e0e66c2a282ebf46e6036f81d3d568b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="d4028-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList 方法</span><span class="sxs-lookup"><span data-stu-id="d4028-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="d4028-103">获取一个值，该值指示所提供的名称是否与列表中的程序集的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="d4028-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4028-104">语法</span><span class="sxs-lookup"><span data-stu-id="d4028-104">Syntax</span></span>  
  
```  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4028-105">参数</span><span class="sxs-lookup"><span data-stu-id="d4028-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="d4028-106">[in]要搜索程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="d4028-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4028-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d4028-107">Return Value</span></span>  
  
|<span data-ttu-id="d4028-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d4028-108">HRESULT</span></span>|<span data-ttu-id="d4028-109">描述</span><span class="sxs-lookup"><span data-stu-id="d4028-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d4028-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d4028-110">S_OK</span></span>|<span data-ttu-id="d4028-111">在列表中显示字符串。</span><span class="sxs-lookup"><span data-stu-id="d4028-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="d4028-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d4028-112">S_FALSE</span></span>|<span data-ttu-id="d4028-113">列表中不显示字符串。</span><span class="sxs-lookup"><span data-stu-id="d4028-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="d4028-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d4028-114">E_FAIL</span></span>|<span data-ttu-id="d4028-115">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d4028-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d4028-116">方法返回 E_FAIL 后，公共语言运行时不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="d4028-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="d4028-117">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d4028-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d4028-118">要求</span><span class="sxs-lookup"><span data-stu-id="d4028-118">Requirements</span></span>  
 <span data-ttu-id="d4028-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d4028-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4028-120">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d4028-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d4028-121">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d4028-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d4028-122">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4028-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4028-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4028-123">See Also</span></span>  
 [<span data-ttu-id="d4028-124">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="d4028-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="d4028-125">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="d4028-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="d4028-126">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="d4028-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="d4028-127">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="d4028-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
