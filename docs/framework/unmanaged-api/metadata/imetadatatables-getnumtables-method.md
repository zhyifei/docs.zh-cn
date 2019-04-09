---
title: IMetaDataTables::GetNumTables 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNumTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNumTables
helpviewer_keywords:
- GetNumTables method [.NET Framework metadata]
- IMetaDataTables::GetNumTables method [.NET Framework metadata]
ms.assetid: 8196f2a3-bbf2-45d3-a6cd-74502c356644
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b9ffd9ab9ddb95945744ecf210d0ae1d9d9812ec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125822"
---
# <a name="imetadatatablesgetnumtables-method"></a><span data-ttu-id="8d29a-102">IMetaDataTables::GetNumTables 方法</span><span class="sxs-lookup"><span data-stu-id="8d29a-102">IMetaDataTables::GetNumTables Method</span></span>
<span data-ttu-id="8d29a-103">获取在当前作用域中的表数`IMetaDataTables`实例。</span><span class="sxs-lookup"><span data-stu-id="8d29a-103">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d29a-104">语法</span><span class="sxs-lookup"><span data-stu-id="8d29a-104">Syntax</span></span>  
  
```  
HRESULT GetNumTables (  
    [out]  ULONG   *pcTables  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d29a-105">参数</span><span class="sxs-lookup"><span data-stu-id="8d29a-105">Parameters</span></span>  
 `pcTables`  
 <span data-ttu-id="8d29a-106">[out]指向当前实例作用域中的表数的指针。</span><span class="sxs-lookup"><span data-stu-id="8d29a-106">[out] A pointer to the number of tables in the current instance scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d29a-107">要求</span><span class="sxs-lookup"><span data-stu-id="8d29a-107">Requirements</span></span>  
 <span data-ttu-id="8d29a-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8d29a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d29a-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8d29a-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8d29a-110">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8d29a-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="8d29a-111">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="8d29a-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8d29a-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d29a-112">See also</span></span>

- [<span data-ttu-id="8d29a-113">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="8d29a-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="8d29a-114">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="8d29a-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
