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
ms.openlocfilehash: 4b2860e811a16406a71d7ab8df123f2b32aaf13e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773295"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="06443-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList 方法</span><span class="sxs-lookup"><span data-stu-id="06443-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="06443-103">获取一个值，指示所提供的名称是否与列表中的程序集的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="06443-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06443-104">语法</span><span class="sxs-lookup"><span data-stu-id="06443-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06443-105">参数</span><span class="sxs-lookup"><span data-stu-id="06443-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="06443-106">[in]要搜索的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="06443-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06443-107">返回值</span><span class="sxs-lookup"><span data-stu-id="06443-107">Return Value</span></span>  
  
|<span data-ttu-id="06443-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="06443-108">HRESULT</span></span>|<span data-ttu-id="06443-109">描述</span><span class="sxs-lookup"><span data-stu-id="06443-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="06443-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="06443-110">S_OK</span></span>|<span data-ttu-id="06443-111">在列表中显示字符串。</span><span class="sxs-lookup"><span data-stu-id="06443-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="06443-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="06443-112">S_FALSE</span></span>|<span data-ttu-id="06443-113">列表中不显示字符串。</span><span class="sxs-lookup"><span data-stu-id="06443-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="06443-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="06443-114">E_FAIL</span></span>|<span data-ttu-id="06443-115">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="06443-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="06443-116">方法返回 E_FAIL 后，公共语言运行时不能再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="06443-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="06443-117">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="06443-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06443-118">要求</span><span class="sxs-lookup"><span data-stu-id="06443-118">Requirements</span></span>  
 <span data-ttu-id="06443-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="06443-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06443-120">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="06443-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06443-121">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="06443-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06443-122">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06443-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06443-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="06443-123">See also</span></span>

- [<span data-ttu-id="06443-124">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="06443-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="06443-125">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="06443-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="06443-126">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="06443-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="06443-127">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="06443-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
