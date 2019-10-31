---
title: IAssemblyName::SetProperty 方法
ms.date: 03/30/2017
api_name:
- IAssemblyName.SetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::SetProperty
helpviewer_keywords:
- IAssemblyName::SetProperty method [.NET Framework fusion]
- SetProperty method [.NET Framework fusion]
ms.assetid: 496c3add-f60b-4073-943f-d1bcf33330cb
topic_type:
- apiref
ms.openlocfilehash: ffa1fa2f5e141728a56f1b598a1aae9602b2ac86
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108222"
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="a76b7-102">IAssemblyName::SetProperty 方法</span><span class="sxs-lookup"><span data-stu-id="a76b7-102">IAssemblyName::SetProperty Method</span></span>
<span data-ttu-id="a76b7-103">设置由指定的属性标识符引用的属性的值。</span><span class="sxs-lookup"><span data-stu-id="a76b7-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a76b7-104">语法</span><span class="sxs-lookup"><span data-stu-id="a76b7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a76b7-105">参数</span><span class="sxs-lookup"><span data-stu-id="a76b7-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="a76b7-106">中将设置其值的属性的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="a76b7-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="a76b7-107">中要将 `PropertyId`引用的属性设置为的值。</span><span class="sxs-lookup"><span data-stu-id="a76b7-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="a76b7-108">中`pvProperty`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="a76b7-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a76b7-109">要求</span><span class="sxs-lookup"><span data-stu-id="a76b7-109">Requirements</span></span>  
 <span data-ttu-id="a76b7-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a76b7-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a76b7-111">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="a76b7-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a76b7-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a76b7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a76b7-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="a76b7-113">See also</span></span>

- [<span data-ttu-id="a76b7-114">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="a76b7-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
