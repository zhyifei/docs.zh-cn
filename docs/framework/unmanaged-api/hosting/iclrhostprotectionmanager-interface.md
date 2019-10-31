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
ms.openlocfilehash: 0487a87420c888cf5466f54c28c2d89623260add
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141048"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="8c403-102">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="8c403-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="8c403-103">允许宿主阻止在部分受信任的代码中运行特定的托管类、方法、属性和字段。</span><span class="sxs-lookup"><span data-stu-id="8c403-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8c403-104">方法</span><span class="sxs-lookup"><span data-stu-id="8c403-104">Methods</span></span>  
  
|<span data-ttu-id="8c403-105">方法</span><span class="sxs-lookup"><span data-stu-id="8c403-105">Method</span></span>|<span data-ttu-id="8c403-106">描述</span><span class="sxs-lookup"><span data-stu-id="8c403-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8c403-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="8c403-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="8c403-108">保证某些极少数争用条件可能会导致严重的公共语言运行时（CLR）错误。</span><span class="sxs-lookup"><span data-stu-id="8c403-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="8c403-109">SetProtectedCategories 方法</span><span class="sxs-lookup"><span data-stu-id="8c403-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="8c403-110">指定应阻止在部分受信任代码中运行的托管类型和成员的类别。</span><span class="sxs-lookup"><span data-stu-id="8c403-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c403-111">要求</span><span class="sxs-lookup"><span data-stu-id="8c403-111">Requirements</span></span>  
 <span data-ttu-id="8c403-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8c403-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c403-113">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8c403-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8c403-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8c403-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c403-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c403-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c403-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c403-116">See also</span></span>

- [<span data-ttu-id="8c403-117">EApiCategories 枚举</span><span class="sxs-lookup"><span data-stu-id="8c403-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="8c403-118">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="8c403-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
