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
ms.openlocfilehash: ab864b251a989056bc34b2c7c6658964556f9ac1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449501"
---
# <a name="imetadatatablesgetnumtables-method"></a><span data-ttu-id="c64d4-102">IMetaDataTables::GetNumTables 方法</span><span class="sxs-lookup"><span data-stu-id="c64d4-102">IMetaDataTables::GetNumTables Method</span></span>
<span data-ttu-id="c64d4-103">获取当前 `IMetaDataTables` 实例的范围中的表数。</span><span class="sxs-lookup"><span data-stu-id="c64d4-103">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c64d4-104">语法</span><span class="sxs-lookup"><span data-stu-id="c64d4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNumTables (  
    [out]  ULONG   *pcTables  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c64d4-105">参数</span><span class="sxs-lookup"><span data-stu-id="c64d4-105">Parameters</span></span>  
 `pcTables`  
 <span data-ttu-id="c64d4-106">弄一个指针，指向当前实例范围中的表数。</span><span class="sxs-lookup"><span data-stu-id="c64d4-106">[out] A pointer to the number of tables in the current instance scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c64d4-107">要求</span><span class="sxs-lookup"><span data-stu-id="c64d4-107">Requirements</span></span>  
 <span data-ttu-id="c64d4-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c64d4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c64d4-109">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="c64d4-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c64d4-110">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c64d4-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c64d4-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c64d4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c64d4-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c64d4-112">See also</span></span>

- [<span data-ttu-id="c64d4-113">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="c64d4-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="c64d4-114">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="c64d4-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
