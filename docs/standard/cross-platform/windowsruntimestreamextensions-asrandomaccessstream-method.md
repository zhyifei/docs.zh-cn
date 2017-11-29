---
title: "WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
api_name: System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream
api_location: System.Runtime.WindowsRuntime.dll
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: be93ddc0f3bf0a5079f31bfa0ff5caa882342c37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a><span data-ttu-id="18b4b-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) 方法</span><span class="sxs-lookup"><span data-stu-id="18b4b-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) Method</span></span>
<span data-ttu-id="18b4b-103">[在 .NET Framework 4.5.1 和更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="18b4b-103">[Supported in the .NET Framework 4.5.1 and later versions]</span></span>  
  
 <span data-ttu-id="18b4b-104">将指定的流转换为随机访问流。</span><span class="sxs-lookup"><span data-stu-id="18b4b-104">Converts the specified stream to a random access stream.</span></span>  
  
 <span data-ttu-id="18b4b-105">**Namespace:**<xref:System.IO?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="18b4b-105">**Namespace:** <xref:System.IO?displayProperty=nameWithType></span></span>  
 <span data-ttu-id="18b4b-106">**程序集：** System.Runtime.WindowsRuntime （在 system.runtime.windowsruntime.dll 中）</span><span class="sxs-lookup"><span data-stu-id="18b4b-106">**Assembly:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18b4b-107">语法</span><span class="sxs-lookup"><span data-stu-id="18b4b-107">Syntax</span></span>  
  
```csharp  
[CLSCompliantAttribute(false)]  
public static  IRandomAccessStream AsRandomAccessStream(Stream stream)  
```  
  
```vb  
'Declaration  
<ExtensionAttribute> _  
<CLSCompliantAttribute(False)> _  
Public Shared Function AsRandomAccessStream ( _  
        stream As Stream) As IRandomAccessStream  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18b4b-108">参数</span><span class="sxs-lookup"><span data-stu-id="18b4b-108">Parameters</span></span>  
 `stream`  
  
 <span data-ttu-id="18b4b-109">类型：<xref:System.IO.Stream?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="18b4b-109">Type: <xref:System.IO.Stream?displayProperty=nameWithType></span></span>  
<span data-ttu-id="18b4b-110">要转换的流。</span><span class="sxs-lookup"><span data-stu-id="18b4b-110">The stream to convert.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18b4b-111">返回值</span><span class="sxs-lookup"><span data-stu-id="18b4b-111">Return Value</span></span>  
 <span data-ttu-id="18b4b-112">类型： [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)</span><span class="sxs-lookup"><span data-stu-id="18b4b-112">Type: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)</span></span>  
<span data-ttu-id="18b4b-113">A[!INCLUDE[wrt](../../../includes/wrt-md.md)]随机访问流，它表示转换后的流。</span><span class="sxs-lookup"><span data-stu-id="18b4b-113">A [!INCLUDE[wrt](../../../includes/wrt-md.md)] random access stream, which represents the converted stream.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="18b4b-114">异常</span><span class="sxs-lookup"><span data-stu-id="18b4b-114">Exceptions</span></span>  
  
|<span data-ttu-id="18b4b-115">例外</span><span class="sxs-lookup"><span data-stu-id="18b4b-115">Exception</span></span>|<span data-ttu-id="18b4b-116">条件</span><span class="sxs-lookup"><span data-stu-id="18b4b-116">Condition</span></span>|  
|---------------|---------------|  
|<xref:System.NotSupportedException>|<span data-ttu-id="18b4b-117">要转换的流不支持查找。</span><span class="sxs-lookup"><span data-stu-id="18b4b-117">The stream to convert does not support seeking.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18b4b-118">备注</span><span class="sxs-lookup"><span data-stu-id="18b4b-118">Remarks</span></span>  
 <span data-ttu-id="18b4b-119">此扩展方法仅在开发 Windows 应用商店应用时可用。</span><span class="sxs-lookup"><span data-stu-id="18b4b-119">This extension method is available only when you develop Windows Store apps.</span></span> <span data-ttu-id="18b4b-120">利用此方法，可以在 Windows 应用商店应用中轻松使用流。</span><span class="sxs-lookup"><span data-stu-id="18b4b-120">This method provides a convenient way of working with streams in Windows Store apps.</span></span> <span data-ttu-id="18b4b-121">要转换的 .NET Framework 流必须支持查找。</span><span class="sxs-lookup"><span data-stu-id="18b4b-121">The .NET Framework stream you want to convert must support seeking.</span></span> <span data-ttu-id="18b4b-122">有关更多信息，请参见 <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="18b4b-122">For more information, see the <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType> method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="18b4b-123">此 API 在 .NET Framework 4.5.1 和更高版本中受支持，但在 4.5 版中不受支持。</span><span class="sxs-lookup"><span data-stu-id="18b4b-123">This API is supported in the .NET Framework 4.5.1 and later versions, but not in version 4.5.</span></span>  
  
## <a name="version-information"></a><span data-ttu-id="18b4b-124">版本信息</span><span class="sxs-lookup"><span data-stu-id="18b4b-124">Version Information</span></span>  
 <span data-ttu-id="18b4b-125">**适用于 Windows 应用商店应用的.NET**</span><span class="sxs-lookup"><span data-stu-id="18b4b-125">**.NET for Windows Store apps**</span></span>  
  
 <span data-ttu-id="18b4b-126">受支持：Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="18b4b-126">Supported in: Windows 8.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18b4b-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18b4b-127">See Also</span></span>  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions`  
 [<span data-ttu-id="18b4b-128">如何：在 .NET Framework 流和 Windows 运行时流之间进行转换</span><span class="sxs-lookup"><span data-stu-id="18b4b-128">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)
