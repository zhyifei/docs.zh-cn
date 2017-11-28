---
title: "ICorDebugType::GetRank 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetRank
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetRank
helpviewer_keywords:
- GetRank method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetRank method [.NET Framework debugging]
ms.assetid: 72d3d927-f590-4f2d-8f60-448f3dfb96af
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: eb27cc774ccd199151059049bbcc9c4e17a4de59
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypegetrank-method"></a><span data-ttu-id="567ac-102">ICorDebugType::GetRank 方法</span><span class="sxs-lookup"><span data-stu-id="567ac-102">ICorDebugType::GetRank Method</span></span>
<span data-ttu-id="567ac-103">获取一个数组类型中的维度数。</span><span class="sxs-lookup"><span data-stu-id="567ac-103">Gets the number of dimensions in an array type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="567ac-104">语法</span><span class="sxs-lookup"><span data-stu-id="567ac-104">Syntax</span></span>  
  
```  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="567ac-105">参数</span><span class="sxs-lookup"><span data-stu-id="567ac-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="567ac-106">[out]指向的维度数的指针。</span><span class="sxs-lookup"><span data-stu-id="567ac-106">[out] A pointer to the number of dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="567ac-107">要求</span><span class="sxs-lookup"><span data-stu-id="567ac-107">Requirements</span></span>  
 <span data-ttu-id="567ac-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="567ac-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="567ac-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="567ac-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="567ac-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="567ac-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="567ac-111">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="567ac-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
