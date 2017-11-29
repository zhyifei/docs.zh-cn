---
title: "如何：对 JSON 数据进行序列化和反序列化"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 14029250f3bc26ff8598e0b8d4ccce8e9fcca331
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-serialize-and-deserialize-json-data"></a>如何：对 JSON 数据进行序列化和反序列化
JSON（JavaScript 对象符号）是一种高效的数据编码格式，可用于在客户端浏览器和支持 AJAX 的 Web 服务之间快速交换少量数据。  
  
 本主题演示如何使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 将 .NET 类型对象序列化为 JSON 编码数据，然后将 JSON 格式的数据反序列化回 .NET 类型的实例。 本示例使用数据协定来演示用户定义的 `Person` 类型的序列化和反序列化。  
  
 通常，当在通过支持 AJAX 的终结点公开的服务操作中使用数据协定类型时，[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 会自动处理 JSON 序列化和反序列化。 但是，在某些情况下您可能需要直接处理 JSON 数据，这正是本主题演示的方案。  
  
> [!NOTE]
>  如果在服务器上序列化传出答复期间出现错误，或者答复操作由于某个其他原因引发异常，则可能不会将其作为错误返回到客户端。  
  
 本主题基于[JSON 序列化](../../../../docs/framework/wcf/samples/json-serialization.md)示例。  
  
### <a name="to-define-the-data-contract-for-a-person"></a>定义 Person 的数据协定  
  
1.  通过将 `Person` 附加到类并将 <xref:System.Runtime.Serialization.DataContractAttribute> 特性附加到要序列化的成员，为 <xref:System.Runtime.Serialization.DataMemberAttribute> 定义数据协定。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]数据协定，请参阅[设计服务协定](../../../../docs/framework/wcf/designing-service-contracts.md)。  
  
    ```  
    [DataContract]  
        internal class Person  
        {  
            [DataMember]  
            internal string name;  
  
            [DataMember]  
            internal int age;  
        }  
    ```  
  
### <a name="to-serialize-an-instance-of-type-person-to-json"></a>将 Person 类型的实例序列化为 JSON  
  
1.  创建 `Person` 类型的实例。  
  
    ```  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2.  使用 `Person` 将 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 对象序列化为内存流。  
  
    ```  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3.  使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 方法将 JSON 数据写入到流中。  
  
    ```  
    ser.WriteObject(stream1, p);  
    ```  
  
4.  显示 JSON 输出。  
  
    ```  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
### <a name="to-deserialize-an-instance-of-type-person-from-json"></a>从 JSON 反序列化 Person 类型的实例  
  
1.  通过使用 `Person` 的 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> 方法，将 JSON 编码数据反序列化为一个新的 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 实例。  
  
    ```  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2.  显示结果。  
  
    ```  
    Console.Write("Deserialized back, got name=");  
    Console.Write(p2.name);  
    Console.Write(", age=");  
    Console.WriteLine(p2.age);  
    ```  
  
## <a name="example"></a>示例  
  
```  
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
>  对于包含多个具有相同名称的成员的数据协定，JSON 序列化程序将引发一个序列化异常，如以下示例代码中所示。  
  
```  
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
  
## <a name="see-also"></a>另请参阅  
 [独立 JSON 序列化](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)  
 [对 JSON 和其他数据传输格式的支持](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)
