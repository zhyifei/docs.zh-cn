---
title: .NET 中的序列化
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: e05d358452a247b0d071f78d19c0bf721502899a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018029"
---
# <a name="serialization-in-net"></a><span data-ttu-id="2ce9d-102">.NET 中的序列化</span><span class="sxs-lookup"><span data-stu-id="2ce9d-102">Serialization in .NET</span></span>
<span data-ttu-id="2ce9d-103">序列化是将对象状态转换为可保持或传输的形式的过程。</span><span class="sxs-lookup"><span data-stu-id="2ce9d-103">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="2ce9d-104">序列化的补集是反序列化，后者将流转换为对象。</span><span class="sxs-lookup"><span data-stu-id="2ce9d-104">The complement of serialization is deserialization, which converts a stream into an object.</span></span> <span data-ttu-id="2ce9d-105">这两个过程一起保证数据易于存储和传输。</span><span class="sxs-lookup"><span data-stu-id="2ce9d-105">Together, these processes allow data to be easily stored and transferred.</span></span>  
  
<span data-ttu-id="2ce9d-106">.NET 具有两种序列化技术：</span><span class="sxs-lookup"><span data-stu-id="2ce9d-106">.NET features two serialization technologies:</span></span>  
  
- <span data-ttu-id="2ce9d-107">二进制序列化保持类型保真，这对于多次调用应用程序时保持对象状态非常有用。</span><span class="sxs-lookup"><span data-stu-id="2ce9d-107">Binary serialization preserves type fidelity, which is useful for preserving the state of an object between different invocations of an application.</span></span> <span data-ttu-id="2ce9d-108">例如，通过将对象序列化到剪贴板，可在不同的应用程序之间共享对象。</span><span class="sxs-lookup"><span data-stu-id="2ce9d-108">For example, you can share an object between different applications by serializing it to the Clipboard.</span></span> <span data-ttu-id="2ce9d-109">您可以将对象序列化到流、磁盘、内存和网络等。</span><span class="sxs-lookup"><span data-stu-id="2ce9d-109">You can serialize an object to a stream, to a disk, to memory, over the network, and so forth.</span></span> <span data-ttu-id="2ce9d-110">远程处理使用序列化，“按值”在计算机或应用程序域之间传递对象。</span><span class="sxs-lookup"><span data-stu-id="2ce9d-110">Remoting uses serialization to pass objects "by value" from one computer or application domain to another.</span></span>  
  
- <span data-ttu-id="2ce9d-111">XML 序列化只序列化公共属性和字段，并且不保持类型保真。</span><span class="sxs-lookup"><span data-stu-id="2ce9d-111">XML serialization serializes only public properties and fields and does not preserve type fidelity.</span></span> <span data-ttu-id="2ce9d-112">当您希望提供或使用数据而不限制使用该数据的应用程序时，这一点非常有用。</span><span class="sxs-lookup"><span data-stu-id="2ce9d-112">This is useful when you want to provide or consume data without restricting the application that uses the data.</span></span> <span data-ttu-id="2ce9d-113">由于 XML 是开放式的标准，因此它对于通过 Web 共享数据来说是一个理想选择。</span><span class="sxs-lookup"><span data-stu-id="2ce9d-113">Because XML is an open standard, it is an attractive choice for sharing data across the Web.</span></span> <span data-ttu-id="2ce9d-114">SOAP 同样是开放式的标准，这使它也成为一个理想选择。</span><span class="sxs-lookup"><span data-stu-id="2ce9d-114">SOAP is likewise an open standard, which makes it an attractive choice.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ce9d-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="2ce9d-115">In This Section</span></span>  
[<span data-ttu-id="2ce9d-116">序列化帮助主题</span><span class="sxs-lookup"><span data-stu-id="2ce9d-116">Serialization How-to Topics</span></span>](../../../docs/standard/serialization/serialization-how-to-topics.md)  
<span data-ttu-id="2ce9d-117">列出指向此节中包含的“如何”主题的链接。</span><span class="sxs-lookup"><span data-stu-id="2ce9d-117">Lists links to How-to topics contained in this section.</span></span>
  
[<span data-ttu-id="2ce9d-118">二进制序列化</span><span class="sxs-lookup"><span data-stu-id="2ce9d-118">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)  
<span data-ttu-id="2ce9d-119">描述随公共语言运行库一起提供的二进制序列化机制。</span><span class="sxs-lookup"><span data-stu-id="2ce9d-119">Describes the binary serialization mechanism that is included with the common language runtime.</span></span>

[<span data-ttu-id="2ce9d-120">XML 和 SOAP 序列化</span><span class="sxs-lookup"><span data-stu-id="2ce9d-120">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
<span data-ttu-id="2ce9d-121">描述随公共语言运行库一起提供的 XML 和 SOAP 序列化机制。</span><span class="sxs-lookup"><span data-stu-id="2ce9d-121">Describes the XML and SOAP serialization mechanism that is included with the common language runtime.</span></span>

[<span data-ttu-id="2ce9d-122">序列化工具</span><span class="sxs-lookup"><span data-stu-id="2ce9d-122">Serialization Tools</span></span>](../../../docs/standard/serialization/serialization-tools.md)  
<span data-ttu-id="2ce9d-123">这些工具可帮助开发序列化代码。</span><span class="sxs-lookup"><span data-stu-id="2ce9d-123">These tools help develop serialization code.</span></span>

[<span data-ttu-id="2ce9d-124">序列化示例</span><span class="sxs-lookup"><span data-stu-id="2ce9d-124">Serialization Samples</span></span>](../../../docs/standard/serialization/serialization-samples.md)  
<span data-ttu-id="2ce9d-125">这些示例演示了如何进行序列化。</span><span class="sxs-lookup"><span data-stu-id="2ce9d-125">The samples demonstrate how to do serialization.</span></span>

## <a name="reference"></a><span data-ttu-id="2ce9d-126">参考</span><span class="sxs-lookup"><span data-stu-id="2ce9d-126">Reference</span></span>
<span data-ttu-id="2ce9d-127"><xref:System.Runtime.Serialization> 包含可用于序列化和反序列化对象的类。</span><span class="sxs-lookup"><span data-stu-id="2ce9d-127"><xref:System.Runtime.Serialization> Contains classes that can be used for serializing and deserializing objects.</span></span>
  
<xref:System.Xml.Serialization>  
<span data-ttu-id="2ce9d-128">包含可用于将对象序列化为 XML 格式的文档或流的类。</span><span class="sxs-lookup"><span data-stu-id="2ce9d-128">Contains classes that can be used to serialize objects into XML format documents or streams.</span></span>