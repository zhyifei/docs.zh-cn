---
title: MemoryStream. InternalGetOriginAndLength 方法（System.IO）
author: mairaw
ms.author: mairaw
ms.date: 11/19/2019
topic_type:
- apiref
api_name:
- System.IO.MemoryStream.InternalGetOriginAndLength
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: d2bfa087fe2fb247f963cfa687c27056363d5696
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74284041"
---
# <a name="memorystreaminternalgetoriginandlength-method"></a><span data-ttu-id="6748c-102">MemoryStream. InternalGetOriginAndLength 方法</span><span class="sxs-lookup"><span data-stu-id="6748c-102">MemoryStream.InternalGetOriginAndLength method</span></span>

<span data-ttu-id="6748c-103">获取内存流的源的内部值和长度。</span><span class="sxs-lookup"><span data-stu-id="6748c-103">Gets the internal values of origin and length of the memory stream.</span></span>

```csharp
internal void InternalGetOriginAndLength(out int origin, out int length)
```

## <a name="parameters"></a><span data-ttu-id="6748c-104">参数</span><span class="sxs-lookup"><span data-stu-id="6748c-104">Parameters</span></span>

- <span data-ttu-id="6748c-105">`origin` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="6748c-105">`origin` <xref:System.Int32></span></span>\
  <span data-ttu-id="6748c-106">此方法返回时，创建新 <xref:System.IO.MemoryStream> 对象时指定的字节数组的偏移量。</span><span class="sxs-lookup"><span data-stu-id="6748c-106">When this method returns, the offset of the byte array specified when creating a new <xref:System.IO.MemoryStream> object.</span></span> <span data-ttu-id="6748c-107">如果字节数组由 <xref:System.IO.MemoryStream>创建，则包含0。</span><span class="sxs-lookup"><span data-stu-id="6748c-107">Contains 0 if the byte array was created by <xref:System.IO.MemoryStream>.</span></span>

- <span data-ttu-id="6748c-108">`length` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="6748c-108">`length` <xref:System.Int32></span></span>\
  <span data-ttu-id="6748c-109">此方法返回时，为内存流中的字节数。</span><span class="sxs-lookup"><span data-stu-id="6748c-109">When this method returns, the number of bytes within the memory stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="6748c-110">备注</span><span class="sxs-lookup"><span data-stu-id="6748c-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="6748c-111">`MemoryStream.InternalGetOriginAndLength` 方法是内部的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="6748c-111">The `MemoryStream.InternalGetOriginAndLength` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="6748c-112">在任何情况下，Microsoft 不支持在生产应用程序中使用此方法。</span><span class="sxs-lookup"><span data-stu-id="6748c-112">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="6748c-113">要求</span><span class="sxs-lookup"><span data-stu-id="6748c-113">Requirements</span></span>

<span data-ttu-id="6748c-114">**命名空间：** <xref:System.IO></span><span class="sxs-lookup"><span data-stu-id="6748c-114">**Namespace:** <xref:System.IO></span></span>

<span data-ttu-id="6748c-115">**Assembly：** mscorlib （在 mscorlib.dll 中）</span><span class="sxs-lookup"><span data-stu-id="6748c-115">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="6748c-116">**.NET Framework 版本：** 自2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="6748c-116">**.NET Framework versions:** Available since 2.0.</span></span>
