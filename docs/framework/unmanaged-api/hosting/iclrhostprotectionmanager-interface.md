---
title: ICLRHostProtectionManager 接口
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager
helpviewer_keywords:
- ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type:
- apiref
ms.openlocfilehash: 7b1fc70380fff3c551c56043f49c2deda507e366
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703842"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="44f85-102">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="44f85-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="44f85-103">允许宿主阻止在部分受信任的代码中运行特定的托管类、方法、属性和字段。</span><span class="sxs-lookup"><span data-stu-id="44f85-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="44f85-104">方法</span><span class="sxs-lookup"><span data-stu-id="44f85-104">Methods</span></span>  
  
|<span data-ttu-id="44f85-105">方法</span><span class="sxs-lookup"><span data-stu-id="44f85-105">Method</span></span>|<span data-ttu-id="44f85-106">说明</span><span class="sxs-lookup"><span data-stu-id="44f85-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="44f85-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="44f85-107">SetEagerSerializeGrantSets</span></span>](iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="44f85-108">保证某些极少数争用条件可能会导致严重的公共语言运行时（CLR）错误。</span><span class="sxs-lookup"><span data-stu-id="44f85-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="44f85-109">SetProtectedCategories 方法</span><span class="sxs-lookup"><span data-stu-id="44f85-109">SetProtectedCategories Method</span></span>](iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="44f85-110">指定应阻止在部分受信任代码中运行的托管类型和成员的类别。</span><span class="sxs-lookup"><span data-stu-id="44f85-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="44f85-111">要求</span><span class="sxs-lookup"><span data-stu-id="44f85-111">Requirements</span></span>  
 <span data-ttu-id="44f85-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="44f85-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44f85-113">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="44f85-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="44f85-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="44f85-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="44f85-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44f85-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44f85-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44f85-116">See also</span></span>

- [<span data-ttu-id="44f85-117">EApiCategories 枚举</span><span class="sxs-lookup"><span data-stu-id="44f85-117">EApiCategories Enumeration</span></span>](eapicategories-enumeration.md)
- [<span data-ttu-id="44f85-118">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="44f85-118">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
