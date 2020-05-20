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
ms.openlocfilehash: f1aa40ef868bf6ff7730e01ab66a6fec58af1196
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615873"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="a57d2-102">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="a57d2-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="a57d2-103">管理由公共语言运行时（CLR）而不是由宿主加载的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="a57d2-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a57d2-104">方法</span><span class="sxs-lookup"><span data-stu-id="a57d2-104">Methods</span></span>  
  
|<span data-ttu-id="a57d2-105">方法</span><span class="sxs-lookup"><span data-stu-id="a57d2-105">Method</span></span>|<span data-ttu-id="a57d2-106">说明</span><span class="sxs-lookup"><span data-stu-id="a57d2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a57d2-107">IsAssemblyReferenceInList 方法</span><span class="sxs-lookup"><span data-stu-id="a57d2-107">IsAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="a57d2-108">获取一个值，该值指示提供的指针是否引用列表中的程序集。</span><span class="sxs-lookup"><span data-stu-id="a57d2-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="a57d2-109">IsStringAssemblyReferenceInList 方法</span><span class="sxs-lookup"><span data-stu-id="a57d2-109">IsStringAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="a57d2-110">获取一个值，该值指示所提供的名称是否与列表中的程序集的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="a57d2-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a57d2-111">备注</span><span class="sxs-lookup"><span data-stu-id="a57d2-111">Remarks</span></span>  
 <span data-ttu-id="a57d2-112">调用[ICLRAssemblyIdentityManager：： GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)方法以获取指向实例的指针 `ICLRAssemblyReferenceList` 。</span><span class="sxs-lookup"><span data-stu-id="a57d2-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a57d2-113">要求</span><span class="sxs-lookup"><span data-stu-id="a57d2-113">Requirements</span></span>  
 <span data-ttu-id="a57d2-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a57d2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a57d2-115">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a57d2-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a57d2-116">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="a57d2-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a57d2-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a57d2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a57d2-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a57d2-118">See also</span></span>

- [<span data-ttu-id="a57d2-119">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="a57d2-119">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="a57d2-120">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="a57d2-120">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="a57d2-121">承载接口</span><span class="sxs-lookup"><span data-stu-id="a57d2-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
