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
ms.openlocfilehash: 0632a7f5feee87c386d9488a6c989413af68a47f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615886"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="d2ef0-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList 方法</span><span class="sxs-lookup"><span data-stu-id="d2ef0-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>
<span data-ttu-id="d2ef0-103">获取一个值，该值指示提供的指针是否引用列表中的程序集。</span><span class="sxs-lookup"><span data-stu-id="d2ef0-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2ef0-104">语法</span><span class="sxs-lookup"><span data-stu-id="d2ef0-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2ef0-105">参数</span><span class="sxs-lookup"><span data-stu-id="d2ef0-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="d2ef0-106">中一个接口指针，指向要搜索的程序集。</span><span class="sxs-lookup"><span data-stu-id="d2ef0-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="d2ef0-107">有效值的类型为 `IAssemblyName` 或 `IReferenceIdentity` 。</span><span class="sxs-lookup"><span data-stu-id="d2ef0-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2ef0-108">返回值</span><span class="sxs-lookup"><span data-stu-id="d2ef0-108">Return Value</span></span>  
  
|<span data-ttu-id="d2ef0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d2ef0-109">HRESULT</span></span>|<span data-ttu-id="d2ef0-110">说明</span><span class="sxs-lookup"><span data-stu-id="d2ef0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d2ef0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d2ef0-111">S_OK</span></span>|<span data-ttu-id="d2ef0-112">此字符串将显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="d2ef0-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="d2ef0-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d2ef0-113">S_FALSE</span></span>|<span data-ttu-id="d2ef0-114">该字符串未出现在列表中。</span><span class="sxs-lookup"><span data-stu-id="d2ef0-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="d2ef0-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d2ef0-115">E_FAIL</span></span>|<span data-ttu-id="d2ef0-116">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d2ef0-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d2ef0-117">方法返回 E_FAIL 后，公共语言运行时在进程中将不再可用。</span><span class="sxs-lookup"><span data-stu-id="d2ef0-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="d2ef0-118">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d2ef0-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d2ef0-119">要求</span><span class="sxs-lookup"><span data-stu-id="d2ef0-119">Requirements</span></span>  
 <span data-ttu-id="d2ef0-120">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d2ef0-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2ef0-121">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d2ef0-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d2ef0-122">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d2ef0-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2ef0-123">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2ef0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2ef0-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2ef0-124">See also</span></span>

- [<span data-ttu-id="d2ef0-125">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="d2ef0-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="d2ef0-126">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="d2ef0-126">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="d2ef0-127">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="d2ef0-127">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="d2ef0-128">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="d2ef0-128">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
