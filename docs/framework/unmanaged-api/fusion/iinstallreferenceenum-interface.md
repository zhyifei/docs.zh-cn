---
title: "IInstallReferenceEnum 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IInstallReferenceEnum
api_location: fusion.dll
api_type: COM
f1_keywords: IInstallReferenceEnum
helpviewer_keywords: IInstallReferenceEnum interface [.NET Framework fusion]
ms.assetid: 2863b33b-a541-462c-bbe8-702a2832898e
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d3847d06c77a92eb6e63542f03405ca0cb9c9560
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="bc9c7-102">IInstallReferenceEnum 接口</span><span class="sxs-lookup"><span data-stu-id="bc9c7-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="bc9c7-103">表示引用的程序集安装到全局程序集缓存中的枚举数。</span><span class="sxs-lookup"><span data-stu-id="bc9c7-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc9c7-104">语法</span><span class="sxs-lookup"><span data-stu-id="bc9c7-104">Syntax</span></span>  
  
```  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bc9c7-105">方法</span><span class="sxs-lookup"><span data-stu-id="bc9c7-105">Methods</span></span>  
  
|<span data-ttu-id="bc9c7-106">方法</span><span class="sxs-lookup"><span data-stu-id="bc9c7-106">Method</span></span>|<span data-ttu-id="bc9c7-107">描述</span><span class="sxs-lookup"><span data-stu-id="bc9c7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bc9c7-108">GetNextInstallReferenceItem 方法</span><span class="sxs-lookup"><span data-stu-id="bc9c7-108">GetNextInstallReferenceItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="bc9c7-109">获取一个指针指向下一步`IInstallReferenceItem`包含在此`IInstallReferenceEnum`。</span><span class="sxs-lookup"><span data-stu-id="bc9c7-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bc9c7-110">要求</span><span class="sxs-lookup"><span data-stu-id="bc9c7-110">Requirements</span></span>  
 <span data-ttu-id="bc9c7-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bc9c7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc9c7-112">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="bc9c7-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="bc9c7-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc9c7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc9c7-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc9c7-114">See Also</span></span>  
 [<span data-ttu-id="bc9c7-115">合成接口</span><span class="sxs-lookup"><span data-stu-id="bc9c7-115">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="bc9c7-116">IInstallReferenceItem 接口</span><span class="sxs-lookup"><span data-stu-id="bc9c7-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
