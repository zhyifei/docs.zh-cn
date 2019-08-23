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
ms.openlocfilehash: 277b93267f0537c8e499a8d8f3b456c4396a975c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966341"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="dc747-102">IMetaDataError 接口</span><span class="sxs-lookup"><span data-stu-id="dc747-102">IMetaDataError Interface</span></span>
<span data-ttu-id="dc747-103">提供用于在元数据合并期间报告错误的回调机制。</span><span class="sxs-lookup"><span data-stu-id="dc747-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc747-104">`IMetaDataError`接口必须由客户端实现。</span><span class="sxs-lookup"><span data-stu-id="dc747-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dc747-105">方法</span><span class="sxs-lookup"><span data-stu-id="dc747-105">Methods</span></span>  
  
|<span data-ttu-id="dc747-106">方法</span><span class="sxs-lookup"><span data-stu-id="dc747-106">Method</span></span>|<span data-ttu-id="dc747-107">描述</span><span class="sxs-lookup"><span data-stu-id="dc747-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dc747-108">OnError 方法</span><span class="sxs-lookup"><span data-stu-id="dc747-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="dc747-109">提供在元数据合并期间发生的错误的通知。</span><span class="sxs-lookup"><span data-stu-id="dc747-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dc747-110">要求</span><span class="sxs-lookup"><span data-stu-id="dc747-110">Requirements</span></span>  
 <span data-ttu-id="dc747-111">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dc747-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc747-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="dc747-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dc747-113">**类库**用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="dc747-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dc747-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc747-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc747-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="dc747-115">See also</span></span>

- [<span data-ttu-id="dc747-116">元数据接口</span><span class="sxs-lookup"><span data-stu-id="dc747-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
