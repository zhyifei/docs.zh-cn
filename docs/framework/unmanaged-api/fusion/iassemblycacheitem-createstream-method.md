---
title: "IAssemblyCacheItem::CreateStream 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCacheItem.CreateStream
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAsssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8dfdb34e10c6bc47ce13230ee03ef024cb15b07b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="0255d-102">IAssemblyCacheItem::CreateStream 方法</span><span class="sxs-lookup"><span data-stu-id="0255d-102">IAssemblyCacheItem::CreateStream Method</span></span>
<span data-ttu-id="0255d-103">具有指定的名称和格式创建一个流。</span><span class="sxs-lookup"><span data-stu-id="0255d-103">Creates a stream with the specified name and format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0255d-104">语法</span><span class="sxs-lookup"><span data-stu-id="0255d-104">Syntax</span></span>  
  
```  
HRESULT CreateStream (  
    [in]  DWORD dwFlags,  
    [in]  LPCWSTR pszStreamName,  
    [in]  DWORD dwFormat,  
    [in]  DWORD dwFormatFlags,  
    [out] IStream **ppIStream,  
    [in, optional] ULARGE_INTEGER *puliMaxSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0255d-105">参数</span><span class="sxs-lookup"><span data-stu-id="0255d-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="0255d-106">[in]在包括中定义的标志。</span><span class="sxs-lookup"><span data-stu-id="0255d-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszStreamName`  
 <span data-ttu-id="0255d-107">[in]要创建的流名称。</span><span class="sxs-lookup"><span data-stu-id="0255d-107">[in] The name of the stream to be created.</span></span>  
  
 `dwFormat`  
 <span data-ttu-id="0255d-108">[in]要进行流处理的文件的格式。</span><span class="sxs-lookup"><span data-stu-id="0255d-108">[in] The format of the file to be streamed.</span></span>  
  
 `dwFormatFlags`  
 <span data-ttu-id="0255d-109">[in]在包括中定义的特定格式的标志。</span><span class="sxs-lookup"><span data-stu-id="0255d-109">[in] Format-specific flags defined in Fusion.idl.</span></span>  
  
 `ppIStream`  
 <span data-ttu-id="0255d-110">[out]返回的地址指针<xref:IStream>实例。</span><span class="sxs-lookup"><span data-stu-id="0255d-110">[out] A pointer to the address of the returned <xref:IStream> instance.</span></span>  
  
 `puliMaxSize`  
 <span data-ttu-id="0255d-111">[in，可选]引用的流的最大大小`ppIStream`。</span><span class="sxs-lookup"><span data-stu-id="0255d-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0255d-112">要求</span><span class="sxs-lookup"><span data-stu-id="0255d-112">Requirements</span></span>  
 <span data-ttu-id="0255d-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0255d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0255d-114">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="0255d-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0255d-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0255d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0255d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0255d-116">See Also</span></span>  
 [<span data-ttu-id="0255d-117">IAssemblyCacheItem 接口</span><span class="sxs-lookup"><span data-stu-id="0255d-117">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
