---
title: 序列化-.NET
ms.date: 09/02/2019
helpviewer_keywords:
- JSON serialization
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: e6db24326c79ab6509b253c45c27f87a2aacd73c
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053350"
---
# <a name="serialization-in-net"></a><span data-ttu-id="73b2d-102">.NET 中的序列化</span><span class="sxs-lookup"><span data-stu-id="73b2d-102">Serialization in .NET</span></span>

<span data-ttu-id="73b2d-103">序列化是将对象状态转换为可保持或传输的形式的过程。</span><span class="sxs-lookup"><span data-stu-id="73b2d-103">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="73b2d-104">序列化的补集是反序列化，后者将流转换为对象。</span><span class="sxs-lookup"><span data-stu-id="73b2d-104">The complement of serialization is deserialization, which converts a stream into an object.</span></span> <span data-ttu-id="73b2d-105">这些进程一起允许存储和传输数据。</span><span class="sxs-lookup"><span data-stu-id="73b2d-105">Together, these processes allow data to be stored and transferred.</span></span>  
  
<span data-ttu-id="73b2d-106">.NET 具有以下序列化技术：</span><span class="sxs-lookup"><span data-stu-id="73b2d-106">.NET features the following serialization technologies:</span></span>  
  
- <span data-ttu-id="73b2d-107">[二进制序列化](binary-serialization.md)保存类型保真，这对于在不同的应用程序调用之间保留对象的状态非常有用。</span><span class="sxs-lookup"><span data-stu-id="73b2d-107">[Binary serialization](binary-serialization.md) preserves type fidelity, which is useful for preserving the state of an object between different invocations of an application.</span></span> <span data-ttu-id="73b2d-108">例如，通过将对象序列化到剪贴板，可在不同的应用程序之间共享对象。</span><span class="sxs-lookup"><span data-stu-id="73b2d-108">For example, you can share an object between different applications by serializing it to the Clipboard.</span></span> <span data-ttu-id="73b2d-109">您可以将对象序列化到流、磁盘、内存和网络等。</span><span class="sxs-lookup"><span data-stu-id="73b2d-109">You can serialize an object to a stream, to a disk, to memory, over the network, and so forth.</span></span> <span data-ttu-id="73b2d-110">远程处理使用序列化，“按值”在计算机或应用程序域之间传递对象。</span><span class="sxs-lookup"><span data-stu-id="73b2d-110">Remoting uses serialization to pass objects "by value" from one computer or application domain to another.</span></span>  
  
- <span data-ttu-id="73b2d-111">[XML 和 SOAP 序列化](xml-and-soap-serialization.md)只会序列化公共属性和字段，并且不会保留类型保真。</span><span class="sxs-lookup"><span data-stu-id="73b2d-111">[XML and SOAP serialization](xml-and-soap-serialization.md) serializes only public properties and fields and does not preserve type fidelity.</span></span> <span data-ttu-id="73b2d-112">当您希望提供或使用数据而不限制使用该数据的应用程序时，这一点非常有用。</span><span class="sxs-lookup"><span data-stu-id="73b2d-112">This is useful when you want to provide or consume data without restricting the application that uses the data.</span></span> <span data-ttu-id="73b2d-113">由于 XML 是开放式的标准，因此它对于通过 Web 共享数据来说是一个理想选择。</span><span class="sxs-lookup"><span data-stu-id="73b2d-113">Because XML is an open standard, it is an attractive choice for sharing data across the Web.</span></span> <span data-ttu-id="73b2d-114">SOAP 同样是开放式的标准，这使它也成为一个理想选择。</span><span class="sxs-lookup"><span data-stu-id="73b2d-114">SOAP is likewise an open standard, which makes it an attractive choice.</span></span>  
  
- <span data-ttu-id="73b2d-115">[JSON 序列化](system-text-json-overview.md)只序列化公共属性，不会保留类型保真。</span><span class="sxs-lookup"><span data-stu-id="73b2d-115">[JSON serialization](system-text-json-overview.md) serializes only public properties and does not preserve type fidelity.</span></span> <span data-ttu-id="73b2d-116">JSON 是一种开放式标准，是一种用于在 web 上共享数据的极具吸引力的选择。</span><span class="sxs-lookup"><span data-stu-id="73b2d-116">JSON is an open standard that is an attractive choice for sharing data across the web.</span></span>

## <a name="reference"></a><span data-ttu-id="73b2d-117">参考</span><span class="sxs-lookup"><span data-stu-id="73b2d-117">Reference</span></span>

<xref:System.Runtime.Serialization>  
<span data-ttu-id="73b2d-118">包含可用于序列化和反序列化对象的类。</span><span class="sxs-lookup"><span data-stu-id="73b2d-118">Contains classes that can be used for serializing and deserializing objects.</span></span>
  
<xref:System.Xml.Serialization>  
<span data-ttu-id="73b2d-119">包含可用于将对象序列化为 XML 格式的文档或流的类。</span><span class="sxs-lookup"><span data-stu-id="73b2d-119">Contains classes that can be used to serialize objects into XML format documents or streams.</span></span>

<xref:System.Text.Json>  
<span data-ttu-id="73b2d-120">包含可用于将对象序列化为 JSON 格式文档或流的类。</span><span class="sxs-lookup"><span data-stu-id="73b2d-120">Contains classes that can be used to serialize objects into JSON format documents or streams.</span></span>
