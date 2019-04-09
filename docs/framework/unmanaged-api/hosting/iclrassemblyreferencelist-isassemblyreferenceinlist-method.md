---
title: ICLRAssemblyReferenceList::IsAssemblyReferenceInList 方法
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList method [.NET Framework hosting]
- IsAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: 8a570813-21be-407e-92a6-7ae8de3bc728
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6a95a636623f0b4ea75706039194572ecf1bbe0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136196"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="fba3e-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList 方法</span><span class="sxs-lookup"><span data-stu-id="fba3e-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>
<span data-ttu-id="fba3e-103">获取一个值，该值指示是否在列表中的程序集引用所提供的指针。</span><span class="sxs-lookup"><span data-stu-id="fba3e-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fba3e-104">语法</span><span class="sxs-lookup"><span data-stu-id="fba3e-104">Syntax</span></span>  
  
```  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fba3e-105">参数</span><span class="sxs-lookup"><span data-stu-id="fba3e-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="fba3e-106">[in]指向要搜索的程序集的接口指针。</span><span class="sxs-lookup"><span data-stu-id="fba3e-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="fba3e-107">有效的值属于类型`IAssemblyName`或`IReferenceIdentity`。</span><span class="sxs-lookup"><span data-stu-id="fba3e-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fba3e-108">返回值</span><span class="sxs-lookup"><span data-stu-id="fba3e-108">Return Value</span></span>  
  
|<span data-ttu-id="fba3e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fba3e-109">HRESULT</span></span>|<span data-ttu-id="fba3e-110">描述</span><span class="sxs-lookup"><span data-stu-id="fba3e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fba3e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fba3e-111">S_OK</span></span>|<span data-ttu-id="fba3e-112">在列表中显示字符串。</span><span class="sxs-lookup"><span data-stu-id="fba3e-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="fba3e-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="fba3e-113">S_FALSE</span></span>|<span data-ttu-id="fba3e-114">列表中不显示字符串。</span><span class="sxs-lookup"><span data-stu-id="fba3e-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="fba3e-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fba3e-115">E_FAIL</span></span>|<span data-ttu-id="fba3e-116">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="fba3e-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fba3e-117">方法返回 E_FAIL 后，公共语言运行时不能再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="fba3e-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="fba3e-118">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="fba3e-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fba3e-119">要求</span><span class="sxs-lookup"><span data-stu-id="fba3e-119">Requirements</span></span>  
 <span data-ttu-id="fba3e-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fba3e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fba3e-121">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fba3e-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fba3e-122">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fba3e-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="fba3e-123">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="fba3e-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fba3e-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="fba3e-124">See also</span></span>

- [<span data-ttu-id="fba3e-125">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="fba3e-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="fba3e-126">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="fba3e-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="fba3e-127">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="fba3e-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="fba3e-128">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="fba3e-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
