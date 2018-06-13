---
title: CreateHistoryReader 函数
ms.date: 03/30/2017
api_name:
- CreateHistoryReader
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateHistoryReader
helpviewer_keywords:
- CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f3a3cc21dbbcfa99ddcecb534bd2e337da005597
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431173"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="7457b-102">CreateHistoryReader 函数</span><span class="sxs-lookup"><span data-stu-id="7457b-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="7457b-103">创建指定的文件历史记录读取器。</span><span class="sxs-lookup"><span data-stu-id="7457b-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7457b-104">语法</span><span class="sxs-lookup"><span data-stu-id="7457b-104">Syntax</span></span>  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7457b-105">参数</span><span class="sxs-lookup"><span data-stu-id="7457b-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="7457b-106">[in]文件路径中。</span><span class="sxs-lookup"><span data-stu-id="7457b-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="7457b-107">[out]在成功完成，包含指向历史记录读取器的指针。</span><span class="sxs-lookup"><span data-stu-id="7457b-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7457b-108">返回值</span><span class="sxs-lookup"><span data-stu-id="7457b-108">Return Value</span></span>  
 <span data-ttu-id="7457b-109">定义在 WinError.h，除了下表中描述的值，此方法将返回标准的 COM 错误代码。</span><span class="sxs-lookup"><span data-stu-id="7457b-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="7457b-110">返回代码</span><span class="sxs-lookup"><span data-stu-id="7457b-110">Return code</span></span>|<span data-ttu-id="7457b-111">描述</span><span class="sxs-lookup"><span data-stu-id="7457b-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="7457b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="7457b-112">S_OK</span></span>|<span data-ttu-id="7457b-113">指示已成功完成的方法。</span><span class="sxs-lookup"><span data-stu-id="7457b-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="7457b-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="7457b-114">E_INVALIDARG</span></span>|<span data-ttu-id="7457b-115">指示`wzFilePath`或`ppHistoryReader`设置为 null 引用。</span><span class="sxs-lookup"><span data-stu-id="7457b-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7457b-116">要求</span><span class="sxs-lookup"><span data-stu-id="7457b-116">Requirements</span></span>  
 <span data-ttu-id="7457b-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7457b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7457b-118">**库：** 为 Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="7457b-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="7457b-119">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7457b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7457b-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="7457b-120">See Also</span></span>  
 [<span data-ttu-id="7457b-121">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="7457b-121">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
