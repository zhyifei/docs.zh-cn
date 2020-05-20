---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 方法
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: c35455fc679d79d56814a9c2f026ec395e944f24
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441716"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="cf6bd-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 方法</span><span class="sxs-lookup"><span data-stu-id="cf6bd-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="cf6bd-103">设置启动异步操作的启动方法。</span><span class="sxs-lookup"><span data-stu-id="cf6bd-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf6bd-104">语法</span><span class="sxs-lookup"><span data-stu-id="cf6bd-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf6bd-105">参数</span><span class="sxs-lookup"><span data-stu-id="cf6bd-105">Parameters</span></span>  
  
|<span data-ttu-id="cf6bd-106">参数</span><span class="sxs-lookup"><span data-stu-id="cf6bd-106">Parameter</span></span>|<span data-ttu-id="cf6bd-107">说明</span><span class="sxs-lookup"><span data-stu-id="cf6bd-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="cf6bd-108">返回值</span><span class="sxs-lookup"><span data-stu-id="cf6bd-108">Return Value</span></span>  
 <span data-ttu-id="cf6bd-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="cf6bd-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf6bd-110">要求</span><span class="sxs-lookup"><span data-stu-id="cf6bd-110">Requirements</span></span>  
 <span data-ttu-id="cf6bd-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="cf6bd-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf6bd-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf6bd-112">See also</span></span>

- [<span data-ttu-id="cf6bd-113">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="cf6bd-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
