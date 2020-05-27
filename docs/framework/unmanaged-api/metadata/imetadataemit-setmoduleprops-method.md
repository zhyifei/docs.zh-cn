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
ms.openlocfilehash: aee258c49e6726ebef990257456fd273b01b9ef0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007840"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="88aac-102">IMetaDataEmit::SetModuleProps 方法</span><span class="sxs-lookup"><span data-stu-id="88aac-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="88aac-103">更新对[IMetaDataEmit：:D efinemoduleref](imetadataemit-definemoduleref-method.md)之前调用定义的模块的引用。</span><span class="sxs-lookup"><span data-stu-id="88aac-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88aac-104">语法</span><span class="sxs-lookup"><span data-stu-id="88aac-104">Syntax</span></span>  
  
```cpp  
HRESULT SetModuleProps (
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88aac-105">参数</span><span class="sxs-lookup"><span data-stu-id="88aac-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="88aac-106">中Unicode 中的模块名称。</span><span class="sxs-lookup"><span data-stu-id="88aac-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="88aac-107">这只是文件名，而不是完整路径名称。</span><span class="sxs-lookup"><span data-stu-id="88aac-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88aac-108">要求</span><span class="sxs-lookup"><span data-stu-id="88aac-108">Requirements</span></span>  
 <span data-ttu-id="88aac-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="88aac-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88aac-110">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="88aac-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="88aac-111">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="88aac-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="88aac-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88aac-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88aac-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88aac-113">See also</span></span>

- [<span data-ttu-id="88aac-114">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="88aac-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="88aac-115">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="88aac-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
