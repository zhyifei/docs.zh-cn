---
title: ICLRProbingAssemblyEnum 接口
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum
helpviewer_keywords:
- ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type:
- apiref
ms.openlocfilehash: e1e114070f39e75254fc1bc0f8c1bf3e4733d5a2
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703370"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="c4ef1-102">ICLRProbingAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="c4ef1-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="c4ef1-103">提供使宿主可以通过使用公共语言运行时（CLR）内部的程序集的标识信息来获取程序集的探测标识的方法，无需创建或了解该标识。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c4ef1-104">方法</span><span class="sxs-lookup"><span data-stu-id="c4ef1-104">Methods</span></span>  
  
|<span data-ttu-id="c4ef1-105">方法</span><span class="sxs-lookup"><span data-stu-id="c4ef1-105">Method</span></span>|<span data-ttu-id="c4ef1-106">说明</span><span class="sxs-lookup"><span data-stu-id="c4ef1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c4ef1-107">Get 方法</span><span class="sxs-lookup"><span data-stu-id="c4ef1-107">Get Method</span></span>](iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="c4ef1-108">获取指定索引处的程序集标识。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4ef1-109">备注</span><span class="sxs-lookup"><span data-stu-id="c4ef1-109">Remarks</span></span>  
 <span data-ttu-id="c4ef1-110">方法（如[ICLRAssemblyIdentityManager：： GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) ）返回 `ICLRProbingAssemblyEnum` 实例。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4ef1-111">要求</span><span class="sxs-lookup"><span data-stu-id="c4ef1-111">Requirements</span></span>  
 <span data-ttu-id="c4ef1-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4ef1-113">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c4ef1-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4ef1-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c4ef1-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4ef1-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4ef1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4ef1-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4ef1-116">See also</span></span>

- [<span data-ttu-id="c4ef1-117">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="c4ef1-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="c4ef1-118">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="c4ef1-118">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="c4ef1-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="c4ef1-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
