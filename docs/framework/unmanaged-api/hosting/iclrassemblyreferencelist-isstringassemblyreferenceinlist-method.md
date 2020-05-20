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
ms.openlocfilehash: 91f174cab4986882df795eb531baedfc0dd43962
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615860"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="68376-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList 方法</span><span class="sxs-lookup"><span data-stu-id="68376-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="68376-103">获取一个值，该值指示所提供的名称是否与列表中的程序集的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="68376-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68376-104">语法</span><span class="sxs-lookup"><span data-stu-id="68376-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68376-105">参数</span><span class="sxs-lookup"><span data-stu-id="68376-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="68376-106">中要搜索的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="68376-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68376-107">返回值</span><span class="sxs-lookup"><span data-stu-id="68376-107">Return Value</span></span>  
  
|<span data-ttu-id="68376-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="68376-108">HRESULT</span></span>|<span data-ttu-id="68376-109">说明</span><span class="sxs-lookup"><span data-stu-id="68376-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="68376-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="68376-110">S_OK</span></span>|<span data-ttu-id="68376-111">此字符串将显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="68376-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="68376-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="68376-112">S_FALSE</span></span>|<span data-ttu-id="68376-113">该字符串未出现在列表中。</span><span class="sxs-lookup"><span data-stu-id="68376-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="68376-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="68376-114">E_FAIL</span></span>|<span data-ttu-id="68376-115">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="68376-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="68376-116">方法返回 E_FAIL 后，公共语言运行时在进程中将不再可用。</span><span class="sxs-lookup"><span data-stu-id="68376-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="68376-117">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="68376-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="68376-118">要求</span><span class="sxs-lookup"><span data-stu-id="68376-118">Requirements</span></span>  
 <span data-ttu-id="68376-119">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="68376-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68376-120">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="68376-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68376-121">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="68376-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68376-122">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68376-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68376-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68376-123">See also</span></span>

- [<span data-ttu-id="68376-124">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="68376-124">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="68376-125">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="68376-125">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="68376-126">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="68376-126">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="68376-127">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="68376-127">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
