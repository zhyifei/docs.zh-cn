---
title: IAssemblyName::GetProperty 方法
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetProperty
helpviewer_keywords:
- IAssemblyName::GetProperty method [.NET Framework fusion]
- GetProperty method [.NET Framework fusion]
ms.assetid: e59fda62-77d5-4e37-89cb-ce7ae4627975
topic_type:
- apiref
ms.openlocfilehash: b86828e01fb00b12feff2ed451793c240e16e240
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134378"
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="2e81a-102">IAssemblyName::GetProperty 方法</span><span class="sxs-lookup"><span data-stu-id="2e81a-102">IAssemblyName::GetProperty Method</span></span>
<span data-ttu-id="2e81a-103">获取一个指针，该指针指向由指定的属性标识符引用的属性。</span><span class="sxs-lookup"><span data-stu-id="2e81a-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e81a-104">语法</span><span class="sxs-lookup"><span data-stu-id="2e81a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e81a-105">参数</span><span class="sxs-lookup"><span data-stu-id="2e81a-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="2e81a-106">中请求的属性的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="2e81a-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="2e81a-107">弄返回的属性数据。</span><span class="sxs-lookup"><span data-stu-id="2e81a-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="2e81a-108">[in，out]`pvProperty`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="2e81a-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e81a-109">要求</span><span class="sxs-lookup"><span data-stu-id="2e81a-109">Requirements</span></span>  
 <span data-ttu-id="2e81a-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2e81a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e81a-111">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="2e81a-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2e81a-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e81a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e81a-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e81a-113">See also</span></span>

- [<span data-ttu-id="2e81a-114">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="2e81a-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
