---
title: IAssemblyEnum::GetNextAssembly 方法
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a77e468363b59e76e55aa24d97d064189ad297e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117736"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="90111-102">IAssemblyEnum::GetNextAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="90111-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="90111-103">获取一个指针指向下一步[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)包含在此[IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="90111-103">Gets a pointer to the next [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) contained in this [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90111-104">语法</span><span class="sxs-lookup"><span data-stu-id="90111-104">Syntax</span></span>  
  
```  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90111-105">参数</span><span class="sxs-lookup"><span data-stu-id="90111-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="90111-106">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="90111-106">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="90111-107">必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="90111-107">must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="90111-108">[out]返回`IAssemblyName`指针。</span><span class="sxs-lookup"><span data-stu-id="90111-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="90111-109">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="90111-109">[in] Reserved for future extensibility.</span></span> `dwFlags` <span data-ttu-id="90111-110">必须为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="90111-110">must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90111-111">要求</span><span class="sxs-lookup"><span data-stu-id="90111-111">Requirements</span></span>  
 <span data-ttu-id="90111-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90111-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90111-113">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="90111-113">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="90111-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="90111-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="90111-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="90111-115">See also</span></span>

- [<span data-ttu-id="90111-116">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="90111-116">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="90111-117">IAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="90111-117">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
