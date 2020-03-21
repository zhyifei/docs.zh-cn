---
title: IMetaDataEmit::SetModuleProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetModuleProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type:
- apiref
ms.openlocfilehash: 69c3ee366dbb8505e0df744037c480da996bb836
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175611"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="a9b57-102">IMetaDataEmit::SetModuleProps 方法</span><span class="sxs-lookup"><span data-stu-id="a9b57-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="a9b57-103">更新对以前调用[IMetaDataEmit：:DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)） 定义的模块的引用。</span><span class="sxs-lookup"><span data-stu-id="a9b57-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9b57-104">语法</span><span class="sxs-lookup"><span data-stu-id="a9b57-104">Syntax</span></span>  
  
```cpp  
HRESULT SetModuleProps (
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9b57-105">parameters</span><span class="sxs-lookup"><span data-stu-id="a9b57-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="a9b57-106">[在]Unicode 中的模块名称。</span><span class="sxs-lookup"><span data-stu-id="a9b57-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="a9b57-107">这只是文件名，而不是完整的路径名称。</span><span class="sxs-lookup"><span data-stu-id="a9b57-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9b57-108">要求</span><span class="sxs-lookup"><span data-stu-id="a9b57-108">Requirements</span></span>  
 <span data-ttu-id="a9b57-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a9b57-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9b57-110">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="a9b57-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9b57-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a9b57-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9b57-112">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9b57-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9b57-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9b57-113">See also</span></span>

- [<span data-ttu-id="a9b57-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="a9b57-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a9b57-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="a9b57-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
