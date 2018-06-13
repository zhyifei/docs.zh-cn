---
title: ICLRAssemblyReferenceList 接口
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList
helpviewer_keywords:
- ICLRAssemblyReferenceList interface [.NET Framework hosting]
ms.assetid: 5f890fdf-d22a-429e-a35f-135273d1a636
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 388b26a5559435ea57300751987d14bc5cb9d50c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435292"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="60468-102">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="60468-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="60468-103">管理由公共语言运行时 (CLR) 而不是主机加载的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="60468-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="60468-104">方法</span><span class="sxs-lookup"><span data-stu-id="60468-104">Methods</span></span>  
  
|<span data-ttu-id="60468-105">方法</span><span class="sxs-lookup"><span data-stu-id="60468-105">Method</span></span>|<span data-ttu-id="60468-106">描述</span><span class="sxs-lookup"><span data-stu-id="60468-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="60468-107">IsAssemblyReferenceInList 方法</span><span class="sxs-lookup"><span data-stu-id="60468-107">IsAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="60468-108">获取一个值，该值指示所提供的指针是否引用列表中的程序集。</span><span class="sxs-lookup"><span data-stu-id="60468-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="60468-109">IsStringAssemblyReferenceInList 方法</span><span class="sxs-lookup"><span data-stu-id="60468-109">IsStringAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="60468-110">获取一个值，该值指示所提供的名称是否与列表中的程序集的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="60468-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60468-111">备注</span><span class="sxs-lookup"><span data-stu-id="60468-111">Remarks</span></span>  
 <span data-ttu-id="60468-112">调用[iclrassemblyidentitymanager:: Getclrassemblyreferencelist](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)方法以获取指向的实例的指针`ICLRAssemblyReferenceList`。</span><span class="sxs-lookup"><span data-stu-id="60468-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60468-113">要求</span><span class="sxs-lookup"><span data-stu-id="60468-113">Requirements</span></span>  
 <span data-ttu-id="60468-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="60468-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60468-115">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="60468-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="60468-116">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="60468-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="60468-117">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60468-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60468-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="60468-118">See Also</span></span>  
 [<span data-ttu-id="60468-119">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="60468-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="60468-120">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="60468-120">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [<span data-ttu-id="60468-121">承载接口</span><span class="sxs-lookup"><span data-stu-id="60468-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
