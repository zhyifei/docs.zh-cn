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
ms.openlocfilehash: babe098b16729cfcd41b48075a49b9ae9be7dfdc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117178"
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="24efe-102">IMetaDataTables::GetBlob 方法</span><span class="sxs-lookup"><span data-stu-id="24efe-102">IMetaDataTables::GetBlob Method</span></span>
<span data-ttu-id="24efe-103">获取一个指向二进制大型对象 (BLOB) 中的指定的列索引处。</span><span class="sxs-lookup"><span data-stu-id="24efe-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24efe-104">语法</span><span class="sxs-lookup"><span data-stu-id="24efe-104">Syntax</span></span>  
  
```  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24efe-105">参数</span><span class="sxs-lookup"><span data-stu-id="24efe-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="24efe-106">[in]要从其中获取的内存地址`ppData`。</span><span class="sxs-lookup"><span data-stu-id="24efe-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="24efe-107">[out]指向的大小，以字节为单位的`ppData`。</span><span class="sxs-lookup"><span data-stu-id="24efe-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="24efe-108">[out]检索到的二进制数据的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="24efe-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24efe-109">要求</span><span class="sxs-lookup"><span data-stu-id="24efe-109">Requirements</span></span>  
 <span data-ttu-id="24efe-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="24efe-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24efe-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="24efe-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="24efe-112">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="24efe-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="24efe-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="24efe-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="24efe-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="24efe-114">See also</span></span>

- [<span data-ttu-id="24efe-115">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="24efe-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="24efe-116">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="24efe-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
