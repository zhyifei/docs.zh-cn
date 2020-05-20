---
title: ICLRDomainManager 接口
ms.date: 03/30/2017
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
ms.openlocfilehash: dda243ccbf18f396c1bcc03358997ea0f06c42a8
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615704"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="8e7ef-102">ICLRDomainManager 接口</span><span class="sxs-lookup"><span data-stu-id="8e7ef-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="8e7ef-103">使宿主能够指定将用于初始化默认应用程序域的应用程序域管理器，并指定初始化属性。</span><span class="sxs-lookup"><span data-stu-id="8e7ef-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8e7ef-104">方法</span><span class="sxs-lookup"><span data-stu-id="8e7ef-104">Methods</span></span>  
  
|<span data-ttu-id="8e7ef-105">方法</span><span class="sxs-lookup"><span data-stu-id="8e7ef-105">Method</span></span>|<span data-ttu-id="8e7ef-106">说明</span><span class="sxs-lookup"><span data-stu-id="8e7ef-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8e7ef-107">SetAppDomainManagerType 方法</span><span class="sxs-lookup"><span data-stu-id="8e7ef-107">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="8e7ef-108">指定从类派生的、 <xref:System.AppDomainManager?displayProperty=nameWithType> 将用于初始化默认应用程序域的应用程序域管理器的类型。</span><span class="sxs-lookup"><span data-stu-id="8e7ef-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="8e7ef-109">SetPropertiesForDefaultAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="8e7ef-109">SetPropertiesForDefaultAppDomain Method</span></span>](iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="8e7ef-110">设置将用于初始化默认应用程序域的属性。</span><span class="sxs-lookup"><span data-stu-id="8e7ef-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e7ef-111">备注</span><span class="sxs-lookup"><span data-stu-id="8e7ef-111">Remarks</span></span>  
 <span data-ttu-id="8e7ef-112">若要获取此接口的实例，请使用管理器类型 IID 调用[ICLRControl：： GetCLRManager](iclrcontrol-getclrmanager-method.md)方法 `IID_ICLRDomainManager` 。</span><span class="sxs-lookup"><span data-stu-id="8e7ef-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e7ef-113">要求</span><span class="sxs-lookup"><span data-stu-id="8e7ef-113">Requirements</span></span>  
 <span data-ttu-id="8e7ef-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8e7ef-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e7ef-115">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="8e7ef-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8e7ef-116">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8e7ef-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e7ef-117">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e7ef-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e7ef-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e7ef-118">See also</span></span>

- [<span data-ttu-id="8e7ef-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="8e7ef-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="8e7ef-120">承载</span><span class="sxs-lookup"><span data-stu-id="8e7ef-120">Hosting</span></span>](index.md)
