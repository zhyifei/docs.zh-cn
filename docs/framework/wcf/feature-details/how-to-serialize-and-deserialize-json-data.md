---
title: 如何：对 JSON 数据进行序列化和反序列化
ms.date: 03/25/2019
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
ms.openlocfilehash: 7edce66a23021fa03a6f98b3b847a5b671c17124
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336949"
---
# <a name="how-to-serialize-and-deserialize-json-data"></a><span data-ttu-id="bb977-102">如何：序列化和反序列化 JSON 数据</span><span class="sxs-lookup"><span data-stu-id="bb977-102">How to: Serialize and deserialize JSON data</span></span>
<span data-ttu-id="bb977-103">JSON（JavaScript 对象符号）是一种高效的数据编码格式，可用于在客户端浏览器和支持 AJAX 的 Web 服务之间快速交换少量数据。</span><span class="sxs-lookup"><span data-stu-id="bb977-103">JSON (JavaScript Object Notation) is an efficient data encoding format that enables fast exchanges of small amounts of data between client browsers and AJAX-enabled Web services.</span></span>  
  
 <span data-ttu-id="bb977-104">本文演示如何以.NET 类型对象序列化为 JSON 编码数据，然后以 JSON 格式的数据反序列化回.NET 类型的实例。</span><span class="sxs-lookup"><span data-stu-id="bb977-104">This article demonstrates how to serialize .NET type objects into JSON-encoded data and then deserialize data in the JSON format back into instances of .NET types.</span></span> <span data-ttu-id="bb977-105">此示例使用数据协定演示序列化和反序列化的用户定义`Person`类型，并使用<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>。</span><span class="sxs-lookup"><span data-stu-id="bb977-105">This example uses a data contract to demonstrate serialization and deserialization of a user-defined `Person` type and uses <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
 <span data-ttu-id="bb977-106">通常情况下，JSON 序列化和反序列化自动处理由 Windows Communication Foundation (WCF) 通过启用 AJAX 的终结点公开的服务操作中使用数据协定类型时。</span><span class="sxs-lookup"><span data-stu-id="bb977-106">Normally, JSON serialization and deserialization are handled automatically by Windows Communication Foundation (WCF) when you use data contract types in service operations that are exposed over AJAX-enabled endpoints.</span></span> <span data-ttu-id="bb977-107">但是，在某些情况下，您可能需要直接处理 JSON 数据。</span><span class="sxs-lookup"><span data-stu-id="bb977-107">However, in some cases you may need to work with JSON data directly.</span></span>   
  
> [!NOTE]
>  <span data-ttu-id="bb977-108">如果在服务器上或某些其他原因的传出答复的序列化期间发生错误，它可能不获取返回到客户端作为错误。</span><span class="sxs-lookup"><span data-stu-id="bb977-108">If an error occurs during serialization of an outgoing reply on the server or for some other reason, it may not get returned to the client as a fault.</span></span>  
  
 <span data-ttu-id="bb977-109">这篇文章基于[JSON 序列化](../samples/json-serialization.md)示例。</span><span class="sxs-lookup"><span data-stu-id="bb977-109">This article is based on the [JSON serialization](../samples/json-serialization.md) sample.</span></span>  
  
## <a name="to-define-the-data-contract-for-a-person-type"></a><span data-ttu-id="bb977-110">若要定义一个 Person 类型的数据协定</span><span class="sxs-lookup"><span data-stu-id="bb977-110">To define the data contract for a Person type</span></span> 
  
1. <span data-ttu-id="bb977-111">通过将 `Person` 附加到类并将 <xref:System.Runtime.Serialization.DataContractAttribute> 特性附加到要序列化的成员，为 <xref:System.Runtime.Serialization.DataMemberAttribute> 定义数据协定。</span><span class="sxs-lookup"><span data-stu-id="bb977-111">Define the data contract for `Person` by attaching the <xref:System.Runtime.Serialization.DataContractAttribute> to the class and <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the members you want to serialize.</span></span> <span data-ttu-id="bb977-112">有关数据协定的详细信息，请参阅[设计服务协定](../designing-service-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="bb977-112">For more information about data contracts, see [Designing service contracts](../designing-service-contracts.md).</span></span>  
  
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
  
## <a name="to-serialize-an-instance-of-type-person-to-json"></a><span data-ttu-id="bb977-113">将 Person 类型的实例序列化为 JSON</span><span class="sxs-lookup"><span data-stu-id="bb977-113">To serialize an instance of type Person to JSON</span></span>  
  
1. <span data-ttu-id="bb977-114">创建 `Person` 类型的实例。</span><span class="sxs-lookup"><span data-stu-id="bb977-114">Create an instance of the `Person` type.</span></span>  
  
    ```csharp  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2. <span data-ttu-id="bb977-115">序列化`Person`到使用内存流<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>。</span><span class="sxs-lookup"><span data-stu-id="bb977-115">Serialize the `Person` object to a memory stream by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```csharp  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3. <span data-ttu-id="bb977-116">使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 方法将 JSON 数据写入到流中。</span><span class="sxs-lookup"><span data-stu-id="bb977-116">Use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> method to write JSON data to the stream.</span></span>  
  
    ```csharp  
    ser.WriteObject(stream1, p);  
    ```  
  
4. <span data-ttu-id="bb977-117">显示 JSON 输出。</span><span class="sxs-lookup"><span data-stu-id="bb977-117">Show the JSON output.</span></span>  
  
    ```csharp  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
## <a name="to-deserialize-an-instance-of-type-person-from-json"></a><span data-ttu-id="bb977-118">从 JSON 反序列化 Person 类型的实例</span><span class="sxs-lookup"><span data-stu-id="bb977-118">To deserialize an instance of type Person from JSON</span></span>  
  
1. <span data-ttu-id="bb977-119">通过使用 `Person` 的 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> 方法，将 JSON 编码数据反序列化为一个新的 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 实例。</span><span class="sxs-lookup"><span data-stu-id="bb977-119">Deserialize the JSON-encoded data into a new instance of `Person` by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> method of the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```csharp  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2. <span data-ttu-id="bb977-120">显示结果。</span><span class="sxs-lookup"><span data-stu-id="bb977-120">Show the results.</span></span>  
  
    ```csharp  
    Console.WriteLine($"Deserialized back, got name={p2.name}, age={p2.age}");  
    ```  
  
## <a name="example"></a><span data-ttu-id="bb977-121">示例</span><span class="sxs-lookup"><span data-stu-id="bb977-121">Example</span></span>  
  
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
>  <span data-ttu-id="bb977-122">对于包含多个具有相同名称的成员的数据协定，JSON 序列化程序将引发一个序列化异常，如以下示例代码中所示。</span><span class="sxs-lookup"><span data-stu-id="bb977-122">The JSON serializer throws a serialization exception for data contracts that have multiple members with the same name, as shown in the following sample code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bb977-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb977-123">See also</span></span>

- [<span data-ttu-id="bb977-124">独立 JSON 序列化</span><span class="sxs-lookup"><span data-stu-id="bb977-124">Stand-alone JSON serialization</span></span>](stand-alone-json-serialization.md)
- [<span data-ttu-id="bb977-125">支持 JSON 和其他数据传输格式</span><span class="sxs-lookup"><span data-stu-id="bb977-125">Support for JSON and other data transfer formats</span></span>](support-for-json-and-other-data-transfer-formats.md)
