---
title: IMetaDataError::OnError 方法
ms.date: 03/30/2017
api_name:
- IMetaDataError.OnError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError::OnError
helpviewer_keywords:
- IMetaDataError::OnError method [.NET Framework metadata]
- OnError method, IMetaDataError interface [.NET Framework metadata]
ms.assetid: c1e744b8-a6fb-4d9c-a971-8babc875d8f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 011183d2f60e4abb967e5381d30a4c28e619e34c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479774"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="7c393-102">IMetaDataError::OnError 方法</span><span class="sxs-lookup"><span data-stu-id="7c393-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="7c393-103">提供元数据合并过程中发生的错误的通知。</span><span class="sxs-lookup"><span data-stu-id="7c393-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c393-104">语法</span><span class="sxs-lookup"><span data-stu-id="7c393-104">Syntax</span></span>  
  
```  
HRESULT OnError (  
    [in] HRESULT   hrError,   
    [in] mdToken   token  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c393-105">参数</span><span class="sxs-lookup"><span data-stu-id="7c393-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="7c393-106">[in]HRESULT 错误值返回给调用的方法。</span><span class="sxs-lookup"><span data-stu-id="7c393-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="7c393-107">[in]发生错误时合并代码对象的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="7c393-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c393-108">要求</span><span class="sxs-lookup"><span data-stu-id="7c393-108">Requirements</span></span>  
 <span data-ttu-id="7c393-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c393-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c393-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7c393-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c393-111">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7c393-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7c393-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c393-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c393-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c393-113">See also</span></span>
- [<span data-ttu-id="7c393-114">IMetaDataError 接口</span><span class="sxs-lookup"><span data-stu-id="7c393-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)
