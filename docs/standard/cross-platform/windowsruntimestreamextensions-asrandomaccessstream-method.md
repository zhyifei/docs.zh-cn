---
title: WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) 方法
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
api_name:
- System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream
api_location:
- System.Runtime.WindowsRuntime.dll
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d5dd2829a9a00f869af3d7f370f99361979b8106
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758789"
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a><span data-ttu-id="12ee6-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) 方法</span><span class="sxs-lookup"><span data-stu-id="12ee6-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) Method</span></span>

<span data-ttu-id="12ee6-103">[在 .NET Framework 4.5.1 和更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="12ee6-103">[Supported in the .NET Framework 4.5.1 and later versions]</span></span>

<span data-ttu-id="12ee6-104">将指定的流转换为随机访问流。</span><span class="sxs-lookup"><span data-stu-id="12ee6-104">Converts the specified stream to a random access stream.</span></span>

<span data-ttu-id="12ee6-105">**命名空间：**<xref:System.IO?displayProperty=nameWithType>
**程序集：** System.Runtime.WindowsRuntime （在 system.runtime.windowsruntime.dll 中）</span><span class="sxs-lookup"><span data-stu-id="12ee6-105">**Namespace:** <xref:System.IO?displayProperty=nameWithType>
**Assembly:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)</span></span>

## <a name="syntax"></a><span data-ttu-id="12ee6-106">语法</span><span class="sxs-lookup"><span data-stu-id="12ee6-106">Syntax</span></span>

```csharp
[CLSCompliantAttribute(false)]
public static IRandomAccessStream AsRandomAccessStream(Stream stream)
```

```vb
'Declaration
<ExtensionAttribute> _
<CLSCompliantAttribute(False)> _
Public Shared Function AsRandomAccessStream ( _
        stream As Stream) As IRandomAccessStream
```

## <a name="parameters"></a><span data-ttu-id="12ee6-107">参数</span><span class="sxs-lookup"><span data-stu-id="12ee6-107">Parameters</span></span>

`stream`

<span data-ttu-id="12ee6-108">类型：<xref:System.IO.Stream?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="12ee6-108">Type: <xref:System.IO.Stream?displayProperty=nameWithType></span></span>  
<span data-ttu-id="12ee6-109">要转换的流。</span><span class="sxs-lookup"><span data-stu-id="12ee6-109">The stream to convert.</span></span>

## <a name="return-value"></a><span data-ttu-id="12ee6-110">返回值</span><span class="sxs-lookup"><span data-stu-id="12ee6-110">Return Value</span></span>

<span data-ttu-id="12ee6-111">类型：<xref:Windows.Storage.Streams.RandomAccessStream></span><span class="sxs-lookup"><span data-stu-id="12ee6-111">Type: <xref:Windows.Storage.Streams.RandomAccessStream></span></span>  
<span data-ttu-id="12ee6-112">一个[!INCLUDE[wrt](../../../includes/wrt-md.md)]随机访问流，表示已转换的流。</span><span class="sxs-lookup"><span data-stu-id="12ee6-112">A [!INCLUDE[wrt](../../../includes/wrt-md.md)] random access stream, which represents the converted stream.</span></span>

## <a name="exceptions"></a><span data-ttu-id="12ee6-113">Exceptions</span><span class="sxs-lookup"><span data-stu-id="12ee6-113">Exceptions</span></span>

|<span data-ttu-id="12ee6-114">例外</span><span class="sxs-lookup"><span data-stu-id="12ee6-114">Exception</span></span>|<span data-ttu-id="12ee6-115">条件</span><span class="sxs-lookup"><span data-stu-id="12ee6-115">Condition</span></span>|
|---------------|---------------|
|<xref:System.NotSupportedException>|<span data-ttu-id="12ee6-116">要转换的流不支持查找。</span><span class="sxs-lookup"><span data-stu-id="12ee6-116">The stream to convert does not support seeking.</span></span>|

## <a name="remarks"></a><span data-ttu-id="12ee6-117">备注</span><span class="sxs-lookup"><span data-stu-id="12ee6-117">Remarks</span></span>

<span data-ttu-id="12ee6-118">此扩展方法仅在开发 Windows 应用商店应用时可用。</span><span class="sxs-lookup"><span data-stu-id="12ee6-118">This extension method is available only when you develop Windows Store apps.</span></span> <span data-ttu-id="12ee6-119">利用此方法，可以在 Windows 应用商店应用中轻松使用流。</span><span class="sxs-lookup"><span data-stu-id="12ee6-119">This method provides a convenient way of working with streams in Windows Store apps.</span></span> <span data-ttu-id="12ee6-120">要转换的 .NET Framework 流必须支持查找。</span><span class="sxs-lookup"><span data-stu-id="12ee6-120">The .NET Framework stream you want to convert must support seeking.</span></span> <span data-ttu-id="12ee6-121">有关更多信息，请参见 <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="12ee6-121">For more information, see the <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="12ee6-122">此 API 在 .NET Framework 4.5.1 和更高版本中受支持，但在 4.5 版中不受支持。</span><span class="sxs-lookup"><span data-stu-id="12ee6-122">This API is supported in the .NET Framework 4.5.1 and later versions, but not in version 4.5.</span></span>

## <a name="version-information"></a><span data-ttu-id="12ee6-123">版本信息</span><span class="sxs-lookup"><span data-stu-id="12ee6-123">Version Information</span></span>

<span data-ttu-id="12ee6-124">**适用于 Windows 应用商店应用程序的.NET**</span><span class="sxs-lookup"><span data-stu-id="12ee6-124">**.NET for Windows Store apps**</span></span>

<span data-ttu-id="12ee6-125">支持版本：Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="12ee6-125">Supported in: Windows 8.1</span></span>

## <a name="see-also"></a><span data-ttu-id="12ee6-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="12ee6-126">See also</span></span>

- [<span data-ttu-id="12ee6-127">如何：在 .NET Framework 流和 Windows 运行时流之间进行转换</span><span class="sxs-lookup"><span data-stu-id="12ee6-127">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)
