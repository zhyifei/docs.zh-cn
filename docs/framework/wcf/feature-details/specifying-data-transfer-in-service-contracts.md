---
title: 在服务协定中指定数据传输
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], data transfer
ms.assetid: 7c5a26c8-89c9-4bcb-a4bc-7131e6d01f0c
ms.openlocfilehash: a9066054c82fdb2e25dace0b7611df4cbbf4ec93
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54617260"
---
# <a name="specifying-data-transfer-in-service-contracts"></a><span data-ttu-id="0eee0-102">在服务协定中指定数据传输</span><span class="sxs-lookup"><span data-stu-id="0eee0-102">Specifying Data Transfer in Service Contracts</span></span>
<span data-ttu-id="0eee0-103">Windows Communication Foundation (WCF) 将视为消息传送基础结构。</span><span class="sxs-lookup"><span data-stu-id="0eee0-103">The Windows Communication Foundation (WCF) can be thought of as a messaging infrastructure.</span></span> <span data-ttu-id="0eee0-104">服务操作可以接收消息、处理消息以及发送消息。</span><span class="sxs-lookup"><span data-stu-id="0eee0-104">Service operations can receive messages, process them, and send them messages.</span></span> <span data-ttu-id="0eee0-105">消息是使用操作协定描述的。</span><span class="sxs-lookup"><span data-stu-id="0eee0-105">Messages are described using operation contracts.</span></span> <span data-ttu-id="0eee0-106">例如，请考虑以下协定。</span><span class="sxs-lookup"><span data-stu-id="0eee0-106">For example, consider the following contract.</span></span>  
  
```csharp  
[ServiceContract]  
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    float GetAirfare(string fromCity, string toCity);  
}  
```  
  
```vb  
<ServiceContract()>  
Public Interface IAirfareQuoteService  
  
    <OperationContract()>  
    Function GetAirfare(fromCity As String, toCity As String) As Double  
End Interface  
```  
  
 <span data-ttu-id="0eee0-107">这里，`GetAirfare` 操作接受了一个包含有关 `fromCity` 和 `toCity` 的信息的消息，然后返回一个包含一个数字的消息。</span><span class="sxs-lookup"><span data-stu-id="0eee0-107">Here, the `GetAirfare` operation accepts a message with information about `fromCity` and `toCity`, and then returns a message that contains a number.</span></span>  
  
 <span data-ttu-id="0eee0-108">本主题说明操作协定可用来描述消息的各种方式。</span><span class="sxs-lookup"><span data-stu-id="0eee0-108">This topic explains the various ways in which an operation contract can describe messages.</span></span>  
  
## <a name="describing-messages-by-using-parameters"></a><span data-ttu-id="0eee0-109">使用参数描述消息</span><span class="sxs-lookup"><span data-stu-id="0eee0-109">Describing Messages by Using Parameters</span></span>  
 <span data-ttu-id="0eee0-110">描述消息的最简单方式是使用参数列表和返回值。</span><span class="sxs-lookup"><span data-stu-id="0eee0-110">The simplest way to describe a message is to use a parameter list and the return value.</span></span> <span data-ttu-id="0eee0-111">在上面的示例中，`fromCity` 和 `toCity` 字符串参数用于描述请求消息，浮点型返回值用于描述答复消息。</span><span class="sxs-lookup"><span data-stu-id="0eee0-111">In the preceding example, the `fromCity` and `toCity` string parameters were used to describe the request message, and the float return value was used to describe the reply message.</span></span> <span data-ttu-id="0eee0-112">如果返回值本身不足以描述答复消息，则可以使用 out 参数。</span><span class="sxs-lookup"><span data-stu-id="0eee0-112">If the return value alone is not enough to describe a reply message, out parameters may be used.</span></span> <span data-ttu-id="0eee0-113">例如，下面的操作在其请求消息中包含 `fromCity` 和 `toCity`，在其答复消息中包含一个数字和一种货币。</span><span class="sxs-lookup"><span data-stu-id="0eee0-113">For example, the following operation has `fromCity` and `toCity` in its request message, and a number together with a currency in its reply message:</span></span>  
  
```csharp  
[OperationContract]  
float GetAirfare(string fromCity, string toCity, out string currency);  
```  
  
```vb  
<OperationContract()>  
    Function GetAirfare(fromCity As String, toCity As String) As Double  
```  
  
 <span data-ttu-id="0eee0-114">此外，可以使用引用参数让某个参数同时成为请求消息和答复消息的一部分。</span><span class="sxs-lookup"><span data-stu-id="0eee0-114">Additionally, you may use reference parameters to make a parameter part of both the request and the reply message.</span></span> <span data-ttu-id="0eee0-115">这些参数必须是可以序列化（转换为 XML）的类型。</span><span class="sxs-lookup"><span data-stu-id="0eee0-115">The parameters must be of types that can be serialized (converted to XML).</span></span> <span data-ttu-id="0eee0-116">默认情况下，WCF 使用名为的组件<xref:System.Runtime.Serialization.DataContractSerializer>类来执行此转换。</span><span class="sxs-lookup"><span data-stu-id="0eee0-116">By default, WCF uses a component called the <xref:System.Runtime.Serialization.DataContractSerializer> class to perform this conversion.</span></span> <span data-ttu-id="0eee0-117">支持大多数基元类型（如 `int`、`string`、`float` 和 `DateTime`）。</span><span class="sxs-lookup"><span data-stu-id="0eee0-117">Most primitive types (such as `int`, `string`, `float`, and `DateTime`.) are supported.</span></span> <span data-ttu-id="0eee0-118">用户定义的类型通常必须具有数据协定。</span><span class="sxs-lookup"><span data-stu-id="0eee0-118">User-defined types must normally have a data contract.</span></span> <span data-ttu-id="0eee0-119">有关详细信息，请参阅[Using Data Contracts](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="0eee0-119">For more information, see [Using Data Contracts](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).</span></span>  
  
```csharp
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    float GetAirfare(Itinerary itinerary, DateTime date);  
  
    [DataContract]  
    public class Itinerary  
    {  
        [DataMember]  
        public string fromCity;  
        [DataMember]  
        public string toCity;  
   }  
}  
```  
  
```vb  
Public Interface IAirfareQuoteService  
    <OperationContract()>  
    GetAirfare(itinerary as Itinerary, date as DateTime) as Double  
  
    <DataContract()>  
    Class Itinerary  
  
        <DataMember()>  
        Public fromCity As String  
        <DataMember()>  
        Public toCity As String  
    End Class  
End Interface  
```  
  
 <span data-ttu-id="0eee0-120">偶尔，`DataContractSerializer` 不足以序列化您的类型。</span><span class="sxs-lookup"><span data-stu-id="0eee0-120">Occasionally, the `DataContractSerializer` is not adequate to serialize your types.</span></span> <span data-ttu-id="0eee0-121">WCF 支持一个备选的序列化引擎<xref:System.Xml.Serialization.XmlSerializer>，这还可用于序列化参数。</span><span class="sxs-lookup"><span data-stu-id="0eee0-121">WCF supports an alternative serialization engine, the <xref:System.Xml.Serialization.XmlSerializer>, which you can also use to serialize parameters.</span></span> <span data-ttu-id="0eee0-122"><xref:System.Xml.Serialization.XmlSerializer> 使您可以使用诸如 `XmlAttributeAttribute` 之类的属性对得到的 XML 进行更多控制。</span><span class="sxs-lookup"><span data-stu-id="0eee0-122">The <xref:System.Xml.Serialization.XmlSerializer> allows you to use more control over the resultant XML using attributes such as the `XmlAttributeAttribute`.</span></span> <span data-ttu-id="0eee0-123">若要切换到对特定操作或整个服务使用 <xref:System.Xml.Serialization.XmlSerializer>，请将 <xref:System.ServiceModel.XmlSerializerFormatAttribute> 属性应用到相应的操作或服务。</span><span class="sxs-lookup"><span data-stu-id="0eee0-123">To switch to using the <xref:System.Xml.Serialization.XmlSerializer> for a particular operation or for the entire service, apply the <xref:System.ServiceModel.XmlSerializerFormatAttribute> attribute to an operation or a service.</span></span> <span data-ttu-id="0eee0-124">例如：</span><span class="sxs-lookup"><span data-stu-id="0eee0-124">For example:</span></span>  
  
```csharp  
[ServiceContract]  
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    [XmlSerializerFormat]  
    float GetAirfare(Itinerary itinerary, DateTime date);  
}  
public class Itinerary  
{  
    public string fromCity;  
    public string toCity;  
    [XmlAttribute]  
    public bool isFirstClass;  
}  
```  
  
```vb  
<ServiceContract()>  
Public Interface IAirfareQuoteService  
    <OperationContract()>  
    <XmlSerializerFormat>  
    GetAirfare(itinerary as Itinerary, date as DateTime) as Double  
  
End Interface  
  
Class Itinerary  
  
    Public fromCity As String  
    Public toCity As String  
    <XmlSerializerFormat()>  
    Public isFirstClass As Boolean  
End Class  
```  
  
 <span data-ttu-id="0eee0-125">有关详细信息，请参阅[使用 XmlSerializer 类](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)。</span><span class="sxs-lookup"><span data-stu-id="0eee0-125">For more information, see [Using the XmlSerializer Class](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md).</span></span> <span data-ttu-id="0eee0-126">请记住，最好不要如此处所示手动切换到 <xref:System.Xml.Serialization.XmlSerializer>，除非有该主题详细讨论的特定原因需要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0eee0-126">Remember that manually switching to the <xref:System.Xml.Serialization.XmlSerializer> as shown here is not recommended unless you have specific reasons to do so as detailed in that topic.</span></span>  
  
 <span data-ttu-id="0eee0-127">若要将 .NET 参数名称与协定名称分开，可以使用 <xref:System.ServiceModel.MessageParameterAttribute> 属性 (Attribute)，并且使用 `Name` 属性 (Property) 来设置协定名称。</span><span class="sxs-lookup"><span data-stu-id="0eee0-127">To isolate .NET parameter names from contract names, you can use the <xref:System.ServiceModel.MessageParameterAttribute> attribute, and use the `Name` property to set the contract name.</span></span> <span data-ttu-id="0eee0-128">例如，下面的操作协定等效于本主题中的第一个示例。</span><span class="sxs-lookup"><span data-stu-id="0eee0-128">For example, the following operation contract is equivalent to the first example in this topic.</span></span>  
  
```csharp  
[OperationContract]  
public float GetAirfare(  
    [MessageParameter(Name="fromCity")] string originCity,  
    [MessageParameter(Name="toCity")] string destinationCity);  
```  
  
```vb  
<OperationContract()>  
  Function GetAirfare(<MessageParameter(Name := "fromCity")> fromCity As String, <MessageParameter(Name := "toCity")> toCity As String) As Double  
```  
  
## <a name="describing-empty-messages"></a><span data-ttu-id="0eee0-129">描述空消息</span><span class="sxs-lookup"><span data-stu-id="0eee0-129">Describing Empty Messages</span></span>  
 <span data-ttu-id="0eee0-130">可以通过不使用输入参数和引用参数来描述空请求消息。</span><span class="sxs-lookup"><span data-stu-id="0eee0-130">An empty request message can be described by having no input or reference parameters.</span></span> <span data-ttu-id="0eee0-131">例如，在 C# 中：</span><span class="sxs-lookup"><span data-stu-id="0eee0-131">For example in C#:</span></span>  
  
 `[OperationContract]`  
  
 `public int GetCurrentTemperature();`  
  
 <span data-ttu-id="0eee0-132">例如，在 VB 中：</span><span class="sxs-lookup"><span data-stu-id="0eee0-132">For example in VB:</span></span>  
  
 `<OperationContract()>`  
  
 `Function GetCurrentTemperature() as Integer`  
  
 <span data-ttu-id="0eee0-133">可以通过使用 `void` 返回类型并且不使用输出参数和引用参数来描述空答复消息。</span><span class="sxs-lookup"><span data-stu-id="0eee0-133">An empty reply message can be described by having a `void` return type and no output or reference parameters.</span></span> <span data-ttu-id="0eee0-134">例如，在：</span><span class="sxs-lookup"><span data-stu-id="0eee0-134">For example in:</span></span>  
  
```csharp  
[OperationContract]  
public void SetTemperature(int temperature);  
```  
  
```vb  
<OperationContract()>  
Sub SetTemperature(temperature As Integer)  
```  
  
 <span data-ttu-id="0eee0-135">这不同于单向操作，例如：</span><span class="sxs-lookup"><span data-stu-id="0eee0-135">This is different from a one-way operation, such as:</span></span>  
  
```csharp  
[OperationContract(IsOneWay=true)]  
public void SetLightbulbStatus(bool isOn);  
```  
  
```vb  
<OperationContract(IsOneWay:=True)>  
Sub SetLightbulbStatus(isOne As Boolean)  
```  
  
 <span data-ttu-id="0eee0-136">`SetTemperatureStatus` 操作返回一个空消息。</span><span class="sxs-lookup"><span data-stu-id="0eee0-136">The `SetTemperatureStatus` operation returns an empty message.</span></span> <span data-ttu-id="0eee0-137">如果在处理输入消息时出现问题，它可能改而返回错误。</span><span class="sxs-lookup"><span data-stu-id="0eee0-137">It may return a fault instead if there is a problem processing the input message.</span></span> <span data-ttu-id="0eee0-138">`SetLightbulbStatus` 操作不返回任何内容。</span><span class="sxs-lookup"><span data-stu-id="0eee0-138">The `SetLightbulbStatus` operation returns nothing.</span></span> <span data-ttu-id="0eee0-139">无法在此操作中传递错误条件。</span><span class="sxs-lookup"><span data-stu-id="0eee0-139">There is no way to communicate a fault condition from this operation.</span></span>  
  
## <a name="describing-messages-by-using-message-contracts"></a><span data-ttu-id="0eee0-140">使用消息协定描述消息</span><span class="sxs-lookup"><span data-stu-id="0eee0-140">Describing Messages by Using Message Contracts</span></span>  
 <span data-ttu-id="0eee0-141">您可能希望使用单个类型来表示整个消息。</span><span class="sxs-lookup"><span data-stu-id="0eee0-141">You may want to use a single type to represent the entire message.</span></span> <span data-ttu-id="0eee0-142">虽然可将数据协定用于此目的，但建议使用消息协定来执行此操作，这可以避免在得到的 XML 中采用不必要的包装级别。</span><span class="sxs-lookup"><span data-stu-id="0eee0-142">While it is possible to use a data contract for this purpose, the recommended way to do this is to use a message contract—this avoids unnecessary levels of wrapping in the resultant XML.</span></span> <span data-ttu-id="0eee0-143">此外，使用消息协定可以对得到的消息进行更多的控制。</span><span class="sxs-lookup"><span data-stu-id="0eee0-143">Additionally, message contracts allow you to exercise more control over resultant messages.</span></span> <span data-ttu-id="0eee0-144">例如，您可以决定哪些信息段应包含在消息正文中，哪些信息段应包含在消息头中。</span><span class="sxs-lookup"><span data-stu-id="0eee0-144">For instance, you can decide which pieces of information should be in the message body and which should be in the message headers.</span></span> <span data-ttu-id="0eee0-145">下面的示例演示消息协定的用法。</span><span class="sxs-lookup"><span data-stu-id="0eee0-145">The following example shows the use of message contracts.</span></span>  
  
```csharp  
[ServiceContract]  
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    GetAirfareResponse GetAirfare(GetAirfareRequest request);  
}  
  
[MessageContract]  
public class GetAirfareRequest  
{  
    [MessageHeader] public DateTime date;  
    [MessageBodyMember] public Itinerary itinerary;  
}  
  
[MessageContract]  
public class GetAirfareResponse  
{  
    [MessageBodyMember] public float airfare;  
    [MessageBodyMember] public string currency;  
}  
  
[DataContract]  
public class Itinerary  
{  
    [DataMember] public string fromCity;  
    [DataMember] public string toCity;  
}  
```  
  
```vb  
<ServiceContract()>  
Public Interface IAirfareQuoteService  
    <OperationContract()>  
    Function GetAirfare(request As GetAirfareRequest) As GetAirfareResponse  
End Interface  
  
<MessageContract()>  
Public Class GetAirfareRequest  
    <MessageHeader()>   
    Public Property date as DateTime  
    <MessageBodyMember()>  
    Public Property itinerary As Itinerary  
End Class  
  
<MessageContract()>  
Public Class GetAirfareResponse  
    <MessageBodyMember()>  
    Public Property airfare As Double  
    <MessageBodyMember()> Public Property currency As String  
End Class  
  
<DataContract()>  
Public Class Itinerary  
    <DataMember()> Public Property fromCity As String  
    <DataMember()> Public Property toCity As String  
End Class  
```  
  
 <span data-ttu-id="0eee0-146">有关详细信息，请参阅[Using Message Contracts](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="0eee0-146">For more information, see [Using Message Contracts](../../../../docs/framework/wcf/feature-details/using-message-contracts.md).</span></span>  
  
 <span data-ttu-id="0eee0-147">在上面的示例中，默认情况下仍然使用 <xref:System.Runtime.Serialization.DataContractSerializer> 类。</span><span class="sxs-lookup"><span data-stu-id="0eee0-147">In the previous example, the <xref:System.Runtime.Serialization.DataContractSerializer> class is still used by default.</span></span> <span data-ttu-id="0eee0-148"><xref:System.Xml.Serialization.XmlSerializer> 类也可用于消息协定。</span><span class="sxs-lookup"><span data-stu-id="0eee0-148">The <xref:System.Xml.Serialization.XmlSerializer> class can also be used with message contracts.</span></span> <span data-ttu-id="0eee0-149">为此，请将 <xref:System.ServiceModel.XmlSerializerFormatAttribute> 属性应用于操作或协定，并在消息头和正文成员中使用与 <xref:System.Xml.Serialization.XmlSerializer> 类兼容的类型。</span><span class="sxs-lookup"><span data-stu-id="0eee0-149">To do this, apply the <xref:System.ServiceModel.XmlSerializerFormatAttribute> attribute to either the operation or the contract, and use types compatible with the <xref:System.Xml.Serialization.XmlSerializer> class in the message headers and body members.</span></span>  
  
## <a name="describing-messages-by-using-streams"></a><span data-ttu-id="0eee0-150">使用流描述消息</span><span class="sxs-lookup"><span data-stu-id="0eee0-150">Describing Messages by Using Streams</span></span>  
 <span data-ttu-id="0eee0-151">另一种在操作中描述消息的方式是在操作协定中使用 <xref:System.IO.Stream> 类或它的派生类之一，或者将该类用作消息协定正文成员（此时，它必须是唯一的成员）。</span><span class="sxs-lookup"><span data-stu-id="0eee0-151">Another way to describe messages in operations is to use the <xref:System.IO.Stream> class or one of its derived classes in an operation contract or as a message contract body member (it must be the only member in this case).</span></span> <span data-ttu-id="0eee0-152">对于传入消息，类型必须是 `Stream` — 您不能使用派生类。</span><span class="sxs-lookup"><span data-stu-id="0eee0-152">For incoming messages, the type must be `Stream`—you cannot use derived classes.</span></span>  
  
 <span data-ttu-id="0eee0-153">而不是调用序列化程序，WCF 从流中检索数据并将它放入传出消息时，直接或从传入消息中检索数据并将其放在流中直接。</span><span class="sxs-lookup"><span data-stu-id="0eee0-153">Instead of invoking the serializer, WCF retrieves data from a stream and puts it directly into an outgoing message, or retrieves data from an incoming message and puts it directly into a stream.</span></span> <span data-ttu-id="0eee0-154">下面的示例演示流的用法。</span><span class="sxs-lookup"><span data-stu-id="0eee0-154">The following sample shows the use of streams.</span></span>  
  
```csharp  
[OperationContract]  
public Stream DownloadFile(string fileName);  
```  
  
```vb  
<OperationContract()>  
Function DownloadFile(fileName As String) As String  
```  
  
 <span data-ttu-id="0eee0-155">不能将 `Stream` 和非流数据一起放入单个消息正文中。</span><span class="sxs-lookup"><span data-stu-id="0eee0-155">You cannot combine `Stream` and non-stream data in a single message body.</span></span> <span data-ttu-id="0eee0-156">使用消息协定可将额外的数据放入消息头中。</span><span class="sxs-lookup"><span data-stu-id="0eee0-156">Use a message contract to put the extra data in message headers.</span></span> <span data-ttu-id="0eee0-157">下面的示例演示在定义操作协定时不正确的流用法。</span><span class="sxs-lookup"><span data-stu-id="0eee0-157">The following example shows the incorrect usage of streams when defining the operation contract.</span></span>  
  
```csharp  
//Incorrect:  
// [OperationContract]  
// public void UploadFile (string fileName, Stream fileData);  
```  
  
```vb  
'Incorrect:  
    '<OperationContract()>  
    Public Sub UploadFile(fileName As String, fileData As StreamingContext)  
```  
  
 <span data-ttu-id="0eee0-158">下面的示例演示在定义操作协定时正确的流用法。</span><span class="sxs-lookup"><span data-stu-id="0eee0-158">The following sample shows the correct usage of streams when defining an operation contract.</span></span>  
  
```csharp  
[OperationContract]  
public void UploadFile (UploadFileMessage message);  
//code omitted  
[MessageContract]  
public class UploadFileMessage  
{  
    [MessageHeader] public string fileName;  
    [MessageBodyMember] public Stream fileData;  
}  
```  
  
```vb  
<OperationContract()>  
Public Sub UploadFile(fileName As String, fileData As StreamingContext)  
'Code Omitted  
<MessageContract()>  
Public Class UploadFileMessage  
   <MessageHeader()>  
    Public Property fileName As String  
    <MessageBodyMember()>  
    Public Property fileData As Stream  
End Class  
```  
  
 <span data-ttu-id="0eee0-159">有关详细信息，请参阅[Large Data and Streaming](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)。</span><span class="sxs-lookup"><span data-stu-id="0eee0-159">For more information, see [Large Data and Streaming](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md).</span></span>  
  
## <a name="using-the-message-class"></a><span data-ttu-id="0eee0-160">使用 Message 类</span><span class="sxs-lookup"><span data-stu-id="0eee0-160">Using the Message Class</span></span>  
 <span data-ttu-id="0eee0-161">若要对发送或接收的消息具有完全编程控制，可以直接使用 <xref:System.ServiceModel.Channels.Message> 类，如下面的示例代码所示。</span><span class="sxs-lookup"><span data-stu-id="0eee0-161">To have complete programmatic control over messages sent or received, you can use the <xref:System.ServiceModel.Channels.Message> class directly, as shown in the following example code.</span></span>  
  
```csharp  
[OperationContract]  
public void LogMessage(Message m);  
```  
  
```vb  
<OperationContract()>  
Sub LogMessage(m As Message)  
```  
  
 <span data-ttu-id="0eee0-162">这是高级的方案中，在详细信息中所述[Using the Message Class](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)。</span><span class="sxs-lookup"><span data-stu-id="0eee0-162">This is an advanced scenario, which is described in detail in [Using the Message Class](../../../../docs/framework/wcf/feature-details/using-the-message-class.md).</span></span>  
  
## <a name="describing-fault-messages"></a><span data-ttu-id="0eee0-163">描述错误消息</span><span class="sxs-lookup"><span data-stu-id="0eee0-163">Describing Fault Messages</span></span>  
 <span data-ttu-id="0eee0-164">除了由返回值以及输出参数或引用参数描述的消息以外，任何非单向操作都至少可以返回两种可能的消息：它的正常响应消息和错误消息。</span><span class="sxs-lookup"><span data-stu-id="0eee0-164">In addition to the messages that are described by the return value and output or reference parameters, any operation that is not one-way can return at least two possible messages: its normal response message and a fault message.</span></span> <span data-ttu-id="0eee0-165">请考虑下面的操作协定。</span><span class="sxs-lookup"><span data-stu-id="0eee0-165">Consider the following operation contract.</span></span>  
  
```csharp  
[OperationContract]  
float GetAirfare(string fromCity, string toCity, DateTime date);  
```  
  
```vb  
<OperationContract()>  
Function GetAirfare(fromCity As String, toCity As String, date as DateTime)  
```  
  
 <span data-ttu-id="0eee0-166">此操作可能返回包含一个 `float` 数的正常消息，也可能返回包含一个错误代码和说明的错误消息。</span><span class="sxs-lookup"><span data-stu-id="0eee0-166">This operation may either return a normal message that contains a `float` number, or a fault message that contains a fault code and a description.</span></span> <span data-ttu-id="0eee0-167">这可以通过在服务实现中引发 <xref:System.ServiceModel.FaultException> 来实现。</span><span class="sxs-lookup"><span data-stu-id="0eee0-167">You can accomplish this by throwing a <xref:System.ServiceModel.FaultException> in your service implementation.</span></span>  
  
 <span data-ttu-id="0eee0-168">使用 <xref:System.ServiceModel.FaultContractAttribute> 属性可以指定其他可能的错误消息。</span><span class="sxs-lookup"><span data-stu-id="0eee0-168">You can specify additional possible fault messages by using the <xref:System.ServiceModel.FaultContractAttribute> attribute.</span></span> <span data-ttu-id="0eee0-169">其他错误必须可以使用 <xref:System.Runtime.Serialization.DataContractSerializer> 进行序列化，如下面的示例代码所示。</span><span class="sxs-lookup"><span data-stu-id="0eee0-169">The additional faults must be serializable using the <xref:System.Runtime.Serialization.DataContractSerializer>, as shown in the following example code.</span></span>  
  
```csharp  
[OperationContract]  
[FaultContract(typeof(ItineraryNotAvailableFault))]  
float GetAirfare(string fromCity, string toCity, DateTime date);  
  
//code omitted  
  
[DataContract]  
public class ItineraryNotAvailableFault  
{  
    [DataMember]  
    public bool IsAlternativeDateAvailable;  
  
    [DataMember]  
    public DateTime alternativeSuggestedDate;  
}  
```  
  
```vb  
<OperationContract()>  
<FaultContract(GetType(ItineraryNotAvailableFault))>  
Function GetAirfare(fromCity As String, toCity As String, date as DateTime) As Double  
  
'Code Omitted  
<DataContract()>  
Public Class  
  <DataMember()>  
  Public Property IsAlternativeDateAvailable As Boolean  
  <DataMember()>  
  Public Property alternativeSuggestedDate As DateTime  
End Class  
```  
  
 <span data-ttu-id="0eee0-170">可以通过引发相应数据协定类型的 <xref:System.ServiceModel.FaultException%601> 来生成这些其他错误。</span><span class="sxs-lookup"><span data-stu-id="0eee0-170">These additional faults can be generated by throwing a <xref:System.ServiceModel.FaultException%601> of the appropriate data contract type.</span></span> <span data-ttu-id="0eee0-171">有关详细信息，请参阅[处理异常和错误](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md)。</span><span class="sxs-lookup"><span data-stu-id="0eee0-171">For more information, see [Handling Exceptions and Faults](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md).</span></span>  
  
 <span data-ttu-id="0eee0-172">不能使用 <xref:System.Xml.Serialization.XmlSerializer> 类描述错误。</span><span class="sxs-lookup"><span data-stu-id="0eee0-172">You cannot use the <xref:System.Xml.Serialization.XmlSerializer> class to describe faults.</span></span> <span data-ttu-id="0eee0-173"><xref:System.ServiceModel.XmlSerializerFormatAttribute> 对错误协定无效。</span><span class="sxs-lookup"><span data-stu-id="0eee0-173">The <xref:System.ServiceModel.XmlSerializerFormatAttribute> has no effect on fault contracts.</span></span>  
  
## <a name="using-derived-types"></a><span data-ttu-id="0eee0-174">使用派生类型</span><span class="sxs-lookup"><span data-stu-id="0eee0-174">Using Derived Types</span></span>  
 <span data-ttu-id="0eee0-175">您可能希望在操作或消息协定中使用基类型，然后在实际调用操作时使用派生类型。</span><span class="sxs-lookup"><span data-stu-id="0eee0-175">You may want to use a base type in an operation or a message contract, and then use a derived type when actually invoking the operation.</span></span> <span data-ttu-id="0eee0-176">在这种情况下，必须使用 <xref:System.ServiceModel.ServiceKnownTypeAttribute> 属性或某种替代机制，以允许使用派生类型。</span><span class="sxs-lookup"><span data-stu-id="0eee0-176">In this case, you must use either the <xref:System.ServiceModel.ServiceKnownTypeAttribute> attribute or some alternative mechanism to allow the use of derived types.</span></span> <span data-ttu-id="0eee0-177">请考虑下面的操作。</span><span class="sxs-lookup"><span data-stu-id="0eee0-177">Consider the following operation.</span></span>  
  
```csharp  
[OperationContract]  
public bool IsLibraryItemAvailable(LibraryItem item);  
```  
  
```vb
<OperationContract()>  
    Function IsLibraryItemAvailable(item As LibraryItem) As Boolean  
```  
  
 <span data-ttu-id="0eee0-178">假定 `Book` 和 `Magazine` 这两个类型派生自 `LibraryItem`。</span><span class="sxs-lookup"><span data-stu-id="0eee0-178">Assume that two types, `Book` and `Magazine`, derive from `LibraryItem`.</span></span> <span data-ttu-id="0eee0-179">若要在 `IsLibraryItemAvailable` 操作中使用这些类型，可以按如下方式更改操作：</span><span class="sxs-lookup"><span data-stu-id="0eee0-179">To use these types in the `IsLibraryItemAvailable` operation, you can change the operation as follows:</span></span>  
  
 `[OperationContract]`  
  
 `[ServiceKnownType(typeof(Book))]`  
  
 `[ServiceKnownType(typeof(Magazine))]`  
  
 `public bool IsLibraryItemAvailable(LibraryItem item);`  
  
 <span data-ttu-id="0eee0-180">或者，当使用默认 <xref:System.Runtime.Serialization.KnownTypeAttribute> 时，也可以使用 <xref:System.Runtime.Serialization.DataContractSerializer> 属性，如下面的示例代码所示。</span><span class="sxs-lookup"><span data-stu-id="0eee0-180">Alternatively, you can use the <xref:System.Runtime.Serialization.KnownTypeAttribute> attribute when the default <xref:System.Runtime.Serialization.DataContractSerializer> is in use, as shown in the following example code.</span></span>  
  
```csharp  
[OperationContract]  
public bool IsLibraryItemAvailable(LibraryItem item);  
  
// code omitted   
  
[DataContract]  
[KnownType(typeof(Book))]  
[KnownType(typeof(Magazine))]  
public class LibraryItem  
{  
    //code omitted  
}  
```  
  
```vb  
<OperationContract()>  
Function IsLibraryItemAvailable(item As LibraryItem) As Boolean  
  
'Code Omitted  
<DataContract()>  
<KnownType(GetType(Book))>  
<KnownType(GetType(Magazine))>  
Public Class LibraryItem  
  'Code Omitted  
End Class  
```  
  
 <span data-ttu-id="0eee0-181">使用 <xref:System.Xml.Serialization.XmlIncludeAttribute> 时，可以使用 <xref:System.Xml.Serialization.XmlSerializer> 属性。</span><span class="sxs-lookup"><span data-stu-id="0eee0-181">You can use the <xref:System.Xml.Serialization.XmlIncludeAttribute> attribute when using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
 <span data-ttu-id="0eee0-182">可以将 <xref:System.ServiceModel.ServiceKnownTypeAttribute> 属性应用于某个操作或整个服务。</span><span class="sxs-lookup"><span data-stu-id="0eee0-182">You can apply the <xref:System.ServiceModel.ServiceKnownTypeAttribute> attribute to an operation or to the entire service.</span></span> <span data-ttu-id="0eee0-183">它接受一个类型或要调用的方法的名称，以获取已知类型的列表，就像 <xref:System.Runtime.Serialization.KnownTypeAttribute> 属性一样。</span><span class="sxs-lookup"><span data-stu-id="0eee0-183">It accepts either a type or the name of the method to call to get a list of known types, just like the <xref:System.Runtime.Serialization.KnownTypeAttribute> attribute.</span></span> <span data-ttu-id="0eee0-184">有关详细信息，请参阅[Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)。</span><span class="sxs-lookup"><span data-stu-id="0eee0-184">For more information, see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="specifying-the-use-and-style"></a><span data-ttu-id="0eee0-185">指定用法和样式</span><span class="sxs-lookup"><span data-stu-id="0eee0-185">Specifying the Use and Style</span></span>  
 <span data-ttu-id="0eee0-186">在使用 Web Services 描述语言 (WSDL) 描述服务时，两种常用的样式是文档和远程过程调用 (RPC)。</span><span class="sxs-lookup"><span data-stu-id="0eee0-186">When describing services using Web Services Description Language (WSDL), the two commonly used styles are Document and remote procedure call (RPC).</span></span> <span data-ttu-id="0eee0-187">在文档样式中，使用架构来描述整个消息正文，并且 WSDL 通过引用该架构内的元素来描述各种消息正文部分。</span><span class="sxs-lookup"><span data-stu-id="0eee0-187">In the Document style, the entire message body is described using the schema, and the WSDL describes the various message body parts by referring to elements within that schema.</span></span> <span data-ttu-id="0eee0-188">在 RPC 样式中，WSDL 引用每个消息部分的架构类型而不是元素来描述消息正文部分。</span><span class="sxs-lookup"><span data-stu-id="0eee0-188">In the RPC style, the WSDL refers to a schema type for each message part rather than an element.</span></span> <span data-ttu-id="0eee0-189">在某些情况下，您必须手动选择其中的一种样式。</span><span class="sxs-lookup"><span data-stu-id="0eee0-189">In some cases, you have to manually select one of these styles.</span></span> <span data-ttu-id="0eee0-190">若要执行此操作，可以应用 <xref:System.ServiceModel.DataContractFormatAttribute> 属性并设置 `Style` 属性 (Property)（使用 <xref:System.Runtime.Serialization.DataContractSerializer> 时），或者设置 `Style` 属性 (Attribute) 上的 <xref:System.ServiceModel.XmlSerializerFormatAttribute>（使用 <xref:System.Xml.Serialization.XmlSerializer> 时）。</span><span class="sxs-lookup"><span data-stu-id="0eee0-190">You can do this by applying the <xref:System.ServiceModel.DataContractFormatAttribute> attribute and setting the `Style` property (when the <xref:System.Runtime.Serialization.DataContractSerializer> is in use), or by setting `Style` on the <xref:System.ServiceModel.XmlSerializerFormatAttribute> attribute (when using the <xref:System.Xml.Serialization.XmlSerializer>).</span></span>  
  
 <span data-ttu-id="0eee0-191">此外，<xref:System.Xml.Serialization.XmlSerializer> 还支持两种形式的序列化 XML：`Literal` 和 `Encoded`。</span><span class="sxs-lookup"><span data-stu-id="0eee0-191">Additionally, the <xref:System.Xml.Serialization.XmlSerializer> supports two forms of serialized XML: `Literal` and `Encoded`.</span></span> <span data-ttu-id="0eee0-192">`Literal` 是最广为接受的格式，也是 <xref:System.Runtime.Serialization.DataContractSerializer> 唯一支持的格式。</span><span class="sxs-lookup"><span data-stu-id="0eee0-192">`Literal` is the most commonly accepted form, and is the only form the <xref:System.Runtime.Serialization.DataContractSerializer> supports.</span></span> <span data-ttu-id="0eee0-193">`Encoded` 是 SOAP 规范第 5 节中描述的旧格式，建议不要用于新服务。</span><span class="sxs-lookup"><span data-stu-id="0eee0-193">`Encoded` is a legacy form described in section 5 of the SOAP specification, and is not recommended for new services.</span></span> <span data-ttu-id="0eee0-194">若要切换到 `Encoded` 模式，请将 `Use` 属性 (Attribute) 上的 <xref:System.ServiceModel.XmlSerializerFormatAttribute> 属性 (Property) 设置为 `Encoded`。</span><span class="sxs-lookup"><span data-stu-id="0eee0-194">To switch to `Encoded` mode, set the `Use` property on the <xref:System.ServiceModel.XmlSerializerFormatAttribute> attribute to `Encoded`.</span></span>  
  
 <span data-ttu-id="0eee0-195">在大多数情况下，不应更改 `Style` 和 `Use` 属性的默认设置。</span><span class="sxs-lookup"><span data-stu-id="0eee0-195">In most cases, you should not change the default settings for the `Style` and `Use` properties.</span></span>  
  
## <a name="controlling-the-serialization-process"></a><span data-ttu-id="0eee0-196">控制序列化过程</span><span class="sxs-lookup"><span data-stu-id="0eee0-196">Controlling the Serialization Process</span></span>  
 <span data-ttu-id="0eee0-197">可以执行许多操作来自定义序列化数据的方式。</span><span class="sxs-lookup"><span data-stu-id="0eee0-197">You can do a number of things to customize the way data is serialized.</span></span>  
  
### <a name="changing-server-serialization-settings"></a><span data-ttu-id="0eee0-198">更改服务器序列化设置</span><span class="sxs-lookup"><span data-stu-id="0eee0-198">Changing Server Serialization Settings</span></span>  
 <span data-ttu-id="0eee0-199">当使用默认 <xref:System.Runtime.Serialization.DataContractSerializer> 时，可以通过将 <xref:System.ServiceModel.ServiceBehaviorAttribute> 属性应用于服务，控制服务上的序列化过程的某些方面。</span><span class="sxs-lookup"><span data-stu-id="0eee0-199">When the default <xref:System.Runtime.Serialization.DataContractSerializer> is in use, you can control some aspects of the serialization process on the service by applying the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to the service.</span></span> <span data-ttu-id="0eee0-200">具体说来，您可以使用 `MaxItemsInObjectGraph` 属性设置相应的配额，以便对 <xref:System.Runtime.Serialization.DataContractSerializer> 反序列化的最大对象数进行限制。</span><span class="sxs-lookup"><span data-stu-id="0eee0-200">Specifically, you may use the `MaxItemsInObjectGraph` property to set the quota that limits the maximum number of objects the <xref:System.Runtime.Serialization.DataContractSerializer> deserializes.</span></span> <span data-ttu-id="0eee0-201">可以使用 `IgnoreExtensionDataObject` 属性关闭往返过程版本管理功能。</span><span class="sxs-lookup"><span data-stu-id="0eee0-201">You can use the `IgnoreExtensionDataObject` property to turn off the round-tripping versioning feature.</span></span> <span data-ttu-id="0eee0-202">有关配额的详细信息，请参阅[数据的安全注意事项](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)。</span><span class="sxs-lookup"><span data-stu-id="0eee0-202">For more information about quotas, see [Security Considerations for Data](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).</span></span> <span data-ttu-id="0eee0-203">关于往返过程的详细信息，请参阅[向前兼容的数据协定](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="0eee0-203">For more information about round-tripping, see [Forward-Compatible Data Contracts](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).</span></span>  
  
```csharp  
[ServiceBehavior(MaxItemsInObjectGraph=100000)]  
public class MyDataService:IDataService  
{  
    public DataPoint[] GetData()  
    {  
       // Implementation omitted  
    }  
}  
```  
  
```vb  
<ServiceBehavior(MaxItemsInObjectGraph:=100000)>  
Public Class MyDataService Implements IDataService  
  
    Function GetData() As DataPoint()  
         ‘ Implementation omitted  
    End Function  
End Interface  
```  
  
### <a name="serialization-behaviors"></a><span data-ttu-id="0eee0-204">序列化行为</span><span class="sxs-lookup"><span data-stu-id="0eee0-204">Serialization Behaviors</span></span>  
 <span data-ttu-id="0eee0-205">在 WCF 中，提供了两种行为<xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>和<xref:System.ServiceModel.Description.XmlSerializerOperationBehavior>自动插入，取决于哪个序列化程序正在使用特定的操作。</span><span class="sxs-lookup"><span data-stu-id="0eee0-205">Two behaviors are available in WCF, the <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> and the <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> that are automatically plugged in depending on which serializer is in use for a particular operation.</span></span> <span data-ttu-id="0eee0-206">因为这些行为是自动应用的，您通常不必了解它们。</span><span class="sxs-lookup"><span data-stu-id="0eee0-206">Because these behaviors are applied automatically, you normally do not have to be aware of them.</span></span>  
  
 <span data-ttu-id="0eee0-207">但是，`DataContractSerializerOperationBehavior` 具有可用于自定义序列化过程的 `MaxItemsInObjectGraph`、`IgnoreExtensionDataObject` 和 `DataContractSurrogate` 属性。</span><span class="sxs-lookup"><span data-stu-id="0eee0-207">However, the `DataContractSerializerOperationBehavior` has the `MaxItemsInObjectGraph`, `IgnoreExtensionDataObject`, and `DataContractSurrogate` properties that you may use to customize the serialization process.</span></span> <span data-ttu-id="0eee0-208">前两个属性的含义与上一节中讨论的相同。</span><span class="sxs-lookup"><span data-stu-id="0eee0-208">The first two properties have the same meaning as discussed in the previous section.</span></span> <span data-ttu-id="0eee0-209">您可以使用 `DataContractSurrogate` 属性来启用数据协定代理项，这是一种用于自定义和扩展序列化过程的强大机制。</span><span class="sxs-lookup"><span data-stu-id="0eee0-209">You can use the `DataContractSurrogate` property to enable data contract surrogates, which are a powerful mechanism for customizing and extending the serialization process.</span></span> <span data-ttu-id="0eee0-210">有关详细信息，请参阅[数据协定代理项](../../../../docs/framework/wcf/extending/data-contract-surrogates.md)。</span><span class="sxs-lookup"><span data-stu-id="0eee0-210">For more information, see [Data Contract Surrogates](../../../../docs/framework/wcf/extending/data-contract-surrogates.md).</span></span>  
  
 <span data-ttu-id="0eee0-211">可以使用 `DataContractSerializerOperationBehavior` 来自定义客户端和服务器序列化。</span><span class="sxs-lookup"><span data-stu-id="0eee0-211">You can use the `DataContractSerializerOperationBehavior` to customize both client and server serialization.</span></span> <span data-ttu-id="0eee0-212">下面的示例演示如何增加客户端上的 `MaxItemsInObjectGraph` 配额。</span><span class="sxs-lookup"><span data-stu-id="0eee0-212">The following example shows how to increase the `MaxItemsInObjectGraph` quota on the client.</span></span>  
  
```csharp  
ChannelFactory<IDataService> factory = new ChannelFactory<IDataService>(binding, address);  
foreach (OperationDescription op in factory.Endpoint.Contract.Operations)  
{  
    DataContractSerializerOperationBehavior dataContractBehavior =  
                op.Behaviors.Find<DataContractSerializerOperationBehavior>()  
                as DataContractSerializerOperationBehavior;  
    if (dataContractBehavior != null)  
    {  
        dataContractBehavior.MaxItemsInObjectGraph = 100000;  
    }  
}  
IDataService client = factory.CreateChannel();  
```  
  
```vb  
Dim factory As ChannelFactory(Of IDataService) = New ChannelFactory(Of IDataService)(binding, address)  
For Each op As OperationDescription In factory.Endpoint.Contract.Operations  
        Dim dataContractBehavior As DataContractSerializerOperationBehavior = op.Behaviors.Find(Of DataContractSerializerOperationBehavior)()  
        If dataContractBehavior IsNot Nothing Then  
            dataContractBehavior.MaxItemsInObjectGraph = 100000  
        End If  
     Next  
    Dim client As IDataService = factory.CreateChannel  
```  
  
 <span data-ttu-id="0eee0-213">下面的代码是自承载服务上的等效代码。</span><span class="sxs-lookup"><span data-stu-id="0eee0-213">Following is the equivalent code on the service, in the self-hosted case.</span></span>  
  
```csharp  
ServiceHost serviceHost = new ServiceHost(typeof(IDataService))  
foreach (ServiceEndpoint ep in serviceHost.Description.Endpoints)  
{  
foreach (OperationDescription op in ep.Contract.Operations)  
{  
        DataContractSerializerOperationBehavior dataContractBehavior =  
           op.Behaviors.Find<DataContractSerializerOperationBehavior>()  
                as DataContractSerializerOperationBehavior;  
        if (dataContractBehavior != null)  
        {  
            dataContractBehavior.MaxItemsInObjectGraph = 100000;  
        }  
}  
}  
serviceHost.Open();  
```  
  
```vb  
Dim serviceHost As ServiceHost = New ServiceHost(GetType(IDataService))  
        For Each ep As ServiceEndpoint In serviceHost.Description.Endpoints  
            For Each op As OperationDescription In ep.Contract.Operations  
                Dim dataContractBehavior As DataContractSerializerOperationBehavior = op.Behaviors.Find(Of DataContractSerializerOperationBehavior)()  
  
                If dataContractBehavior IsNot Nothing Then  
                    dataContractBehavior.MaxItemsInObjectGraph = 100000  
                End If  
            Next  
        Next  
        serviceHost.Open()  
```  
  
 <span data-ttu-id="0eee0-214">在以 Web 为宿主的情况下，必须创建一个新的 `ServiceHost` 派生类，并且使用服务主机工厂来插入该类。</span><span class="sxs-lookup"><span data-stu-id="0eee0-214">In the Web-hosted case, you must create a new `ServiceHost` derived class and use a service host factory to plug it in.</span></span>  
  
### <a name="controlling-serialization-settings-in-configuration"></a><span data-ttu-id="0eee0-215">在配置中控制序列化设置</span><span class="sxs-lookup"><span data-stu-id="0eee0-215">Controlling Serialization Settings in Configuration</span></span>  
 <span data-ttu-id="0eee0-216">使用 `MaxItemsInObjectGraph` 终结点或服务行为，可以通过配置来控制 `IgnoreExtensionDataObject` 和 `dataContractSerializer`，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="0eee0-216">The `MaxItemsInObjectGraph` and `IgnoreExtensionDataObject` can be controlled through configuration by using the `dataContractSerializer` endpoint or service behavior, as shown in the following example.</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="LargeQuotaBehavior">  
                    <dataContractSerializer  
                      maxItemsInObjectGraph="100000" />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
        <client>  
            <endpoint address="http://example.com/myservice"  
                  behaviorConfiguration="LargeQuotaBehavior"  
                binding="basicHttpBinding" bindingConfiguration=""   
                            contract="IDataService"  
                name="" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="shared-type-serialization-object-graph-preservation-and-custom-serializers"></a><span data-ttu-id="0eee0-217">共享类型序列化、对象图保留和自定义序列化程序</span><span class="sxs-lookup"><span data-stu-id="0eee0-217">Shared Type Serialization, Object Graph Preservation, and Custom Serializers</span></span>  
 <span data-ttu-id="0eee0-218"><xref:System.Runtime.Serialization.DataContractSerializer> 使用数据协定名称而不是 .NET 类型名称序列化。</span><span class="sxs-lookup"><span data-stu-id="0eee0-218">The <xref:System.Runtime.Serialization.DataContractSerializer> serializes using data contract names and not .NET type names.</span></span> <span data-ttu-id="0eee0-219">这与面向服务的体系结构原则是一致的，并且支持更大程度的灵活性 — .NET 类型可以在不影响网络协定的情况下进行更改。</span><span class="sxs-lookup"><span data-stu-id="0eee0-219">This is consistent with service-oriented architecture tenets and allows for a great degree of flexibility—the .NET types can change without affecting the wire contract.</span></span> <span data-ttu-id="0eee0-220">在极少数情况下，您可能希望序列化实际的 .NET 类型名称，从而在客户端和服务器之间引入紧耦合，就像 .NET Framework 远程处理技术那样。</span><span class="sxs-lookup"><span data-stu-id="0eee0-220">In rare cases, you may want to serialize actual .NET type names, thereby introducing a tight coupling between the client and the server, similar to the .NET Framework remoting technology.</span></span> <span data-ttu-id="0eee0-221">这不是建议的做法，除在极少数情况下，通常会发生时从.NET Framework 远程处理迁移到 WCF。</span><span class="sxs-lookup"><span data-stu-id="0eee0-221">This is not a recommended practice, except in rare cases that usually occur when migrating to WCF from .NET Framework remoting.</span></span> <span data-ttu-id="0eee0-222">在这种情况下，必须使用 <xref:System.Runtime.Serialization.NetDataContractSerializer> 类而不是 <xref:System.Runtime.Serialization.DataContractSerializer> 类。</span><span class="sxs-lookup"><span data-stu-id="0eee0-222">In this case, you must use the <xref:System.Runtime.Serialization.NetDataContractSerializer> class instead of the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span>  
  
 <span data-ttu-id="0eee0-223"><xref:System.Runtime.Serialization.DataContractSerializer> 通常按对象树形式序列化对象图。</span><span class="sxs-lookup"><span data-stu-id="0eee0-223">The <xref:System.Runtime.Serialization.DataContractSerializer> normally serializes object graphs as object trees.</span></span> <span data-ttu-id="0eee0-224">即，如果多次引用同一个对象，则会将该对象序列化多次。</span><span class="sxs-lookup"><span data-stu-id="0eee0-224">That is, if the same object is referred to more than once, it is serialized more than once.</span></span> <span data-ttu-id="0eee0-225">例如，考虑一个 `PurchaseOrder` 实例，它有两个名为 `billTo` 和 `shipTo` 的 Address 类型的字段。</span><span class="sxs-lookup"><span data-stu-id="0eee0-225">For example, consider a `PurchaseOrder` instance that has two fields of type Address called `billTo` and `shipTo`.</span></span> <span data-ttu-id="0eee0-226">如果这两个字段设置为同一个 Address 实例，那么在序列化和反序列化后将有两个相同的 Address 实例。</span><span class="sxs-lookup"><span data-stu-id="0eee0-226">If both fields are set to the same Address instance, there are two identical Address instances after serialization and deserialization.</span></span> <span data-ttu-id="0eee0-227">这样做的原因是 XML 中没有用于表示对象图的标准且可互操作的方式（<xref:System.Xml.Serialization.XmlSerializer> 上可用的旧 SOAP 编码标准除外，如上一节中关于 `Style` 和 `Use` 的介绍中所述）。</span><span class="sxs-lookup"><span data-stu-id="0eee0-227">This is done because there is no standard interoperable way to represent object graphs in XML (except for the legacy SOAP encoded standard available on the <xref:System.Xml.Serialization.XmlSerializer>, as described in the previous section on `Style` and `Use`).</span></span> <span data-ttu-id="0eee0-228">按对象树形式序列化对象图具有某些缺点，例如：无法序列化含有循环引用的图。</span><span class="sxs-lookup"><span data-stu-id="0eee0-228">Serializing object graphs as trees has certain disadvantages, for example, graphs with circular references cannot be serialized.</span></span> <span data-ttu-id="0eee0-229">有时，需要切换到真正的对象图序列化，即使它不是可互操作的。</span><span class="sxs-lookup"><span data-stu-id="0eee0-229">Occasionally, it is necessary to switch to true object graph serialization, even though it is not interoperable.</span></span> <span data-ttu-id="0eee0-230">这可以通过使用在将 <xref:System.Runtime.Serialization.DataContractSerializer> 参数设置为 `preserveObjectReferences` 的情况下构造的 `true` 来完成。</span><span class="sxs-lookup"><span data-stu-id="0eee0-230">This can be done by using the <xref:System.Runtime.Serialization.DataContractSerializer> constructed with the `preserveObjectReferences` parameter set to `true`.</span></span>  
  
 <span data-ttu-id="0eee0-231">有时，内置序列化程序不足以满足方案的需要。</span><span class="sxs-lookup"><span data-stu-id="0eee0-231">Occasionally, the built-in serializers are not enough for your scenario.</span></span> <span data-ttu-id="0eee0-232">在大多数情况下，仍可使用用来派生 <xref:System.Runtime.Serialization.XmlObjectSerializer> 和 <xref:System.Runtime.Serialization.DataContractSerializer> 的 <xref:System.Runtime.Serialization.NetDataContractSerializer> 抽象类。</span><span class="sxs-lookup"><span data-stu-id="0eee0-232">In most cases, you can still use the <xref:System.Runtime.Serialization.XmlObjectSerializer> abstraction from which both the <xref:System.Runtime.Serialization.DataContractSerializer> and the <xref:System.Runtime.Serialization.NetDataContractSerializer> derive.</span></span>  
  
 <span data-ttu-id="0eee0-233">前面的三种情况（.NET 类型保留、对象图保留和完全基于 `XmlObjectSerializer` 的自定义序列化）都需要插入一个自定义序列化程序。</span><span class="sxs-lookup"><span data-stu-id="0eee0-233">The previous three cases (.NET type preservation, object graph preservation, and completely custom `XmlObjectSerializer`-based serialization) all require a custom serializer be plugged in.</span></span> <span data-ttu-id="0eee0-234">为此，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="0eee0-234">To do this, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="0eee0-235">编写自己的派生自 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> 的行为。</span><span class="sxs-lookup"><span data-stu-id="0eee0-235">Write your own behavior deriving from the <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>.</span></span>  
  
2.  <span data-ttu-id="0eee0-236">重写两个 `CreateSerializer` 方法以返回自己的序列化程序（<xref:System.Runtime.Serialization.NetDataContractSerializer>、将 <xref:System.Runtime.Serialization.DataContractSerializer> 设置为 `preserveObjectReferences` 的 `true` 或自己的自定义 <xref:System.Runtime.Serialization.XmlObjectSerializer>）。</span><span class="sxs-lookup"><span data-stu-id="0eee0-236">Override the two `CreateSerializer` methods to return your own serializer (either the <xref:System.Runtime.Serialization.NetDataContractSerializer>, the <xref:System.Runtime.Serialization.DataContractSerializer> with `preserveObjectReferences` set to `true`, or your own custom <xref:System.Runtime.Serialization.XmlObjectSerializer>).</span></span>  
  
3.  <span data-ttu-id="0eee0-237">在打开服务主机或创建客户端通道之前，移除现有的 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> 行为并插入在前面的步骤中创建的自定义派生类。</span><span class="sxs-lookup"><span data-stu-id="0eee0-237">Before opening the service host or creating a client channel, remove the existing <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> behavior and plug in the custom derived class that you created in the previous steps.</span></span>  
  
 <span data-ttu-id="0eee0-238">有关高级序列化概念的详细信息，请参阅[序列化和反序列化](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)。</span><span class="sxs-lookup"><span data-stu-id="0eee0-238">For more information about advanced serialization concepts, see [Serialization and Deserialization](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eee0-239">请参阅</span><span class="sxs-lookup"><span data-stu-id="0eee0-239">See also</span></span>
- [<span data-ttu-id="0eee0-240">使用 XmlSerializer 类</span><span class="sxs-lookup"><span data-stu-id="0eee0-240">Using the XmlSerializer Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)
- [<span data-ttu-id="0eee0-241">如何：启用流式传输</span><span class="sxs-lookup"><span data-stu-id="0eee0-241">How to: Enable Streaming</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-streaming.md)
- [<span data-ttu-id="0eee0-242">如何：创建类或结构的基本数据协定</span><span class="sxs-lookup"><span data-stu-id="0eee0-242">How to: Create a Basic Data Contract for a Class or Structure</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-data-contract-for-a-class-or-structure.md)
