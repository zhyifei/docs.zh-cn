---
title: XmlReader.createSqlReader 方法（系统.Xml）
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: 7bd2ef5158516acede47f73f9937d06159bc16c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155734"
---
# <a name="xmlreadercreatesqlreader-method"></a><span data-ttu-id="ca5a1-102">XmlReader.CreateSqlReader 方法</span><span class="sxs-lookup"><span data-stu-id="ca5a1-102">XmlReader.CreateSqlReader Method</span></span>

<span data-ttu-id="ca5a1-103">使用指定的流、设置和用于分析的上下文信息创建一个新的 <xref:System.Xml.XmlReader> 实例。</span><span class="sxs-lookup"><span data-stu-id="ca5a1-103">Creates a new <xref:System.Xml.XmlReader> instance using the specified stream, settings, and context information for parsing.</span></span>

```csharp
internal static XmlReader CreateSqlReader(Stream input,
  XmlReaderSettings settings, XmlParserContext inputContext)
```

## <a name="parameters"></a><span data-ttu-id="ca5a1-104">parameters</span><span class="sxs-lookup"><span data-stu-id="ca5a1-104">Parameters</span></span>

- <span data-ttu-id="ca5a1-105">`input` <xref:System.IO.Stream></span><span class="sxs-lookup"><span data-stu-id="ca5a1-105">`input` <xref:System.IO.Stream></span></span>  
  <span data-ttu-id="ca5a1-106">包含 XML 数据的流。</span><span class="sxs-lookup"><span data-stu-id="ca5a1-106">The stream that contains the XML data.</span></span>

- <span data-ttu-id="ca5a1-107">`settings` <xref:System.Xml.XmlReaderSettings></span><span class="sxs-lookup"><span data-stu-id="ca5a1-107">`settings` <xref:System.Xml.XmlReaderSettings></span></span>  
  <span data-ttu-id="ca5a1-108">新 <xref:System.Xml.XmlReader> 实例的设置。</span><span class="sxs-lookup"><span data-stu-id="ca5a1-108">The settings for the new <xref:System.Xml.XmlReader> instance.</span></span> <span data-ttu-id="ca5a1-109">此值可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="ca5a1-109">This value can be `null`.</span></span>

- <span data-ttu-id="ca5a1-110">`inputContext` <xref:System.Xml.XmlParserContext></span><span class="sxs-lookup"><span data-stu-id="ca5a1-110">`inputContext` <xref:System.Xml.XmlParserContext></span></span>  
  <span data-ttu-id="ca5a1-111">分析 XML 片段所需的上下文信息.</span><span class="sxs-lookup"><span data-stu-id="ca5a1-111">The context information required to parse the XML fragment.</span></span> <span data-ttu-id="ca5a1-112">此值可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="ca5a1-112">This value can be `null`.</span></span>

## <a name="returns"></a><span data-ttu-id="ca5a1-113">返回</span><span class="sxs-lookup"><span data-stu-id="ca5a1-113">Returns</span></span>

<xref:System.Xml.XmlReader>  
<span data-ttu-id="ca5a1-114">一个用于读取数据流中所含数据的对象。</span><span class="sxs-lookup"><span data-stu-id="ca5a1-114">An object that is used to read the XML data in the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="ca5a1-115">备注</span><span class="sxs-lookup"><span data-stu-id="ca5a1-115">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="ca5a1-116">该方法`XmlReader.CreateSqlReader`是内部的，不用于直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="ca5a1-116">The `XmlReader.CreateSqlReader` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="ca5a1-117">在任何情况下，Microsoft 都不支持在生产应用程序中使用此方法。</span><span class="sxs-lookup"><span data-stu-id="ca5a1-117">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="ca5a1-118">要求</span><span class="sxs-lookup"><span data-stu-id="ca5a1-118">Requirements</span></span>

<span data-ttu-id="ca5a1-119">**命名空间：**<xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="ca5a1-119">**Namespace:** <xref:System.Xml></span></span>

<span data-ttu-id="ca5a1-120">**装配：** 系统.Xml.dll</span><span class="sxs-lookup"><span data-stu-id="ca5a1-120">**Assembly:** System.Xml.dll</span></span>

<span data-ttu-id="ca5a1-121">**.NET 框架版本：** 自 2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="ca5a1-121">**.NET Framework versions:** Available since 2.0.</span></span>
