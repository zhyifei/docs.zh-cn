---
title: ICLRReferenceAssemblyEnum 接口
ms.date: 03/30/2017
api_name:
- ICLRReferenceAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRReferenceAssemblyEnum
helpviewer_keywords:
- ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: 8adbf092-c3ba-4bee-b25b-0de6e43a4ce5
topic_type:
- apiref
ms.openlocfilehash: 466b0ceec8ce9c9800393f96055730ecafc153b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120549"
---
# <a name="iclrreferenceassemblyenum-interface"></a><span data-ttu-id="f2027-102">ICLRReferenceAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="f2027-102">ICLRReferenceAssemblyEnum Interface</span></span>
<span data-ttu-id="f2027-103">提供一些方法，这些方法使宿主可以使用公共语言运行时（CLR）内部的程序集标识数据来操作由文件或流引用的程序集集，而无需创建或了解这些标识。</span><span class="sxs-lookup"><span data-stu-id="f2027-103">Provides methods that allow the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the common language runtime (CLR), without needing to create or understand those identities.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f2027-104">方法</span><span class="sxs-lookup"><span data-stu-id="f2027-104">Methods</span></span>  
  
|<span data-ttu-id="f2027-105">方法</span><span class="sxs-lookup"><span data-stu-id="f2027-105">Method</span></span>|<span data-ttu-id="f2027-106">描述</span><span class="sxs-lookup"><span data-stu-id="f2027-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f2027-107">Get 方法</span><span class="sxs-lookup"><span data-stu-id="f2027-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-get-method.md)|<span data-ttu-id="f2027-108">获取所提供索引处的程序集标识。</span><span class="sxs-lookup"><span data-stu-id="f2027-108">Gets the assembly identity at the supplied index.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f2027-109">要求</span><span class="sxs-lookup"><span data-stu-id="f2027-109">Requirements</span></span>  
 <span data-ttu-id="f2027-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f2027-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2027-111">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f2027-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2027-112">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="f2027-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2027-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2027-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2027-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2027-114">See also</span></span>

- [<span data-ttu-id="f2027-115">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="f2027-115">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="f2027-116">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="f2027-116">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="f2027-117">承载接口</span><span class="sxs-lookup"><span data-stu-id="f2027-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
