---
title: IInstallReferenceEnum 接口
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5781254b508887f2e76f6ca0eca6a2830ada172b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774012"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="12e61-102">IInstallReferenceEnum 接口</span><span class="sxs-lookup"><span data-stu-id="12e61-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="12e61-103">表示引用的程序集安装到全局程序集缓存中的枚举器。</span><span class="sxs-lookup"><span data-stu-id="12e61-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12e61-104">语法</span><span class="sxs-lookup"><span data-stu-id="12e61-104">Syntax</span></span>  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="12e61-105">方法</span><span class="sxs-lookup"><span data-stu-id="12e61-105">Methods</span></span>  
  
|<span data-ttu-id="12e61-106">方法</span><span class="sxs-lookup"><span data-stu-id="12e61-106">Method</span></span>|<span data-ttu-id="12e61-107">描述</span><span class="sxs-lookup"><span data-stu-id="12e61-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="12e61-108">GetNextInstallReferenceItem 方法</span><span class="sxs-lookup"><span data-stu-id="12e61-108">GetNextInstallReferenceItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="12e61-109">获取一个指针指向下一步`IInstallReferenceItem`包含在此`IInstallReferenceEnum`。</span><span class="sxs-lookup"><span data-stu-id="12e61-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="12e61-110">要求</span><span class="sxs-lookup"><span data-stu-id="12e61-110">Requirements</span></span>  
 <span data-ttu-id="12e61-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="12e61-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12e61-112">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="12e61-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="12e61-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12e61-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12e61-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="12e61-114">See also</span></span>

- [<span data-ttu-id="12e61-115">合成接口</span><span class="sxs-lookup"><span data-stu-id="12e61-115">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="12e61-116">IInstallReferenceItem 接口</span><span class="sxs-lookup"><span data-stu-id="12e61-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
