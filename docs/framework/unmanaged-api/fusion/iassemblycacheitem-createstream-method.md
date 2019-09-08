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
ms.openlocfilehash: 5af7dc4e1694b66fc4a5ce37e515c71e9fa3db49
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796739"
---
# <a name="iassemblycacheitemcreatestream-method"></a>IAssemblyCacheItem::CreateStream 方法

创建具有指定名称和格式的流。

## <a name="syntax"></a>语法

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

## <a name="parameters"></a>参数

`dwFlags`\
中在合成 .idl 中定义的标志。

`pszStreamName`\
中要创建的流的名称。

`dwFormat`\
中要进行流处理的文件的格式。

`dwFormatFlags`\
中在合成 .idl 中定义的特定于格式的标志。

`ppIStream`\
弄指向返回的[IStream](/windows/desktop/api/objidl/nn-objidl-istream)实例的地址的指针。

`puliMaxSize`\
[in，可选]引用的流的最大大小`ppIStream`。

## <a name="requirements"></a>要求

**适用**请参阅[系统需求](../../get-started/system-requirements.md)。

**标头：** 合成。h

**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>请参阅

- [IAssemblyCacheItem 接口](iassemblycacheitem-interface.md)
