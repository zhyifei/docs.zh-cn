---
title: "ISymUnmanagedSourceServerModule::GetSourceServerData 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedSourceServerModule.GetSourceServerData
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedSourceServerModule::GetSourceServerData
helpviewer_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData method [.NET Framework debugging]
- GetSourceServerData method [.NET Framework debugging]
ms.assetid: 20bdf8ff-2d15-4c64-8950-6888f642d6c0
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f75ffbe3980a6c7587912a1cf099ef87888132a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="30878-102">ISymUnmanagedSourceServerModule::GetSourceServerData 方法</span><span class="sxs-lookup"><span data-stu-id="30878-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="30878-103">返回模块的源服务器数据。</span><span class="sxs-lookup"><span data-stu-id="30878-103">Returns the source server data for the module.</span></span> <span data-ttu-id="30878-104">调用方必须使用释放资源`CoTaskMemFree`。</span><span class="sxs-lookup"><span data-stu-id="30878-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30878-105">语法</span><span class="sxs-lookup"><span data-stu-id="30878-105">Syntax</span></span>  
  
```  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,   
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30878-106">参数</span><span class="sxs-lookup"><span data-stu-id="30878-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="30878-107">[out]指向的指针`ULONG32`接收大小，以字节为单位，源服务器数据。</span><span class="sxs-lookup"><span data-stu-id="30878-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="30878-108">[out]指向返回的指针`pDataByteCount`值。</span><span class="sxs-lookup"><span data-stu-id="30878-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30878-109">返回值</span><span class="sxs-lookup"><span data-stu-id="30878-109">Return Value</span></span>  
 <span data-ttu-id="30878-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="30878-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30878-111">惠?</span><span class="sxs-lookup"><span data-stu-id="30878-111">Requirements</span></span>  
 <span data-ttu-id="30878-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="30878-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30878-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="30878-113">See Also</span></span>  
 [<span data-ttu-id="30878-114">ISymUnmanagedSourceServerModule 接口</span><span class="sxs-lookup"><span data-stu-id="30878-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
