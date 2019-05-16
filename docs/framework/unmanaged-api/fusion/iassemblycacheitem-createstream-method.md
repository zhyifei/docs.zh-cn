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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a98273307003485202d8c12d5c27fda04ff5a0ae
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65629881"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="189eb-102">IAssemblyCacheItem::CreateStream 方法</span><span class="sxs-lookup"><span data-stu-id="189eb-102">IAssemblyCacheItem::CreateStream Method</span></span>

<span data-ttu-id="189eb-103">创建具有指定的名称和格式的流。</span><span class="sxs-lookup"><span data-stu-id="189eb-103">Creates a stream with the specified name and format.</span></span>

## <a name="syntax"></a><span data-ttu-id="189eb-104">语法</span><span class="sxs-lookup"><span data-stu-id="189eb-104">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="189eb-105">参数</span><span class="sxs-lookup"><span data-stu-id="189eb-105">Parameters</span></span>

`dwFlags`\
<span data-ttu-id="189eb-106">[in]包括的标志。</span><span class="sxs-lookup"><span data-stu-id="189eb-106">[in] Flags defined in Fusion.idl.</span></span>

`pszStreamName`\
<span data-ttu-id="189eb-107">[in]若要创建的流的名称。</span><span class="sxs-lookup"><span data-stu-id="189eb-107">[in] The name of the stream to be created.</span></span>

`dwFormat`\
<span data-ttu-id="189eb-108">[in]要进行流处理的文件的格式。</span><span class="sxs-lookup"><span data-stu-id="189eb-108">[in] The format of the file to be streamed.</span></span>

`dwFormatFlags`\
<span data-ttu-id="189eb-109">[in]包括特定于格式的标志。</span><span class="sxs-lookup"><span data-stu-id="189eb-109">[in] Format-specific flags defined in Fusion.idl.</span></span>

`ppIStream`\
<span data-ttu-id="189eb-110">[out]指向所返回的地址的指针[IStream](/windows/desktop/api/objidl/nn-objidl-istream)实例。</span><span class="sxs-lookup"><span data-stu-id="189eb-110">[out] A pointer to the address of the returned [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instance.</span></span>

`puliMaxSize`\
<span data-ttu-id="189eb-111">[in，可选]引用的流的最大大小`ppIStream`。</span><span class="sxs-lookup"><span data-stu-id="189eb-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>

## <a name="requirements"></a><span data-ttu-id="189eb-112">要求</span><span class="sxs-lookup"><span data-stu-id="189eb-112">Requirements</span></span>

<span data-ttu-id="189eb-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="189eb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="189eb-114">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="189eb-114">**Header:** Fusion.h</span></span>

<span data-ttu-id="189eb-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="189eb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="189eb-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="189eb-116">See also</span></span>

- [<span data-ttu-id="189eb-117">IAssemblyCacheItem 接口</span><span class="sxs-lookup"><span data-stu-id="189eb-117">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
