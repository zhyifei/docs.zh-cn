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
ms.openlocfilehash: 489fa217744e41ccb5d27d088790131c15e1ee52
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177403"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="fd418-102">IMetaDataError::OnError 方法</span><span class="sxs-lookup"><span data-stu-id="fd418-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="fd418-103">提供元数据合并期间发生的错误通知。</span><span class="sxs-lookup"><span data-stu-id="fd418-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd418-104">语法</span><span class="sxs-lookup"><span data-stu-id="fd418-104">Syntax</span></span>  
  
```cpp  
HRESULT OnError (  
    [in] HRESULT   hrError,
    [in] mdToken   token  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd418-105">parameters</span><span class="sxs-lookup"><span data-stu-id="fd418-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="fd418-106">[在]HRESULT 错误值返回到调用方法。</span><span class="sxs-lookup"><span data-stu-id="fd418-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="fd418-107">[在]发生错误时正在合并的代码对象的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="fd418-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd418-108">要求</span><span class="sxs-lookup"><span data-stu-id="fd418-108">Requirements</span></span>  
 <span data-ttu-id="fd418-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fd418-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd418-110">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="fd418-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fd418-111">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fd418-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fd418-112">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd418-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd418-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd418-113">See also</span></span>

- [<span data-ttu-id="fd418-114">IMetaDataError 接口</span><span class="sxs-lookup"><span data-stu-id="fd418-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)
