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
ms.openlocfilehash: 80979f0424469bb1d4771ad6507bb8c9d5364ab4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108607"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="d2b13-102">CreateHistoryReader 函数</span><span class="sxs-lookup"><span data-stu-id="d2b13-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="d2b13-103">为指定的文件创建历史记录读取器。</span><span class="sxs-lookup"><span data-stu-id="d2b13-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2b13-104">语法</span><span class="sxs-lookup"><span data-stu-id="d2b13-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2b13-105">参数</span><span class="sxs-lookup"><span data-stu-id="d2b13-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="d2b13-106">中文件路径。</span><span class="sxs-lookup"><span data-stu-id="d2b13-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="d2b13-107">弄成功完成后，包含指向历史记录读取器的指针。</span><span class="sxs-lookup"><span data-stu-id="d2b13-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2b13-108">返回值</span><span class="sxs-lookup"><span data-stu-id="d2b13-108">Return Value</span></span>  
 <span data-ttu-id="d2b13-109">此方法返回 Winerror.h 中定义的标准 COM 错误代码，以及下表中描述的值。</span><span class="sxs-lookup"><span data-stu-id="d2b13-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="d2b13-110">返回代码</span><span class="sxs-lookup"><span data-stu-id="d2b13-110">Return code</span></span>|<span data-ttu-id="d2b13-111">描述</span><span class="sxs-lookup"><span data-stu-id="d2b13-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d2b13-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d2b13-112">S_OK</span></span>|<span data-ttu-id="d2b13-113">指示该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="d2b13-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="d2b13-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d2b13-114">E_INVALIDARG</span></span>|<span data-ttu-id="d2b13-115">指示 `wzFilePath` 或 `ppHistoryReader` 设置为空引用。</span><span class="sxs-lookup"><span data-stu-id="d2b13-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d2b13-116">要求</span><span class="sxs-lookup"><span data-stu-id="d2b13-116">Requirements</span></span>  
 <span data-ttu-id="d2b13-117">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d2b13-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2b13-118">**库：** 合成 .dll</span><span class="sxs-lookup"><span data-stu-id="d2b13-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="d2b13-119">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2b13-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2b13-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2b13-120">See also</span></span>

- [<span data-ttu-id="d2b13-121">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="d2b13-121">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
