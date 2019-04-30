---
title: IMetaDataTables::GetString 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8fed98521c0609ebd8b5f65885d69c77814e9e85
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042284"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="de341-102">IMetaDataTables::GetString 方法</span><span class="sxs-lookup"><span data-stu-id="de341-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="de341-103">获取当前引用作用域中从表的列的指定索引处的字符串。</span><span class="sxs-lookup"><span data-stu-id="de341-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de341-104">语法</span><span class="sxs-lookup"><span data-stu-id="de341-104">Syntax</span></span>  
  
```  
HRESULT GetString (   
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de341-105">参数</span><span class="sxs-lookup"><span data-stu-id="de341-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="de341-106">[in]若要开始搜索下一个值处的索引。</span><span class="sxs-lookup"><span data-stu-id="de341-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="de341-107">[out]指向返回的字符串值的指针指向的指针。</span><span class="sxs-lookup"><span data-stu-id="de341-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de341-108">要求</span><span class="sxs-lookup"><span data-stu-id="de341-108">Requirements</span></span>  
 <span data-ttu-id="de341-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="de341-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de341-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="de341-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="de341-111">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="de341-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="de341-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de341-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de341-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="de341-113">See also</span></span>

- [<span data-ttu-id="de341-114">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="de341-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="de341-115">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="de341-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
