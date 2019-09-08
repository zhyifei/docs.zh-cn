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
ms.openlocfilehash: 0d29b9e2a9b9022f682065816a62734d6c5b2d62
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796407"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="5b5d3-102">IInstallReferenceEnum 接口</span><span class="sxs-lookup"><span data-stu-id="5b5d3-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="5b5d3-103">表示安装在全局程序集缓存中的被引用程序集的枚举器。</span><span class="sxs-lookup"><span data-stu-id="5b5d3-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b5d3-104">语法</span><span class="sxs-lookup"><span data-stu-id="5b5d3-104">Syntax</span></span>  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5b5d3-105">方法</span><span class="sxs-lookup"><span data-stu-id="5b5d3-105">Methods</span></span>  
  
|<span data-ttu-id="5b5d3-106">方法</span><span class="sxs-lookup"><span data-stu-id="5b5d3-106">Method</span></span>|<span data-ttu-id="5b5d3-107">描述</span><span class="sxs-lookup"><span data-stu-id="5b5d3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5b5d3-108">GetNextInstallReferenceItem 方法</span><span class="sxs-lookup"><span data-stu-id="5b5d3-108">GetNextInstallReferenceItem Method</span></span>](iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="5b5d3-109">获取一个指针，该指针`IInstallReferenceItem`指向此`IInstallReferenceEnum`中包含的下一个。</span><span class="sxs-lookup"><span data-stu-id="5b5d3-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5b5d3-110">要求</span><span class="sxs-lookup"><span data-stu-id="5b5d3-110">Requirements</span></span>  
 <span data-ttu-id="5b5d3-111">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5b5d3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b5d3-112">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="5b5d3-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5b5d3-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b5d3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b5d3-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b5d3-114">See also</span></span>

- [<span data-ttu-id="5b5d3-115">合成接口</span><span class="sxs-lookup"><span data-stu-id="5b5d3-115">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="5b5d3-116">IInstallReferenceItem 接口</span><span class="sxs-lookup"><span data-stu-id="5b5d3-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
