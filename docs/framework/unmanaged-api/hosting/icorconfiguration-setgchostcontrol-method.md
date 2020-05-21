---
title: ICorConfiguration::SetGCHostControl 方法
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCHostControl
helpviewer_keywords:
- ICorConfiguration::SetGCHostControl method [.NET Framework hosting]
- SetGCHostControl method [.NET Framework hosting]
ms.assetid: bca6bd79-e288-475a-aa46-6bf81541d966
topic_type:
- apiref
ms.openlocfilehash: e648b36a2b276d9335eefaf71b57ad76f9fe0def
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762378"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="cba90-102">ICorConfiguration::SetGCHostControl 方法</span><span class="sxs-lookup"><span data-stu-id="cba90-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="cba90-103">设置垃圾回收器用于请求主机更改虚拟内存限制的回调接口。</span><span class="sxs-lookup"><span data-stu-id="cba90-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cba90-104">语法</span><span class="sxs-lookup"><span data-stu-id="cba90-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cba90-105">参数</span><span class="sxs-lookup"><span data-stu-id="cba90-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="cba90-106">中指向[IGCHostControl](igchostcontrol-interface.md)对象的指针，该对象允许垃圾回收器请求主机更改虚拟内存的限制。</span><span class="sxs-lookup"><span data-stu-id="cba90-106">[in] A pointer to an [IGCHostControl](igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cba90-107">要求</span><span class="sxs-lookup"><span data-stu-id="cba90-107">Requirements</span></span>  
 <span data-ttu-id="cba90-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cba90-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cba90-109">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="cba90-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cba90-110">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="cba90-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cba90-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cba90-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cba90-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cba90-112">See also</span></span>

- [<span data-ttu-id="cba90-113">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="cba90-113">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
