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
ms.openlocfilehash: 1c264bfd31f8cd31bacf2d194ddbd07338569294
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447165"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="22571-102">IMetaDataError 接口</span><span class="sxs-lookup"><span data-stu-id="22571-102">IMetaDataError Interface</span></span>
<span data-ttu-id="22571-103">提供用于元数据合并期间报告错误的回调机制。</span><span class="sxs-lookup"><span data-stu-id="22571-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22571-104">`IMetaDataError`由客户端必须实现接口。</span><span class="sxs-lookup"><span data-stu-id="22571-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22571-105">方法</span><span class="sxs-lookup"><span data-stu-id="22571-105">Methods</span></span>  
  
|<span data-ttu-id="22571-106">方法</span><span class="sxs-lookup"><span data-stu-id="22571-106">Method</span></span>|<span data-ttu-id="22571-107">描述</span><span class="sxs-lookup"><span data-stu-id="22571-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22571-108">OnError 方法</span><span class="sxs-lookup"><span data-stu-id="22571-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="22571-109">提供在元数据合并过程中发生的错误的通知。</span><span class="sxs-lookup"><span data-stu-id="22571-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="22571-110">要求</span><span class="sxs-lookup"><span data-stu-id="22571-110">Requirements</span></span>  
 <span data-ttu-id="22571-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="22571-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22571-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="22571-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="22571-113">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="22571-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="22571-114">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22571-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22571-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="22571-115">See Also</span></span>  
 [<span data-ttu-id="22571-116">元数据接口</span><span class="sxs-lookup"><span data-stu-id="22571-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
