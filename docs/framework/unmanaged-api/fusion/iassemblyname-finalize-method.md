---
title: IAssemblyName::Finalize 方法
ms.date: 03/30/2017
api_name:
- IAssemblyName.Finalize
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::Finalize
helpviewer_keywords:
- Finalize method [.NET Framework fusion]
- IAssemblyName::Finalize method [.NET Framework fusion]
ms.assetid: 610e792d-98ef-411f-90b0-5b9a3813f547
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c5ea24594f5c7547dc75e6be9d53dd632513ff8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754008"
---
# <a name="iassemblynamefinalize-method"></a><span data-ttu-id="15ced-102">IAssemblyName::Finalize 方法</span><span class="sxs-lookup"><span data-stu-id="15ced-102">IAssemblyName::Finalize Method</span></span>
<span data-ttu-id="15ced-103">允许此操作[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)对象释放资源并调用其析构函数之前执行其他清理操作。</span><span class="sxs-lookup"><span data-stu-id="15ced-103">Allows this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object to release resources and perform other cleanup operations before its destructor is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15ced-104">语法</span><span class="sxs-lookup"><span data-stu-id="15ced-104">Syntax</span></span>  
  
```cpp  
HRESULT Finalize ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="15ced-105">要求</span><span class="sxs-lookup"><span data-stu-id="15ced-105">Requirements</span></span>  
 <span data-ttu-id="15ced-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="15ced-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15ced-107">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="15ced-107">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="15ced-108">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15ced-108">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15ced-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="15ced-109">See also</span></span>

- [<span data-ttu-id="15ced-110">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="15ced-110">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
