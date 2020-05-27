---
title: IMetaDataEmit::SetMethodProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type:
- apiref
ms.openlocfilehash: 57f6de1f7edf7c75a3f96cb2bf9fb98fdbd6f65e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007853"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="fca27-102">IMetaDataEmit::SetMethodProps 方法</span><span class="sxs-lookup"><span data-stu-id="fca27-102">IMetaDataEmit::SetMethodProps Method</span></span>
<span data-ttu-id="fca27-103">设置或更新在指定的相对虚拟地址上存储的功能，该方法由之前对 IMetaDataEmit 的调用定义的方法[：:D efinemethod](imetadataemit-definemethod-method.md)。</span><span class="sxs-lookup"><span data-stu-id="fca27-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fca27-104">语法</span><span class="sxs-lookup"><span data-stu-id="fca27-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodProps (
    [in]  mdMethodDef md,
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,
    [in]  DWORD       dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fca27-105">参数</span><span class="sxs-lookup"><span data-stu-id="fca27-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="fca27-106">中要更改的方法的标记。</span><span class="sxs-lookup"><span data-stu-id="fca27-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="fca27-107">中成员特性。</span><span class="sxs-lookup"><span data-stu-id="fca27-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="fca27-108">中代码的地址。</span><span class="sxs-lookup"><span data-stu-id="fca27-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="fca27-109">中方法的实现标志。</span><span class="sxs-lookup"><span data-stu-id="fca27-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fca27-110">要求</span><span class="sxs-lookup"><span data-stu-id="fca27-110">Requirements</span></span>  
 <span data-ttu-id="fca27-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fca27-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fca27-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="fca27-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fca27-113">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fca27-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fca27-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fca27-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fca27-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fca27-115">See also</span></span>

- [<span data-ttu-id="fca27-116">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="fca27-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="fca27-117">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="fca27-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
