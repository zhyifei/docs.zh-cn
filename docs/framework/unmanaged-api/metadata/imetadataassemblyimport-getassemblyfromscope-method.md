---
title: IMetaDataAssemblyImport::GetAssemblyFromScope 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope method [.NET Framework metadata]
- GetAssemblyFromScope method [.NET Framework metadata]
ms.assetid: 0b437f70-561d-48c7-abe0-0cb9ace10c08
topic_type:
- apiref
ms.openlocfilehash: adcaac02526c7d72ffb75ba6c7552632173032cf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009036"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a><span data-ttu-id="39025-102">IMetaDataAssemblyImport::GetAssemblyFromScope 方法</span><span class="sxs-lookup"><span data-stu-id="39025-102">IMetaDataAssemblyImport::GetAssemblyFromScope Method</span></span>
<span data-ttu-id="39025-103">获取指向当前范围内的程序集的指针。</span><span class="sxs-lookup"><span data-stu-id="39025-103">Gets a pointer to the assembly in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39025-104">语法</span><span class="sxs-lookup"><span data-stu-id="39025-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39025-105">参数</span><span class="sxs-lookup"><span data-stu-id="39025-105">Parameters</span></span>  
 `ptkAssembly`  
 <span data-ttu-id="39025-106">弄指向用于标识程序集的检索到的标记的指针 `mdAssembly` 。</span><span class="sxs-lookup"><span data-stu-id="39025-106">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39025-107">要求</span><span class="sxs-lookup"><span data-stu-id="39025-107">Requirements</span></span>  
 <span data-ttu-id="39025-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="39025-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39025-109">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="39025-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="39025-110">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="39025-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="39025-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39025-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39025-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39025-112">See also</span></span>

- [<span data-ttu-id="39025-113">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="39025-113">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
