---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 方法
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: ccf1287a1b0218e7f2560e1afbb0930c93b43263
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129174"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="26c57-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 方法</span><span class="sxs-lookup"><span data-stu-id="26c57-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="26c57-103">设置启动异步操作的启动方法。</span><span class="sxs-lookup"><span data-stu-id="26c57-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26c57-104">语法</span><span class="sxs-lookup"><span data-stu-id="26c57-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26c57-105">参数</span><span class="sxs-lookup"><span data-stu-id="26c57-105">Parameters</span></span>  
  
|<span data-ttu-id="26c57-106">参数</span><span class="sxs-lookup"><span data-stu-id="26c57-106">Parameter</span></span>|<span data-ttu-id="26c57-107">描述</span><span class="sxs-lookup"><span data-stu-id="26c57-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="26c57-108">返回值</span><span class="sxs-lookup"><span data-stu-id="26c57-108">Return Value</span></span>  
 <span data-ttu-id="26c57-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="26c57-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26c57-110">要求</span><span class="sxs-lookup"><span data-stu-id="26c57-110">Requirements</span></span>  
 <span data-ttu-id="26c57-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="26c57-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26c57-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="26c57-112">See also</span></span>

- [<span data-ttu-id="26c57-113">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="26c57-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
