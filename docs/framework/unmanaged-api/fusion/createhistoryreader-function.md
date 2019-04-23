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
ms.openlocfilehash: e438006d6424866514e73119c05e8fd69d7ba62e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132257"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="00ff7-102">CreateHistoryReader 函数</span><span class="sxs-lookup"><span data-stu-id="00ff7-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="00ff7-103">创建指定的文件的历史记录读取。</span><span class="sxs-lookup"><span data-stu-id="00ff7-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00ff7-104">语法</span><span class="sxs-lookup"><span data-stu-id="00ff7-104">Syntax</span></span>  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="00ff7-105">参数</span><span class="sxs-lookup"><span data-stu-id="00ff7-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="00ff7-106">[in]文件路径中。</span><span class="sxs-lookup"><span data-stu-id="00ff7-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="00ff7-107">[out]成功完成后，将包含历史记录读取器指向的指针。</span><span class="sxs-lookup"><span data-stu-id="00ff7-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00ff7-108">返回值</span><span class="sxs-lookup"><span data-stu-id="00ff7-108">Return Value</span></span>  
 <span data-ttu-id="00ff7-109">定义在 WinError.h，除了下表中描述的值之外，此方法将返回标准 COM 错误代码。</span><span class="sxs-lookup"><span data-stu-id="00ff7-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="00ff7-110">返回代码</span><span class="sxs-lookup"><span data-stu-id="00ff7-110">Return code</span></span>|<span data-ttu-id="00ff7-111">描述</span><span class="sxs-lookup"><span data-stu-id="00ff7-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="00ff7-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="00ff7-112">S_OK</span></span>|<span data-ttu-id="00ff7-113">指示该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="00ff7-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="00ff7-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="00ff7-114">E_INVALIDARG</span></span>|<span data-ttu-id="00ff7-115">指示`wzFilePath`或`ppHistoryReader`设置为 null 引用。</span><span class="sxs-lookup"><span data-stu-id="00ff7-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="00ff7-116">要求</span><span class="sxs-lookup"><span data-stu-id="00ff7-116">Requirements</span></span>  
 <span data-ttu-id="00ff7-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="00ff7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00ff7-118">**库：** Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="00ff7-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="00ff7-119">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00ff7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00ff7-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="00ff7-120">See also</span></span>

- [<span data-ttu-id="00ff7-121">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="00ff7-121">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
