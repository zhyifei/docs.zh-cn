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
ms.openlocfilehash: 7914257d167d0f54d3625d252076576e5e40296b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634931"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a><span data-ttu-id="f35ae-102">IMetaDataAssemblyImport::GetAssemblyFromScope 方法</span><span class="sxs-lookup"><span data-stu-id="f35ae-102">IMetaDataAssemblyImport::GetAssemblyFromScope Method</span></span>
<span data-ttu-id="f35ae-103">获取一个指向对程序集在当前范围内。</span><span class="sxs-lookup"><span data-stu-id="f35ae-103">Gets a pointer to the assembly in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f35ae-104">语法</span><span class="sxs-lookup"><span data-stu-id="f35ae-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f35ae-105">参数</span><span class="sxs-lookup"><span data-stu-id="f35ae-105">Parameters</span></span>  
 `ptkAssembly`  
 <span data-ttu-id="f35ae-106">[out]一个指向检索到的`mdAssembly`令牌，用于标识程序集。</span><span class="sxs-lookup"><span data-stu-id="f35ae-106">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f35ae-107">要求</span><span class="sxs-lookup"><span data-stu-id="f35ae-107">Requirements</span></span>  
 <span data-ttu-id="f35ae-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f35ae-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f35ae-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f35ae-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f35ae-110">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f35ae-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f35ae-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f35ae-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f35ae-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="f35ae-112">See also</span></span>
- [<span data-ttu-id="f35ae-113">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="f35ae-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
