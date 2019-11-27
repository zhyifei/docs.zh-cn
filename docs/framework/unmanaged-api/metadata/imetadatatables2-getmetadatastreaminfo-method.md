---
title: IMetaDataTables2::GetMetaDataStreamInfo 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStreamInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type:
- apiref
ms.openlocfilehash: 279e34689169d31ad89772e90155e7f50bdbac08
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426218"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="697fb-102">IMetaDataTables2::GetMetaDataStreamInfo 方法</span><span class="sxs-lookup"><span data-stu-id="697fb-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>
<span data-ttu-id="697fb-103">获取指定索引处的元数据流的名称、大小和内容。</span><span class="sxs-lookup"><span data-stu-id="697fb-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="697fb-104">语法</span><span class="sxs-lookup"><span data-stu-id="697fb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="697fb-105">参数</span><span class="sxs-lookup"><span data-stu-id="697fb-105">Parameters</span></span>  
 `ix`  
 <span data-ttu-id="697fb-106">中请求的元数据流的索引。</span><span class="sxs-lookup"><span data-stu-id="697fb-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="697fb-107">弄指向流名称的指针。</span><span class="sxs-lookup"><span data-stu-id="697fb-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="697fb-108">弄指向元数据流的指针。</span><span class="sxs-lookup"><span data-stu-id="697fb-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="697fb-109">弄`ppv`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="697fb-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="697fb-110">要求</span><span class="sxs-lookup"><span data-stu-id="697fb-110">Requirements</span></span>  
 <span data-ttu-id="697fb-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="697fb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="697fb-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="697fb-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="697fb-113">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="697fb-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="697fb-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="697fb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="697fb-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="697fb-115">See also</span></span>

- [<span data-ttu-id="697fb-116">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="697fb-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
- [<span data-ttu-id="697fb-117">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="697fb-117">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
