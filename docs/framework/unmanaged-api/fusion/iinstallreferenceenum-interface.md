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
ms.openlocfilehash: d3f7c24b4bd373924c44dbc0490c890e7f1322bd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131735"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="d9f33-102">IInstallReferenceEnum 接口</span><span class="sxs-lookup"><span data-stu-id="d9f33-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="d9f33-103">表示安装在全局程序集缓存中的被引用程序集的枚举器。</span><span class="sxs-lookup"><span data-stu-id="d9f33-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9f33-104">语法</span><span class="sxs-lookup"><span data-stu-id="d9f33-104">Syntax</span></span>  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d9f33-105">方法</span><span class="sxs-lookup"><span data-stu-id="d9f33-105">Methods</span></span>  
  
|<span data-ttu-id="d9f33-106">方法</span><span class="sxs-lookup"><span data-stu-id="d9f33-106">Method</span></span>|<span data-ttu-id="d9f33-107">描述</span><span class="sxs-lookup"><span data-stu-id="d9f33-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d9f33-108">GetNextInstallReferenceItem 方法</span><span class="sxs-lookup"><span data-stu-id="d9f33-108">GetNextInstallReferenceItem Method</span></span>](iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="d9f33-109">获取一个指针，该指针指向此 `IInstallReferenceEnum`中包含的下一个 `IInstallReferenceItem`。</span><span class="sxs-lookup"><span data-stu-id="d9f33-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d9f33-110">要求</span><span class="sxs-lookup"><span data-stu-id="d9f33-110">Requirements</span></span>  
 <span data-ttu-id="d9f33-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d9f33-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9f33-112">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="d9f33-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d9f33-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9f33-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9f33-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9f33-114">See also</span></span>

- [<span data-ttu-id="d9f33-115">合成接口</span><span class="sxs-lookup"><span data-stu-id="d9f33-115">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="d9f33-116">IInstallReferenceItem 接口</span><span class="sxs-lookup"><span data-stu-id="d9f33-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
