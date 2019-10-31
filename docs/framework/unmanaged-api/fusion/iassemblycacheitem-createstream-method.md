---
title: IAssemblyCacheItem::CreateStream 方法
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
ms.openlocfilehash: 0660621f465f2ba3610e06bd1df38baa1bc5c907
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134474"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="e9a87-102">IAssemblyCacheItem::CreateStream 方法</span><span class="sxs-lookup"><span data-stu-id="e9a87-102">IAssemblyCacheItem::CreateStream Method</span></span>

<span data-ttu-id="e9a87-103">创建具有指定名称和格式的流。</span><span class="sxs-lookup"><span data-stu-id="e9a87-103">Creates a stream with the specified name and format.</span></span>

## <a name="syntax"></a><span data-ttu-id="e9a87-104">语法</span><span class="sxs-lookup"><span data-stu-id="e9a87-104">Syntax</span></span>

```cpp
HRESULT CreateStream (
    [in]  DWORD dwFlags,
    [in]  LPCWSTR pszStreamName,
    [in]  DWORD dwFormat,
    [in]  DWORD dwFormatFlags,
    [out] IStream **ppIStream,
    [in, optional] ULARGE_INTEGER *puliMaxSize
);
```

## <a name="parameters"></a><span data-ttu-id="e9a87-105">参数</span><span class="sxs-lookup"><span data-stu-id="e9a87-105">Parameters</span></span>

`dwFlags`\
<span data-ttu-id="e9a87-106">中在合成 .idl 中定义的标志。</span><span class="sxs-lookup"><span data-stu-id="e9a87-106">[in] Flags defined in Fusion.idl.</span></span>

`pszStreamName`\
<span data-ttu-id="e9a87-107">中要创建的流的名称。</span><span class="sxs-lookup"><span data-stu-id="e9a87-107">[in] The name of the stream to be created.</span></span>

`dwFormat`\
<span data-ttu-id="e9a87-108">中要进行流处理的文件的格式。</span><span class="sxs-lookup"><span data-stu-id="e9a87-108">[in] The format of the file to be streamed.</span></span>

`dwFormatFlags`\
<span data-ttu-id="e9a87-109">中在合成 .idl 中定义的特定于格式的标志。</span><span class="sxs-lookup"><span data-stu-id="e9a87-109">[in] Format-specific flags defined in Fusion.idl.</span></span>

`ppIStream`\
<span data-ttu-id="e9a87-110">弄指向返回的[IStream](/windows/desktop/api/objidl/nn-objidl-istream)实例的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="e9a87-110">[out] A pointer to the address of the returned [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instance.</span></span>

`puliMaxSize`\
<span data-ttu-id="e9a87-111">[in，可选]`ppIStream`引用的流的最大大小。</span><span class="sxs-lookup"><span data-stu-id="e9a87-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>

## <a name="requirements"></a><span data-ttu-id="e9a87-112">要求</span><span class="sxs-lookup"><span data-stu-id="e9a87-112">Requirements</span></span>

<span data-ttu-id="e9a87-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e9a87-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="e9a87-114">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="e9a87-114">**Header:** Fusion.h</span></span>

<span data-ttu-id="e9a87-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9a87-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e9a87-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9a87-116">See also</span></span>

- [<span data-ttu-id="e9a87-117">IAssemblyCacheItem 接口</span><span class="sxs-lookup"><span data-stu-id="e9a87-117">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
