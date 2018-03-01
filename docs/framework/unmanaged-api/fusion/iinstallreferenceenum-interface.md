---
title: "IInstallReferenceEnum 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IInstallReferenceEnum
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum
helpviewer_keywords:
- IInstallReferenceEnum interface [.NET Framework fusion]
ms.assetid: 2863b33b-a541-462c-bbe8-702a2832898e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2f1a80d1d79fce952a7071abd5e435604824d00e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="51f17-102">IInstallReferenceEnum 接口</span><span class="sxs-lookup"><span data-stu-id="51f17-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="51f17-103">表示引用的程序集安装到全局程序集缓存中的枚举数。</span><span class="sxs-lookup"><span data-stu-id="51f17-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51f17-104">语法</span><span class="sxs-lookup"><span data-stu-id="51f17-104">Syntax</span></span>  
  
```  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="51f17-105">方法</span><span class="sxs-lookup"><span data-stu-id="51f17-105">Methods</span></span>  
  
|<span data-ttu-id="51f17-106">方法</span><span class="sxs-lookup"><span data-stu-id="51f17-106">Method</span></span>|<span data-ttu-id="51f17-107">描述</span><span class="sxs-lookup"><span data-stu-id="51f17-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="51f17-108">GetNextInstallReferenceItem 方法</span><span class="sxs-lookup"><span data-stu-id="51f17-108">GetNextInstallReferenceItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="51f17-109">获取一个指针指向下一步`IInstallReferenceItem`包含在此`IInstallReferenceEnum`。</span><span class="sxs-lookup"><span data-stu-id="51f17-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="51f17-110">惠?</span><span class="sxs-lookup"><span data-stu-id="51f17-110">Requirements</span></span>  
 <span data-ttu-id="51f17-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="51f17-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51f17-112">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="51f17-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="51f17-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51f17-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51f17-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="51f17-114">See Also</span></span>  
 [<span data-ttu-id="51f17-115">合成接口</span><span class="sxs-lookup"><span data-stu-id="51f17-115">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="51f17-116">IInstallReferenceItem 接口</span><span class="sxs-lookup"><span data-stu-id="51f17-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
