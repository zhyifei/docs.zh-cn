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
ms.openlocfilehash: 1f2f7ba822507a30fe8cd5303f53406d34661833
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796616"
---
# <a name="iassemblynamefinalize-method"></a><span data-ttu-id="a9e5f-102">IAssemblyName::Finalize 方法</span><span class="sxs-lookup"><span data-stu-id="a9e5f-102">IAssemblyName::Finalize Method</span></span>
<span data-ttu-id="a9e5f-103">允许此[IAssemblyName](iassemblyname-interface.md)对象在调用其析构函数之前释放资源并执行其他清理操作。</span><span class="sxs-lookup"><span data-stu-id="a9e5f-103">Allows this [IAssemblyName](iassemblyname-interface.md) object to release resources and perform other cleanup operations before its destructor is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9e5f-104">语法</span><span class="sxs-lookup"><span data-stu-id="a9e5f-104">Syntax</span></span>  
  
```cpp  
HRESULT Finalize ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="a9e5f-105">要求</span><span class="sxs-lookup"><span data-stu-id="a9e5f-105">Requirements</span></span>  
 <span data-ttu-id="a9e5f-106">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a9e5f-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9e5f-107">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="a9e5f-107">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a9e5f-108">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9e5f-108">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9e5f-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9e5f-109">See also</span></span>

- [<span data-ttu-id="a9e5f-110">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="a9e5f-110">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
