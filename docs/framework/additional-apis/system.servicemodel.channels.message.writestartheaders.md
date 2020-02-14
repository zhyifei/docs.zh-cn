---
title: WriteStartHeaders 方法（System.servicemodel. 通道）
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.WriteStartHeaders
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: c826e6a3b976e5705e9815586441e8a25b64f76e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214866"
---
# <a name="messagewritestartheaders-method"></a><span data-ttu-id="7f375-102">WriteStartHeaders 方法</span><span class="sxs-lookup"><span data-stu-id="7f375-102">Message.WriteStartHeaders Method</span></span>

<span data-ttu-id="7f375-103">通过调用 <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType> 方法，将开始标头写入 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="7f375-103">Writes the start header into an XML file by calling the <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType> method.</span></span>

```csharp
internal void WriteStartHeaders(XmlDictionaryWriter writer)
```

## <a name="parameters"></a><span data-ttu-id="7f375-104">parameters</span><span class="sxs-lookup"><span data-stu-id="7f375-104">Parameters</span></span>

- <span data-ttu-id="7f375-105">`writer` <xref:System.Xml.XmlDictionaryWriter></span><span class="sxs-lookup"><span data-stu-id="7f375-105">`writer` <xref:System.Xml.XmlDictionaryWriter></span></span>\
  <span data-ttu-id="7f375-106">用于将开始标头写入 XML 文件的编写器。</span><span class="sxs-lookup"><span data-stu-id="7f375-106">The writer that is used to write the start header into an XML file.</span></span>

## <a name="remarks"></a><span data-ttu-id="7f375-107">备注</span><span class="sxs-lookup"><span data-stu-id="7f375-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="7f375-108">`Message.WriteStartHeaders` 方法是内部的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="7f375-108">The `Message.WriteStartHeaders` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="7f375-109">在任何情况下，Microsoft 不支持在生产应用程序中使用此方法。</span><span class="sxs-lookup"><span data-stu-id="7f375-109">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="7f375-110">要求</span><span class="sxs-lookup"><span data-stu-id="7f375-110">Requirements</span></span>

<span data-ttu-id="7f375-111">**命名空间：** <xref:System.ServiceModel.Channels></span><span class="sxs-lookup"><span data-stu-id="7f375-111">**Namespace:** <xref:System.ServiceModel.Channels></span></span>

<span data-ttu-id="7f375-112">**程序集：** System.servicemodel .dll</span><span class="sxs-lookup"><span data-stu-id="7f375-112">**Assembly:** System.ServiceModel.dll</span></span>

<span data-ttu-id="7f375-113">**.NET Framework 版本：** 自3.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="7f375-113">**.NET Framework versions:** Available since 3.0.</span></span>
