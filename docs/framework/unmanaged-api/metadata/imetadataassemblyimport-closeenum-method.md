---
title: "IMetaDataAssemblyImport::CloseEnum 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.CloseEnum
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::CloseEnum
helpviewer_keywords:
- CloseEnum method, IMetaDataAssemblyImport interface [.NET Framework metadata]
- IMetaDataAssemblyImport::CloseEnum method [.NET Framework metadata]
ms.assetid: c9df4087-12b3-46d9-b075-9067dd7805df
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a239ee69bdcb8c7558a28c7b04a02adbf358be09
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportcloseenum-method"></a><span data-ttu-id="6d1c2-102">IMetaDataAssemblyImport::CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="6d1c2-102">IMetaDataAssemblyImport::CloseEnum Method</span></span>
<span data-ttu-id="6d1c2-103">释放指定的枚举实例的引用。</span><span class="sxs-lookup"><span data-stu-id="6d1c2-103">Releases a reference to the specified enumeration instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d1c2-104">语法</span><span class="sxs-lookup"><span data-stu-id="6d1c2-104">Syntax</span></span>  
  
```  
void CloseEnum (  
    [in] HCORENUM     hEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d1c2-105">参数</span><span class="sxs-lookup"><span data-stu-id="6d1c2-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="6d1c2-106">[in]要关闭的枚举实例。</span><span class="sxs-lookup"><span data-stu-id="6d1c2-106">[in] The enumeration instance to be closed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d1c2-107">要求</span><span class="sxs-lookup"><span data-stu-id="6d1c2-107">Requirements</span></span>  
 <span data-ttu-id="6d1c2-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6d1c2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d1c2-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6d1c2-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6d1c2-110">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6d1c2-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6d1c2-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d1c2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d1c2-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d1c2-112">See Also</span></span>  
 [<span data-ttu-id="6d1c2-113">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="6d1c2-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
