---
title: 如何：反序列化对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deserializing objects
- objects, deserializing steps
ms.assetid: 287129c8-035a-4fea-b7b3-4790057ca076
ms.openlocfilehash: 6da8ec2b78066cd251e4ad492afd2d9d37f7b965
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863234"
---
# <a name="how-to-deserialize-an-object"></a><span data-ttu-id="649c4-102">如何：反序列化对象</span><span class="sxs-lookup"><span data-stu-id="649c4-102">How to: Deserialize an Object</span></span>
<span data-ttu-id="649c4-103">当您反序列化对象时，传输格式确定您将创建流还是文件对象。</span><span class="sxs-lookup"><span data-stu-id="649c4-103">When you deserialize an object, the transport format determines whether you will create a stream or file object.</span></span> <span data-ttu-id="649c4-104">确定了传输格式之后，就可以根据需要调用 <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> 或 <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="649c4-104">After the transport format is determined, you can call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> or <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> methods, as required.</span></span>  
  
### <a name="to-deserialize-an-object"></a><span data-ttu-id="649c4-105">反序列化对象</span><span class="sxs-lookup"><span data-stu-id="649c4-105">To deserialize an object</span></span>  
  
1.  <span data-ttu-id="649c4-106">使用要反序列化的对象的类型构造 <xref:System.Xml.Serialization.XmlSerializer>。</span><span class="sxs-lookup"><span data-stu-id="649c4-106">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object to deserialize.</span></span>  
  
2.  <span data-ttu-id="649c4-107">调用 <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> 方法以生成该对象的副本。</span><span class="sxs-lookup"><span data-stu-id="649c4-107">Call the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> method to produce a replica of the object.</span></span> <span data-ttu-id="649c4-108">在反序列化时，必须将返回的对象强制转换为原始对象的类型，如下面的示例中所示，该示例将该对象反序列化为文件（尽管也可以将该对象反序列化为流）。</span><span class="sxs-lookup"><span data-stu-id="649c4-108">When deserializing, you must cast the returned object to the type of the original, as shown in the following example, which deserializes the object into a file (although it could also be deserialized into a stream).</span></span>  
  
    ```vb  
    Dim myObject As MySerializableClass  
    ' Construct an instance of the XmlSerializer with the type  
    ' of object that is being deserialized.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To read the file, create a FileStream.  
    Dim myFileStream As FileStream = _  
    New FileStream("myFileName.xml", FileMode.Open)  
    ' Call the Deserialize method and cast to the object type.  
    myObject = CType( _  
    mySerializer.Deserialize(myFileStream), MySerializableClass)  
    ```  
  
    ```csharp  
    MySerializableClass myObject;  
    // Construct an instance of the XmlSerializer with the type  
    // of object that is being deserialized.  
    XmlSerializer mySerializer =   
    new XmlSerializer(typeof(MySerializableClass));  
    // To read the file, create a FileStream.  
    FileStream myFileStream =   
    new FileStream("myFileName.xml", FileMode.Open);  
    // Call the Deserialize method and cast to the object type.  
    myObject = (MySerializableClass)   
    mySerializer.Deserialize(myFileStream)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="649c4-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="649c4-109">See also</span></span>

- [<span data-ttu-id="649c4-110">XML 序列化简介</span><span class="sxs-lookup"><span data-stu-id="649c4-110">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
- [<span data-ttu-id="649c4-111">如何：序列化对象</span><span class="sxs-lookup"><span data-stu-id="649c4-111">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
