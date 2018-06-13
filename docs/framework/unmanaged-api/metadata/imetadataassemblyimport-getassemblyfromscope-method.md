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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7322b4d0fce36f5dbef7e82f35cf9e2a1cae24a3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444325"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a><span data-ttu-id="fde97-102">IMetaDataAssemblyImport::GetAssemblyFromScope 方法</span><span class="sxs-lookup"><span data-stu-id="fde97-102">IMetaDataAssemblyImport::GetAssemblyFromScope Method</span></span>
<span data-ttu-id="fde97-103">获取一个指向程序集在当前范围内。</span><span class="sxs-lookup"><span data-stu-id="fde97-103">Gets a pointer to the assembly in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fde97-104">语法</span><span class="sxs-lookup"><span data-stu-id="fde97-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fde97-105">参数</span><span class="sxs-lookup"><span data-stu-id="fde97-105">Parameters</span></span>  
 `ptkAssembly`  
 <span data-ttu-id="fde97-106">[out]指向检索的`mdAssembly`标识的程序集的令牌。</span><span class="sxs-lookup"><span data-stu-id="fde97-106">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fde97-107">要求</span><span class="sxs-lookup"><span data-stu-id="fde97-107">Requirements</span></span>  
 <span data-ttu-id="fde97-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fde97-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fde97-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fde97-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fde97-110">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fde97-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fde97-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fde97-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fde97-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="fde97-112">See Also</span></span>  
 [<span data-ttu-id="fde97-113">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="fde97-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
