---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod 方法
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
ms.openlocfilehash: 879b9eac7cb6df06ffe4f994b505ea9cb2396d7f
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441833"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="83ff4-102">ISymUnmanagedAsyncMethod::GetKickoffMethod 方法</span><span class="sxs-lookup"><span data-stu-id="83ff4-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="83ff4-103">请参阅[DefineKickoffMethod 方法](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)。</span><span class="sxs-lookup"><span data-stu-id="83ff4-103">See [DefineKickoffMethod Method](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83ff4-104">语法</span><span class="sxs-lookup"><span data-stu-id="83ff4-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83ff4-105">参数</span><span class="sxs-lookup"><span data-stu-id="83ff4-105">Parameters</span></span>  
  
|<span data-ttu-id="83ff4-106">参数</span><span class="sxs-lookup"><span data-stu-id="83ff4-106">Parameter</span></span>|<span data-ttu-id="83ff4-107">说明</span><span class="sxs-lookup"><span data-stu-id="83ff4-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="83ff4-108">返回值</span><span class="sxs-lookup"><span data-stu-id="83ff4-108">Return Value</span></span>  
 <span data-ttu-id="83ff4-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="83ff4-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83ff4-110">要求</span><span class="sxs-lookup"><span data-stu-id="83ff4-110">Requirements</span></span>  
 <span data-ttu-id="83ff4-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="83ff4-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ff4-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83ff4-112">See also</span></span>

- [<span data-ttu-id="83ff4-113">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="83ff4-113">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
