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
ms.openlocfilehash: 0fc82ad87721c31337002dcfc5bbfdb9300afb31
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479735"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a><span data-ttu-id="f676d-102">IMetaDataAssemblyImport::GetAssemblyFromScope 方法</span><span class="sxs-lookup"><span data-stu-id="f676d-102">IMetaDataAssemblyImport::GetAssemblyFromScope Method</span></span>
<span data-ttu-id="f676d-103">获取一个指向对程序集在当前范围内。</span><span class="sxs-lookup"><span data-stu-id="f676d-103">Gets a pointer to the assembly in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f676d-104">语法</span><span class="sxs-lookup"><span data-stu-id="f676d-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f676d-105">参数</span><span class="sxs-lookup"><span data-stu-id="f676d-105">Parameters</span></span>  
 `ptkAssembly`  
 <span data-ttu-id="f676d-106">[out]一个指向检索到的`mdAssembly`令牌，用于标识程序集。</span><span class="sxs-lookup"><span data-stu-id="f676d-106">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f676d-107">要求</span><span class="sxs-lookup"><span data-stu-id="f676d-107">Requirements</span></span>  
 <span data-ttu-id="f676d-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f676d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f676d-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f676d-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f676d-110">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f676d-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f676d-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f676d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f676d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="f676d-112">See also</span></span>
- [<span data-ttu-id="f676d-113">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="f676d-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
