---
title: ISymUnmanagedVariable::GetAddressField2 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField2
helpviewer_keywords:
- GetAddressField2 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField2 method [.NET Framework debugging]
ms.assetid: 1f25b294-72b6-4882-a49b-6c9d364b6008
topic_type:
- apiref
ms.openlocfilehash: 6256d052780b1c610e61267be2517954d722a42d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610595"
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a><span data-ttu-id="df596-102">ISymUnmanagedVariable::GetAddressField2 方法</span><span class="sxs-lookup"><span data-stu-id="df596-102">ISymUnmanagedVariable::GetAddressField2 Method</span></span>
<span data-ttu-id="df596-103">获取此变量的第二个地址字段。</span><span class="sxs-lookup"><span data-stu-id="df596-103">Gets the second address field for this variable.</span></span> <span data-ttu-id="df596-104">其含义取决于地址的类型。</span><span class="sxs-lookup"><span data-stu-id="df596-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df596-105">语法</span><span class="sxs-lookup"><span data-stu-id="df596-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df596-106">参数</span><span class="sxs-lookup"><span data-stu-id="df596-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="df596-107">弄指向的指针 `ULONG32` ，该指针接收第二个地址字段。</span><span class="sxs-lookup"><span data-stu-id="df596-107">[out] A pointer to a `ULONG32` that receives the second address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df596-108">返回值</span><span class="sxs-lookup"><span data-stu-id="df596-108">Return Value</span></span>  
 <span data-ttu-id="df596-109">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="df596-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df596-110">要求</span><span class="sxs-lookup"><span data-stu-id="df596-110">Requirements</span></span>  
 <span data-ttu-id="df596-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="df596-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df596-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df596-112">See also</span></span>

- [<span data-ttu-id="df596-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="df596-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="df596-114">GetAddressField1 方法</span><span class="sxs-lookup"><span data-stu-id="df596-114">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="df596-115">GetAddressField3 方法</span><span class="sxs-lookup"><span data-stu-id="df596-115">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="df596-116">GetAddressKind 方法</span><span class="sxs-lookup"><span data-stu-id="df596-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)
