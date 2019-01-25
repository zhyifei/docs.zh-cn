---
title: IMetaDataError 接口
ms.date: 03/30/2017
api_name:
- IMetaDataError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError
helpviewer_keywords:
- IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fe2f683ae46d1ee6205f97536976a358e86fc53d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720374"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="fe03d-102">IMetaDataError 接口</span><span class="sxs-lookup"><span data-stu-id="fe03d-102">IMetaDataError Interface</span></span>
<span data-ttu-id="fe03d-103">提供回调机制，用于在元数据合并期间报告错误。</span><span class="sxs-lookup"><span data-stu-id="fe03d-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe03d-104">`IMetaDataError`接口必须由客户端实现。</span><span class="sxs-lookup"><span data-stu-id="fe03d-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fe03d-105">方法</span><span class="sxs-lookup"><span data-stu-id="fe03d-105">Methods</span></span>  
  
|<span data-ttu-id="fe03d-106">方法</span><span class="sxs-lookup"><span data-stu-id="fe03d-106">Method</span></span>|<span data-ttu-id="fe03d-107">描述</span><span class="sxs-lookup"><span data-stu-id="fe03d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fe03d-108">OnError 方法</span><span class="sxs-lookup"><span data-stu-id="fe03d-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="fe03d-109">提供元数据合并过程中发生的错误的通知。</span><span class="sxs-lookup"><span data-stu-id="fe03d-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fe03d-110">要求</span><span class="sxs-lookup"><span data-stu-id="fe03d-110">Requirements</span></span>  
 <span data-ttu-id="fe03d-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fe03d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe03d-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fe03d-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe03d-113">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fe03d-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fe03d-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe03d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe03d-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe03d-115">See also</span></span>
- [<span data-ttu-id="fe03d-116">元数据接口</span><span class="sxs-lookup"><span data-stu-id="fe03d-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
