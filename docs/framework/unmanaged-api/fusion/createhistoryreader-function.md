---
title: "CreateHistoryReader 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateHistoryReader
api_location: fusion.dll
api_type: DLLExport
f1_keywords: CreateHistoryReader
helpviewer_keywords: CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4f4b09f592a27b7d3d25b2dbe13be7e261023bf5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="54bdc-102">CreateHistoryReader 函数</span><span class="sxs-lookup"><span data-stu-id="54bdc-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="54bdc-103">创建指定的文件历史记录读取器。</span><span class="sxs-lookup"><span data-stu-id="54bdc-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54bdc-104">语法</span><span class="sxs-lookup"><span data-stu-id="54bdc-104">Syntax</span></span>  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54bdc-105">参数</span><span class="sxs-lookup"><span data-stu-id="54bdc-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="54bdc-106">[in]文件路径中。</span><span class="sxs-lookup"><span data-stu-id="54bdc-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="54bdc-107">[out]在成功完成，包含指向历史记录读取器的指针。</span><span class="sxs-lookup"><span data-stu-id="54bdc-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54bdc-108">返回值</span><span class="sxs-lookup"><span data-stu-id="54bdc-108">Return Value</span></span>  
 <span data-ttu-id="54bdc-109">定义在 WinError.h，除了下表中描述的值，此方法将返回标准的 COM 错误代码。</span><span class="sxs-lookup"><span data-stu-id="54bdc-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="54bdc-110">返回代码</span><span class="sxs-lookup"><span data-stu-id="54bdc-110">Return code</span></span>|<span data-ttu-id="54bdc-111">描述</span><span class="sxs-lookup"><span data-stu-id="54bdc-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="54bdc-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="54bdc-112">S_OK</span></span>|<span data-ttu-id="54bdc-113">指示已成功完成的方法。</span><span class="sxs-lookup"><span data-stu-id="54bdc-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="54bdc-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="54bdc-114">E_INVALIDARG</span></span>|<span data-ttu-id="54bdc-115">指示`wzFilePath`或`ppHistoryReader`设置为 null 引用。</span><span class="sxs-lookup"><span data-stu-id="54bdc-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="54bdc-116">要求</span><span class="sxs-lookup"><span data-stu-id="54bdc-116">Requirements</span></span>  
 <span data-ttu-id="54bdc-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="54bdc-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54bdc-118">**库：**为 Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="54bdc-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="54bdc-119">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54bdc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54bdc-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54bdc-120">See Also</span></span>  
 [<span data-ttu-id="54bdc-121">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="54bdc-121">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
