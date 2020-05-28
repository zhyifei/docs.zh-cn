---
title: IMetaDataEmit::SetMethodImplFlags 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodImplFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type:
- apiref
ms.openlocfilehash: a02456393680169ce33369ee5914f6c5216081c6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009211"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="3fe8c-102">IMetaDataEmit::SetMethodImplFlags 方法</span><span class="sxs-lookup"><span data-stu-id="3fe8c-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="3fe8c-103">设置或更新指定的标记所引用的继承方法实现的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="3fe8c-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fe8c-104">语法</span><span class="sxs-lookup"><span data-stu-id="3fe8c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (
    [in]  mdMethodDef   md,
    [in]  DWORD         dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fe8c-105">参数</span><span class="sxs-lookup"><span data-stu-id="3fe8c-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="3fe8c-106">中要更改的方法的标记。</span><span class="sxs-lookup"><span data-stu-id="3fe8c-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="3fe8c-107">中用于指定方法实现功能的[CorMethodImpl](cormethodimpl-enumeration.md)枚举值的组合。</span><span class="sxs-lookup"><span data-stu-id="3fe8c-107">[in] A combination of the values of the [CorMethodImpl](cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fe8c-108">要求</span><span class="sxs-lookup"><span data-stu-id="3fe8c-108">Requirements</span></span>  
 <span data-ttu-id="3fe8c-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3fe8c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fe8c-110">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="3fe8c-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3fe8c-111">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3fe8c-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3fe8c-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fe8c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fe8c-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3fe8c-113">See also</span></span>

- [<span data-ttu-id="3fe8c-114">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="3fe8c-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="3fe8c-115">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="3fe8c-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
