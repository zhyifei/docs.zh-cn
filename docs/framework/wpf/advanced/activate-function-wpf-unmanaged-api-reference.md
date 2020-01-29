---
title: 激活函数 WPF 非托管 API 参考
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 9c0a235e8b94294ab82da88e43f7446c29739c12
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734508"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a>Activate 函数（WPF 非托管 API 参考）

此 API 支持 Windows Presentation Foundation （WPF）基础结构，不应在代码中直接使用。

由用于 Windows 管理的 Windows Presentation Foundation （WPF）基础结构使用。

## <a name="syntax"></a>구문

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a>매개 변수

`pParameters`\
指向窗口的激活参数的指针。

`ppInner`\
指向单个元素缓冲区的地址的指针，该缓冲区包含指向 <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> 对象的指针。

## <a name="requirements"></a>요구 사항

**平台：** 请参阅[.NET Framework 系统要求](../../get-started/system-requirements.md)。

**.DLL**

在 .NET Framework 3.0 和3.5： PresentationHostDLL

在 .NET Framework 4 及更高版本中： PresentationHost_v0400 .dll

**.NET Framework 版本：** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]

## <a name="see-also"></a>另请参阅

- [F 관리되지 않는 API 참조](wpf-unmanaged-api-reference.md)
