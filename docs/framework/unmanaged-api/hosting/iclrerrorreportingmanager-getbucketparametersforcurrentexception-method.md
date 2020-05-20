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
ms.openlocfilehash: 969d74933e908674225684a2e77d5c4804b86122
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615639"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="7ab5b-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="7ab5b-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="7ab5b-103">获取调用线程上的当前异常的 Watson 存储桶。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="7ab5b-104">*存储桶*是与相同代码缺陷相关的错误数据的集合。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="7ab5b-105">*Watson*指的是一组用于收集和分析与异常相关联的数据的技术。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ab5b-106">语法</span><span class="sxs-lookup"><span data-stu-id="7ab5b-106">Syntax</span></span>  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ab5b-107">参数</span><span class="sxs-lookup"><span data-stu-id="7ab5b-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="7ab5b-108">弄指向[BucketParameters](bucketparameters-structure.md)结构的指针，该结构包含异常的错误数据。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-108">[out] A pointer to a [BucketParameters](bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ab5b-109">要求</span><span class="sxs-lookup"><span data-stu-id="7ab5b-109">Requirements</span></span>  
 <span data-ttu-id="7ab5b-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ab5b-111">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7ab5b-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7ab5b-112">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="7ab5b-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ab5b-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ab5b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ab5b-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ab5b-114">See also</span></span>

- [<span data-ttu-id="7ab5b-115">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="7ab5b-115">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
