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
ms.openlocfilehash: 35faeb69e864a428dc40394ad89a7d50b95bbcab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757659"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="777f4-102">IInstallReferenceEnum 接口</span><span class="sxs-lookup"><span data-stu-id="777f4-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="777f4-103">表示引用的程序集安装到全局程序集缓存中的枚举器。</span><span class="sxs-lookup"><span data-stu-id="777f4-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="777f4-104">语法</span><span class="sxs-lookup"><span data-stu-id="777f4-104">Syntax</span></span>  
  
```  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="777f4-105">方法</span><span class="sxs-lookup"><span data-stu-id="777f4-105">Methods</span></span>  
  
|<span data-ttu-id="777f4-106">方法</span><span class="sxs-lookup"><span data-stu-id="777f4-106">Method</span></span>|<span data-ttu-id="777f4-107">描述</span><span class="sxs-lookup"><span data-stu-id="777f4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="777f4-108">GetNextInstallReferenceItem 方法</span><span class="sxs-lookup"><span data-stu-id="777f4-108">GetNextInstallReferenceItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="777f4-109">获取一个指针指向下一步`IInstallReferenceItem`包含在此`IInstallReferenceEnum`。</span><span class="sxs-lookup"><span data-stu-id="777f4-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="777f4-110">要求</span><span class="sxs-lookup"><span data-stu-id="777f4-110">Requirements</span></span>  
 <span data-ttu-id="777f4-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="777f4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="777f4-112">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="777f4-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="777f4-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="777f4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="777f4-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="777f4-114">See also</span></span>

- [<span data-ttu-id="777f4-115">合成接口</span><span class="sxs-lookup"><span data-stu-id="777f4-115">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="777f4-116">IInstallReferenceItem 接口</span><span class="sxs-lookup"><span data-stu-id="777f4-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
