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
ms.openlocfilehash: 43c40e833e3a250239e9e90667196a2a74a96e0b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187650"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="f4228-102">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="f4228-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="f4228-103">管理由公共语言运行时 (CLR) 而不是主机加载的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="f4228-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f4228-104">方法</span><span class="sxs-lookup"><span data-stu-id="f4228-104">Methods</span></span>  
  
|<span data-ttu-id="f4228-105">方法</span><span class="sxs-lookup"><span data-stu-id="f4228-105">Method</span></span>|<span data-ttu-id="f4228-106">描述</span><span class="sxs-lookup"><span data-stu-id="f4228-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f4228-107">IsAssemblyReferenceInList 方法</span><span class="sxs-lookup"><span data-stu-id="f4228-107">IsAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="f4228-108">获取一个值，指示所提供的指针是否引用列表中的程序集。</span><span class="sxs-lookup"><span data-stu-id="f4228-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="f4228-109">IsStringAssemblyReferenceInList 方法</span><span class="sxs-lookup"><span data-stu-id="f4228-109">IsStringAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="f4228-110">获取一个值，指示所提供的名称是否与列表中的程序集的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="f4228-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4228-111">备注</span><span class="sxs-lookup"><span data-stu-id="f4228-111">Remarks</span></span>  
 <span data-ttu-id="f4228-112">调用[iclrassemblyidentitymanager:: Getclrassemblyreferencelist](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)方法来获得到的实例的指针`ICLRAssemblyReferenceList`。</span><span class="sxs-lookup"><span data-stu-id="f4228-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4228-113">要求</span><span class="sxs-lookup"><span data-stu-id="f4228-113">Requirements</span></span>  
 <span data-ttu-id="f4228-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f4228-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4228-115">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f4228-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f4228-116">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f4228-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f4228-117">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="f4228-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f4228-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4228-118">See also</span></span>

- [<span data-ttu-id="f4228-119">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="f4228-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="f4228-120">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="f4228-120">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="f4228-121">承载接口</span><span class="sxs-lookup"><span data-stu-id="f4228-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
