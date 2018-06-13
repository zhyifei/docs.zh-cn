---
title: IMetaDataTables::GetBlob 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlob
helpviewer_keywords:
- GetBlob method [.NET Framework metadata]
- IMetaDataTables::GetBlob method [.NET Framework metadata]
ms.assetid: 94667c1c-6d58-4aa7-b74e-530b11e2a276
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 743fb1c77e2dd74487a7498be25ea23b4919032a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447293"
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="17da5-102">IMetaDataTables::GetBlob 方法</span><span class="sxs-lookup"><span data-stu-id="17da5-102">IMetaDataTables::GetBlob Method</span></span>
<span data-ttu-id="17da5-103">获取一个指向二进制大型对象 (BLOB) 指定的列索引处。</span><span class="sxs-lookup"><span data-stu-id="17da5-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17da5-104">语法</span><span class="sxs-lookup"><span data-stu-id="17da5-104">Syntax</span></span>  
  
```  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="17da5-105">参数</span><span class="sxs-lookup"><span data-stu-id="17da5-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="17da5-106">[in]要从其中获取的内存地址`ppData`。</span><span class="sxs-lookup"><span data-stu-id="17da5-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="17da5-107">[out]大小，以字节为单位，指向的指针的`ppData`。</span><span class="sxs-lookup"><span data-stu-id="17da5-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="17da5-108">[out]检索到二进制数据的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="17da5-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17da5-109">要求</span><span class="sxs-lookup"><span data-stu-id="17da5-109">Requirements</span></span>  
 <span data-ttu-id="17da5-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="17da5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17da5-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="17da5-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="17da5-112">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="17da5-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="17da5-113">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17da5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17da5-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="17da5-114">See Also</span></span>  
 [<span data-ttu-id="17da5-115">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="17da5-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="17da5-116">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="17da5-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
