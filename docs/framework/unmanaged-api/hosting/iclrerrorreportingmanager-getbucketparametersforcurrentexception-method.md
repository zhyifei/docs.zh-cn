---
title: ICLRErrorReportingManager::GetBucketParametersForCurrentException 方法
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3cb2a8d2a4e089d16b6c2129c165a9d8b6828f3f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141722"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="64a91-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="64a91-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="64a91-103">获取调用线程上的当前异常的 Watson 存储桶。</span><span class="sxs-lookup"><span data-stu-id="64a91-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="64a91-104">一个*存储桶*是与相同的代码缺陷相关的错误数据的集合。</span><span class="sxs-lookup"><span data-stu-id="64a91-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="64a91-105">*Watson*指一组技术，用于收集和分析与异常关联的数据。</span><span class="sxs-lookup"><span data-stu-id="64a91-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64a91-106">语法</span><span class="sxs-lookup"><span data-stu-id="64a91-106">Syntax</span></span>  
  
```  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64a91-107">参数</span><span class="sxs-lookup"><span data-stu-id="64a91-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="64a91-108">[out]一个指向[BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md)结构，其中包含异常的错误数据。</span><span class="sxs-lookup"><span data-stu-id="64a91-108">[out] A pointer to a [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64a91-109">要求</span><span class="sxs-lookup"><span data-stu-id="64a91-109">Requirements</span></span>  
 <span data-ttu-id="64a91-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="64a91-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64a91-111">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="64a91-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64a91-112">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="64a91-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64a91-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64a91-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64a91-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="64a91-114">See also</span></span>

- [<span data-ttu-id="64a91-115">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="64a91-115">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
