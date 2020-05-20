---
title: ISymUnmanagedVariable::GetAddressField3 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type:
- apiref
ms.openlocfilehash: ff888d3e2b86efeea3f4e3d33528f731d85886bf
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615262"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="81720-102">ISymUnmanagedVariable::GetAddressField3 方法</span><span class="sxs-lookup"><span data-stu-id="81720-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="81720-103">获取此变量的第三个地址字段。</span><span class="sxs-lookup"><span data-stu-id="81720-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="81720-104">其含义取决于地址的类型。</span><span class="sxs-lookup"><span data-stu-id="81720-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81720-105">语法</span><span class="sxs-lookup"><span data-stu-id="81720-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81720-106">参数</span><span class="sxs-lookup"><span data-stu-id="81720-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="81720-107">弄指向的指针 `ULONG32` ，该指针接收第三个地址字段。</span><span class="sxs-lookup"><span data-stu-id="81720-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81720-108">返回值</span><span class="sxs-lookup"><span data-stu-id="81720-108">Return Value</span></span>  
 <span data-ttu-id="81720-109">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="81720-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81720-110">要求</span><span class="sxs-lookup"><span data-stu-id="81720-110">Requirements</span></span>  
 <span data-ttu-id="81720-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="81720-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81720-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81720-112">See also</span></span>

- [<span data-ttu-id="81720-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="81720-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="81720-114">GetAddressField1 方法</span><span class="sxs-lookup"><span data-stu-id="81720-114">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="81720-115">GetAddressField2 方法</span><span class="sxs-lookup"><span data-stu-id="81720-115">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="81720-116">GetAddressKind 方法</span><span class="sxs-lookup"><span data-stu-id="81720-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)
