---
title: IMetaDataAssemblyImport::CloseEnum 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::CloseEnum
helpviewer_keywords:
- CloseEnum method, IMetaDataAssemblyImport interface [.NET Framework metadata]
- IMetaDataAssemblyImport::CloseEnum method [.NET Framework metadata]
ms.assetid: c9df4087-12b3-46d9-b075-9067dd7805df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cc0a4f52747cbc88a26f4b9aaff6642b6c1d62f1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090013"
---
# <a name="imetadataassemblyimportcloseenum-method"></a><span data-ttu-id="c039c-102">IMetaDataAssemblyImport::CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="c039c-102">IMetaDataAssemblyImport::CloseEnum Method</span></span>
<span data-ttu-id="c039c-103">释放指定的枚举实例的引用。</span><span class="sxs-lookup"><span data-stu-id="c039c-103">Releases a reference to the specified enumeration instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c039c-104">语法</span><span class="sxs-lookup"><span data-stu-id="c039c-104">Syntax</span></span>  
  
```  
void CloseEnum (  
    [in] HCORENUM     hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c039c-105">参数</span><span class="sxs-lookup"><span data-stu-id="c039c-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="c039c-106">[in]要关闭的枚举实例。</span><span class="sxs-lookup"><span data-stu-id="c039c-106">[in] The enumeration instance to be closed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c039c-107">要求</span><span class="sxs-lookup"><span data-stu-id="c039c-107">Requirements</span></span>  
 <span data-ttu-id="c039c-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c039c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c039c-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c039c-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c039c-110">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c039c-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="c039c-111">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="c039c-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c039c-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="c039c-112">See also</span></span>

- [<span data-ttu-id="c039c-113">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="c039c-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
