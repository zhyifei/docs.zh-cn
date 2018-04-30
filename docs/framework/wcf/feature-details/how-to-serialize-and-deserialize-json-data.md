---
title: 如何：对 JSON 数据进行序列化和反序列化
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9152e0047102661664f9b158aa26f83fb1d3c25c
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-serialize-and-deserialize-json-data"></a><span data-ttu-id="c5a8c-102">如何：对 JSON 数据进行序列化和反序列化</span><span class="sxs-lookup"><span data-stu-id="c5a8c-102">How to: Serialize and Deserialize JSON Data</span></span>
<span data-ttu-id="c5a8c-103">JSON（JavaScript 对象符号）是一种高效的数据编码格式，可用于在客户端浏览器和支持 AJAX 的 Web 服务之间快速交换少量数据。</span><span class="sxs-lookup"><span data-stu-id="c5a8c-103">JSON (JavaScript Object Notation) is an efficient data encoding format that enables fast exchanges of small amounts of data between client browsers and AJAX-enabled Web services.</span></span>  
  
 <span data-ttu-id="c5a8c-104">本主题演示如何使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 将 .NET 类型对象序列化为 JSON 编码数据，然后将 JSON 格式的数据反序列化回 .NET 类型的实例。</span><span class="sxs-lookup"><span data-stu-id="c5a8c-104">This topic demonstrates how to serialize .NET type objects into JSON-encoded data and then deserialize data in the JSON format back into instances of .NET types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span> <span data-ttu-id="c5a8c-105">本示例使用数据协定来演示用户定义的 `Person` 类型的序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="c5a8c-105">This example uses a data contract to demonstrate serialization and deserialization of a user-defined `Person` type.</span></span>  
  
 <span data-ttu-id="c5a8c-106">通常，当在通过支持 AJAX 的终结点公开的服务操作中使用数据协定类型时，[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 会自动处理 JSON 序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="c5a8c-106">Normally, JSON serialization and deserialization is handled automatically by [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] when you use data contract types in service operations that are exposed over AJAX-enabled endpoints.</span></span> <span data-ttu-id="c5a8c-107">但是，在某些情况下您可能需要直接处理 JSON 数据，这正是本主题演示的方案。</span><span class="sxs-lookup"><span data-stu-id="c5a8c-107">However, in some cases you may need to work with JSON data directly - this is the scenario that this topic demonstrates.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5a8c-108">如果在服务器上序列化传出答复期间出现错误，或者答复操作由于某个其他原因引发异常，则可能不会将其作为错误返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="c5a8c-108">If an error occurs during serialization of an outgoing reply on the server or the reply operation throws an exception for some other reason, it may not get returned to the client as a fault.</span></span>  
  
 <span data-ttu-id="c5a8c-109">本主题基于[JSON 序列化](../../../../docs/framework/wcf/samples/json-serialization.md)示例。</span><span class="sxs-lookup"><span data-stu-id="c5a8c-109">This topic is based on the [JSON Serialization](../../../../docs/framework/wcf/samples/json-serialization.md) sample.</span></span>  
  
### <a name="to-define-the-data-contract-for-a-person"></a><span data-ttu-id="c5a8c-110">定义 Person 的数据协定</span><span class="sxs-lookup"><span data-stu-id="c5a8c-110">To define the data contract for a Person</span></span>  
  
1.  <span data-ttu-id="c5a8c-111">通过将 `Person` 附加到类并将 <xref:System.Runtime.Serialization.DataContractAttribute> 特性附加到要序列化的成员，为 <xref:System.Runtime.Serialization.DataMemberAttribute> 定义数据协定。</span><span class="sxs-lookup"><span data-stu-id="c5a8c-111">Define the data contract for `Person` by attaching the <xref:System.Runtime.Serialization.DataContractAttribute> to the class and <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the members you want to serialize.</span></span> <span data-ttu-id="c5a8c-112">有关数据协定的详细信息，请参阅[设计服务协定](../../../../docs/framework/wcf/designing-service-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="c5a8c-112">For more information about data contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
    ```csharp  
    [DataContract]  
    internal class Person  
    {  
        [DataMember]  
        internal string name;  
  
        [DataMember]  
        internal int age;  
    }  
    ```  
  
### <a name="to-serialize-an-instance-of-type-person-to-json"></a><span data-ttu-id="c5a8c-113">将 Person 类型的实例序列化为 JSON</span><span class="sxs-lookup"><span data-stu-id="c5a8c-113">To serialize an instance of type Person to JSON</span></span>  
  
1.  <span data-ttu-id="c5a8c-114">创建 `Person` 类型的实例。</span><span class="sxs-lookup"><span data-stu-id="c5a8c-114">Create an instance of the `Person` type.</span></span>  
  
    ```csharp  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2.  <span data-ttu-id="c5a8c-115">使用 `Person` 将 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 对象序列化为内存流。</span><span class="sxs-lookup"><span data-stu-id="c5a8c-115">Serialize the `Person` object to a memory stream using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```csharp  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3.  <span data-ttu-id="c5a8c-116">使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 方法将 JSON 数据写入到流中。</span><span class="sxs-lookup"><span data-stu-id="c5a8c-116">Use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> method to write JSON data to the stream.</span></span>  
  
    ```csharp  
    ser.WriteObject(stream1, p);  
    ```  
  
4.  <span data-ttu-id="c5a8c-117">显示 JSON 输出。</span><span class="sxs-lookup"><span data-stu-id="c5a8c-117">Show the JSON output.</span></span>  
  
    ```csharp  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
### <a name="to-deserialize-an-instance-of-type-person-from-json"></a><span data-ttu-id="c5a8c-118">从 JSON 反序列化 Person 类型的实例</span><span class="sxs-lookup"><span data-stu-id="c5a8c-118">To deserialize an instance of type Person from JSON</span></span>  
  
1.  <span data-ttu-id="c5a8c-119">通过使用 `Person` 的 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> 方法，将 JSON 编码数据反序列化为一个新的 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 实例。</span><span class="sxs-lookup"><span data-stu-id="c5a8c-119">Deserialize the JSON-encoded data into a new instance of `Person` by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> method of the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```csharp  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2.  <span data-ttu-id="c5a8c-120">显示结果。</span><span class="sxs-lookup"><span data-stu-id="c5a8c-120">Show the results.</span></span>  
  
    ```csharp  
    Console.WriteLine($"Deserialized back, got name={p2.name}, age={p2.age}");  
    ```  
  
## <a name="example"></a><span data-ttu-id="c5a8c-121">示例</span><span class="sxs-lookup"><span data-stu-id="c5a8c-121">Example</span></span>  
  
```csharp  
// Create a User object and serialize it to a JSON stream.  
public static string WriteFromObject()  
{  
    //Create User object.  
    User user = new User("Bob", 42);  
  
    //Create a stream to serialize the object to.  
    MemoryStream ms = new MemoryStream();  
  
    // Serializer the User object to the stream.  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(User));  
    ser.WriteObject(ms, user);  
    byte[] json = ms.ToArray();  
    ms.Close();  
    return Encoding.UTF8.GetString(json, 0, json.Length);  
}  
  
// Deserialize a JSON stream to a User object.  
public static User ReadToObject(string json)  
{  
    User deserializedUser = new User();  
    MemoryStream ms = new MemoryStream(Encoding.UTF8.GetBytes(json));  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(deserializedUser.GetType());  
    deserializedUser = ser.ReadObject(ms) as User;  
    ms.Close();  
    return deserializedUser;  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="c5a8c-122">对于包含多个具有相同名称的成员的数据协定，JSON 序列化程序将引发一个序列化异常，如以下示例代码中所示。</span><span class="sxs-lookup"><span data-stu-id="c5a8c-122">The JSON serializer throws a serialization exception for data contracts that have multiple members with the same name, as shown in the following sample code.</span></span>  
  
```csharp  
[DataContract]  
public class TestDuplicateDataBase  
{  
    [DataMember]  
    public int field1 = 123;  
}

[DataContract]  
public class TestDuplicateDataDerived : TestDuplicateDataBase  
{  
    [DataMember]  
    public new int field1 = 999;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5a8c-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5a8c-123">See Also</span></span>  
 [<span data-ttu-id="c5a8c-124">独立 JSON 序列化</span><span class="sxs-lookup"><span data-stu-id="c5a8c-124">Stand-Alone JSON Serialization</span></span>](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)  
 [<span data-ttu-id="c5a8c-125">支持 JSON 和其他数据传输格式</span><span class="sxs-lookup"><span data-stu-id="c5a8c-125">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)
