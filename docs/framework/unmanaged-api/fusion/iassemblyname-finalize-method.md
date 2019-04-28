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
ms.openlocfilehash: f4db24977d46277bc16a8800b0c4f7a550747cb9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697389"
---
# <a name="iassemblynamefinalize-method"></a><span data-ttu-id="d9ea0-102">IAssemblyName::Finalize 方法</span><span class="sxs-lookup"><span data-stu-id="d9ea0-102">IAssemblyName::Finalize Method</span></span>
<span data-ttu-id="d9ea0-103">允许此操作[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)对象释放资源并调用其析构函数之前执行其他清理操作。</span><span class="sxs-lookup"><span data-stu-id="d9ea0-103">Allows this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object to release resources and perform other cleanup operations before its destructor is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9ea0-104">语法</span><span class="sxs-lookup"><span data-stu-id="d9ea0-104">Syntax</span></span>  
  
```  
HRESULT Finalize ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="d9ea0-105">要求</span><span class="sxs-lookup"><span data-stu-id="d9ea0-105">Requirements</span></span>  
 <span data-ttu-id="d9ea0-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d9ea0-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9ea0-107">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="d9ea0-107">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d9ea0-108">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9ea0-108">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9ea0-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9ea0-109">See also</span></span>

- [<span data-ttu-id="d9ea0-110">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="d9ea0-110">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
