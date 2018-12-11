---
title: 自定义消息编码器：自定义文本编码器
ms.date: 03/30/2017
ms.assetid: 68ff5c74-3d33-4b44-bcae-e1d2f5dea0de
ms.openlocfilehash: 39f09fd2ca58bfe7eb38afe536194ecad104d394
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236539"
---
# <a name="custom-message-encoder-custom-text-encoder"></a><span data-ttu-id="2e4ff-102">自定义消息编码器：自定义文本编码器</span><span class="sxs-lookup"><span data-stu-id="2e4ff-102">Custom Message Encoder: Custom Text Encoder</span></span>
<span data-ttu-id="2e4ff-103">此示例演示如何实现自定义文本消息编码器使用 Windows Communication Foundation (WCF)。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-103">This sample demonstrates how to implement a custom text message encoder using Windows Communication Foundation (WCF).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="2e4ff-104">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-104">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2e4ff-105">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="2e4ff-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2e4ff-106">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2e4ff-107">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="2e4ff-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageEncoder\Text`  
  
 <span data-ttu-id="2e4ff-108"><xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> WCF 的支持仅 utf-8、 UTF-16 和 Big Endean Unicode 编码。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-108">The <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> of WCF supports only the UTF-8, UTF-16 and Big Endean Unicode encodings.</span></span> <span data-ttu-id="2e4ff-109">本示例中的自定义文本消息编码器支持所有平台支持的字符编码，这可能是互操作性所要求的。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-109">The custom text message encoder in this sample supports all platform-supported character encoding that may be required for interoperability.</span></span> <span data-ttu-id="2e4ff-110">本示例包括客户端控制台程序 (.exe)、Internet 信息服务 (IIS) 承载的服务库 (.dll) 和文本消息编码器库 (.dll)。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-110">The sample consists of a client console program (.exe), a service library (.dll) hosted by Internet Information Services (IIS) and a text message encoder library (.dll).</span></span> <span data-ttu-id="2e4ff-111">该服务实现定义“请求-答复”通信模式的协定。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-111">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="2e4ff-112">该协定由 `ICalculator` 接口定义，该接口公开数学运算（加、减、乘和除）。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-112">The contract is defined by the `ICalculator` interface, which exposes math operations (Add, Subtract, Multiply, and Divide).</span></span> <span data-ttu-id="2e4ff-113">客户端向给定的数学运算发出同步请求，服务使用结果进行回复。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-113">The client makes synchronous requests to a given math operation and the service replies with the result.</span></span> <span data-ttu-id="2e4ff-114">客户端和服务都使用 `CustomTextMessageEncoder`，而不是使用默认的 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-114">Both client and service uses the `CustomTextMessageEncoder` instead of the default <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span></span>  
  
 <span data-ttu-id="2e4ff-115">自定义编码器实现由消息编码器工厂、消息编码器、消息编码绑定元素和配置处理程序组成，演示如下：</span><span class="sxs-lookup"><span data-stu-id="2e4ff-115">The custom encoder implementation consists of a message encoder factory, a message encoder, a message encoding binding element and a configuration handler, and demonstrates the following:</span></span>  
  
-   <span data-ttu-id="2e4ff-116">生成自定义编码器和编码器工厂。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-116">Building a custom encoder and encoder factory.</span></span>  
  
-   <span data-ttu-id="2e4ff-117">为自定义编码器创建绑定元素。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-117">Creating a binding element for a custom encoder.</span></span>  
  
-   <span data-ttu-id="2e4ff-118">使用自定义绑定配置集成自定义绑定元素。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-118">Using the custom binding configuration for integrating custom binding elements.</span></span>  
  
-   <span data-ttu-id="2e4ff-119">开发自定义配置处理程序以允许对自定义绑定元素进行文件配置。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-119">Developing a custom configuration handler to allow file configuration of a custom binding element.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2e4ff-120">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="2e4ff-120">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2e4ff-121">使用以下命令安装 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-121">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="2e4ff-122">请确保您具有执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-122">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="2e4ff-123">若要生成解决方案，请按照中的说明[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-123">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="2e4ff-124">若要在单或跨计算机配置中运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-124">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="message-encoder-factory-and-the-message-encoder"></a><span data-ttu-id="2e4ff-125">消息编码器工厂和消息编码器</span><span class="sxs-lookup"><span data-stu-id="2e4ff-125">Message Encoder Factory and the Message Encoder</span></span>  
 <span data-ttu-id="2e4ff-126">当 <xref:System.ServiceModel.ServiceHost> 或客户端通道打开时，设计时组件 `CustomTextMessageBindingElement` 可创建 `CustomTextMessageEncoderFactory`。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-126">When the <xref:System.ServiceModel.ServiceHost> or the client channel is opened, the design time component `CustomTextMessageBindingElement` creates the `CustomTextMessageEncoderFactory`.</span></span> <span data-ttu-id="2e4ff-127">该工厂创建 `CustomTextMessageEncoder`。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-127">The factory creates the `CustomTextMessageEncoder`.</span></span> <span data-ttu-id="2e4ff-128">消息编码器运行在流模式和缓冲模式中。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-128">The message encoder operates both in the streaming mode and the buffered mode.</span></span> <span data-ttu-id="2e4ff-129">它分别使用 <xref:System.Xml.XmlReader> 和 <xref:System.Xml.XmlWriter> 读写消息。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-129">It uses the <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter> to read and write the messages respectively.</span></span> <span data-ttu-id="2e4ff-130">而不是优化的 XML 读取器和 WCF 的编写器支持 utf-8、 UTF-16 和 Big-endean Unicode 这些读取器和编写器支持所有平台支持编码。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-130">As opposed to the optimized XML readers and writers of WCF that support only UTF-8, UTF-16 and Big-Endean Unicode these readers and writers support all platform supported encoding.</span></span>  
  
 <span data-ttu-id="2e4ff-131">下面的代码示例演示 CustomTextMessageEncoder。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-131">The following code example shows the CustomTextMessageEncoder.</span></span>  
  
```csharp  
public class CustomTextMessageEncoder : MessageEncoder  
{  
    private CustomTextMessageEncoderFactory factory;  
    private XmlWriterSettings writerSettings;  
    private string contentType;  
  
    public CustomTextMessageEncoder(CustomTextMessageEncoderFactory factory)  
    {  
        this.factory = factory;  
  
        this.writerSettings = new XmlWriterSettings();  
        this.writerSettings.Encoding = Encoding.GetEncoding(factory.CharSet);  
        this.contentType = $"{this.factory.MediaType}; charset={this.writerSettings.Encoding.HeaderName}";
    }  
  
    public override string ContentType  
    {  
        get  
        {  
            return this.contentType;  
        }  
    }  
  
    public override string MediaType  
    {  
        get   
        {  
            return factory.MediaType;  
        }  
    }  
  
    public override MessageVersion MessageVersion  
    {  
        get   
        {  
            return this.factory.MessageVersion;  
        }  
    }  
  
    public override Message ReadMessage(ArraySegment<byte> buffer, BufferManager bufferManager, string contentType)  
    {     
        byte[] msgContents = new byte[buffer.Count];  
        Array.Copy(buffer.Array, buffer.Offset, msgContents, 0, msgContents.Length);  
        bufferManager.ReturnBuffer(buffer.Array);  
  
        MemoryStream stream = new MemoryStream(msgContents);  
        return ReadMessage(stream, int.MaxValue);  
    }  
  
    public override Message ReadMessage(Stream stream, int maxSizeOfHeaders, string contentType)  
    {  
        XmlReader reader = XmlReader.Create(stream);  
        return Message.CreateMessage(reader, maxSizeOfHeaders, this.MessageVersion);  
    }  
  
    public override ArraySegment<byte> WriteMessage(Message message, int maxMessageSize, BufferManager bufferManager, int messageOffset)  
    {  
        MemoryStream stream = new MemoryStream();  
        XmlWriter writer = XmlWriter.Create(stream, this.writerSettings);  
        message.WriteMessage(writer);  
        writer.Close();  
  
        byte[] messageBytes = stream.GetBuffer();  
        int messageLength = (int)stream.Position;  
        stream.Close();  
  
        int totalLength = messageLength + messageOffset;  
        byte[] totalBytes = bufferManager.TakeBuffer(totalLength);  
        Array.Copy(messageBytes, 0, totalBytes, messageOffset, messageLength);  
  
        ArraySegment<byte> byteArray = new ArraySegment<byte>(totalBytes, messageOffset, messageLength);  
        return byteArray;  
    }  
  
    public override void WriteMessage(Message message, Stream stream)  
    {  
        XmlWriter writer = XmlWriter.Create(stream, this.writerSettings);  
        message.WriteMessage(writer);  
        writer.Close();  
    }  
}  
```  
  
 <span data-ttu-id="2e4ff-132">下面的代码示例演示如何生成消息编码器工厂。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-132">The following code example shows how to build the message encoder factory.</span></span>  
  
```csharp  
public class CustomTextMessageEncoderFactory : MessageEncoderFactory  
{  
    private MessageEncoder encoder;  
    private MessageVersion version;  
    private string mediaType;  
    private string charSet;  
  
    internal CustomTextMessageEncoderFactory(string mediaType, string charSet,  
        MessageVersion version)  
    {  
        this.version = version;  
        this.mediaType = mediaType;  
        this.charSet = charSet;  
        this.encoder = new CustomTextMessageEncoder(this);  
    }  
  
    public override MessageEncoder Encoder  
    {  
        get   
        {   
            return this.encoder;  
        }  
    }  
  
    public override MessageVersion MessageVersion  
    {  
        get   
        {   
            return this.version;  
        }  
    }  
  
    internal string MediaType  
    {  
        get  
        {  
            return this.mediaType;  
        }  
    }  
  
    internal string CharSet  
    {  
        get  
        {  
            return this.charSet;  
        }  
    }  
}  
```  
  
## <a name="message-encoding-binding-element"></a><span data-ttu-id="2e4ff-133">消息编码绑定元素</span><span class="sxs-lookup"><span data-stu-id="2e4ff-133">Message Encoding Binding Element</span></span>  
 <span data-ttu-id="2e4ff-134">绑定元素允许 WCF 运行时堆栈的配置。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-134">The binding elements allow the configuration of the WCF run-time stack.</span></span> <span data-ttu-id="2e4ff-135">若要在 WCF 应用程序中使用自定义消息编码器，绑定元素是必需的运行时堆栈中的相应级别的相应设置创建消息编码器工厂。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-135">To use the custom message encoder in a WCF application, a binding element is required that creates the message encoder factory with the appropriate settings at the appropriate level in the run-time stack.</span></span>  
  
 <span data-ttu-id="2e4ff-136">`CustomTextMessageBindingElement` 从 <xref:System.ServiceModel.Channels.BindingElement> 基类派生并从 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> 类继承。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-136">The `CustomTextMessageBindingElement` derives from the <xref:System.ServiceModel.Channels.BindingElement> base class and inherits from the <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> class.</span></span> <span data-ttu-id="2e4ff-137">这允许其他 WCF 组件此绑定元素识别为消息编码绑定元素。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-137">This allows other WCF components to recognize this binding element as being a message encoding binding element.</span></span> <span data-ttu-id="2e4ff-138"><xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A> 的实现返回与相应设置匹配的消息编码器工厂的实例。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-138">The implementation of <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A> returns an instance of the matching message encoder factory with appropriate settings.</span></span>  
  
 <span data-ttu-id="2e4ff-139">`CustomTextMessageBindingElement` 通过属性公开 `MessageVersion`、`ContentType` 和 `Encoding` 的设置。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-139">The `CustomTextMessageBindingElement` exposes settings for `MessageVersion`, `ContentType`, and `Encoding` through properties.</span></span> <span data-ttu-id="2e4ff-140">编码器支持 Soap11Addressing 和 Soap12Addressing1 版本。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-140">The encoder supports both Soap11Addressing and Soap12Addressing1 versions.</span></span> <span data-ttu-id="2e4ff-141">默认值为 Soap11Addressing1。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-141">The default is Soap11Addressing1.</span></span> <span data-ttu-id="2e4ff-142">`ContentType` 的默认值为“text/xml”。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-142">The default value of the `ContentType` is "text/xml".</span></span> <span data-ttu-id="2e4ff-143">使用 `Encoding` 属性可以将该值设置为所需的字符编码。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-143">The `Encoding` property allows you to set the value of the desired character encoding.</span></span> <span data-ttu-id="2e4ff-144">示例客户端和服务使用的 ISO-8859-1 (Latin1) 字符编码，这不支持的<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>的 WCF。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-144">The sample client and service uses the ISO-8859-1 (Latin1) character encoding, which is not supported by the <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> of WCF.</span></span>  
  
 <span data-ttu-id="2e4ff-145">下面的代码演示如何使用自定义文本消息编码器以编程方式创建绑定。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-145">The following code shows how to programmatically create the binding using the custom text message encoder.</span></span>  
  
```  
ICollection<BindingElement> bindingElements = new List<BindingElement>();  
HttpTransportBindingElement httpBindingElement = new HttpTransportBindingElement();  
CustomTextMessageBindingElement textBindingElement = new CustomTextMessageBindingElement();  
bindingElements.Add(textBindingElement);  
bindingElements.Add(httpBindingElement);  
CustomBinding binding = new CustomBinding(bindingElements);  
```  
  
## <a name="adding-metadata-support-to-the-message-encoding-binding-element"></a><span data-ttu-id="2e4ff-146">将元数据支持添加到消息编码绑定元素</span><span class="sxs-lookup"><span data-stu-id="2e4ff-146">Adding Metadata Support to the Message Encoding Binding Element</span></span>  
 <span data-ttu-id="2e4ff-147">从 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> 派生的任何类型负责更新为服务生成的 WSDL 文档中 SOAP 绑定的版本。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-147">Any type that derives from <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> is responsible for updating the version of the SOAP binding in the WSDL document generated for the service.</span></span> <span data-ttu-id="2e4ff-148">这是通过实现 `ExportEndpoint` 接口上的 <xref:System.ServiceModel.Description.IWsdlExportExtension> 方法，然后修改生成的 WSDL 来实现的。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-148">This is done by implementing the `ExportEndpoint` method on the <xref:System.ServiceModel.Description.IWsdlExportExtension> interface and then modifying the generated WSDL.</span></span> <span data-ttu-id="2e4ff-149">在本示例中，`CustomTextMessageBindingElement` 使用来自 `TextMessageEncodingBinidngElement` 的 WSDL 导出逻辑。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-149">In this sample, the `CustomTextMessageBindingElement` uses the WSDL export logic from the `TextMessageEncodingBinidngElement`.</span></span>  
  
 <span data-ttu-id="2e4ff-150">对于本示例，客户端配置是手动配置的。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-150">For this sample, the client configuration is hand configured.</span></span> <span data-ttu-id="2e4ff-151">无法使用 Svcutil.exe 生成客户端配置，因为 `CustomTextMessageBindingElement` 未导出策略断言来描述其行为。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-151">You cannot use Svcutil.exe to generate the client configuration because the `CustomTextMessageBindingElement` does not export a policy assertion to describe its behavior.</span></span> <span data-ttu-id="2e4ff-152">通常应该实现自定义绑定元素上的 <xref:System.ServiceModel.Description.IPolicyExportExtension> 接口，以导出描述绑定元素实现的行为或功能的自定义策略断言。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-152">You should generally implement the <xref:System.ServiceModel.Description.IPolicyExportExtension> interface on a custom binding element to export a custom policy assertion that describes the behavior or capability implemented by the binding element.</span></span> <span data-ttu-id="2e4ff-153">有关如何导出自定义绑定元素的策略断言的示例，请参阅[传输：UDP](../../../../docs/framework/wcf/samples/transport-udp.md)示例。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-153">For an example of how to export a policy assertion for a custom binding element, see the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
## <a name="message-encoding-binding-configuration-handler"></a><span data-ttu-id="2e4ff-154">消息编码绑定配置处理程序</span><span class="sxs-lookup"><span data-stu-id="2e4ff-154">Message Encoding Binding Configuration Handler</span></span>  
 <span data-ttu-id="2e4ff-155">上一节演示如何以编程方式使用自定义文本消息编码器。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-155">The previous section shows how to use the custom text message encoder programmatically.</span></span> <span data-ttu-id="2e4ff-156">`CustomTextMessageEncodingBindingSection` 实现配置处理程序，使用该程序可以在配置文件中指定自定义文本消息编码器的用法。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-156">The `CustomTextMessageEncodingBindingSection` implements a configuration handler that allows you to specify the use of a custom text message encoder within a configuration file.</span></span> <span data-ttu-id="2e4ff-157">`CustomTextMessageEncodingBindingSection` 类是从 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> 类派生的。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-157">The `CustomTextMessageEncodingBindingSection` class derives from the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> class.</span></span> <span data-ttu-id="2e4ff-158">`BindingElementType` 属性通知配置系统要为此节创建的绑定元素的类型。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-158">The `BindingElementType` property informs the configuration system of the type of binding element to create for this section.</span></span>  
  
 <span data-ttu-id="2e4ff-159">由 `CustomTextMessageBindingElement` 定义的所有设置作为 `CustomTextMessageEncodingBindingSection` 中的属性公开。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-159">All of the settings defined by `CustomTextMessageBindingElement` are exposed as the properties in the `CustomTextMessageEncodingBindingSection`.</span></span> <span data-ttu-id="2e4ff-160"><xref:System.Configuration.ConfigurationPropertyAttribute> 有助于将配置元素属性映射到属性并在未设置属性的情况下设置默认值。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-160">The <xref:System.Configuration.ConfigurationPropertyAttribute> assists in mapping the configuration element attributes to the properties and setting default values if the attribute is not set.</span></span> <span data-ttu-id="2e4ff-161">在配置中的值加载并应用到该类型的属性之后，将调用 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A> 方法，该方法将属性转换成绑定元素的具体实例。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-161">After the values from configuration are loaded and applied to the properties of the type, the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A> method is called, which converts the properties into a concrete instance of a binding element.</span></span>  
  
 <span data-ttu-id="2e4ff-162">此配置处理程序映射到服务或客户端的 App.config 或 Web.config 中的以下表示形式。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-162">This configuration handler maps to the following representation in the App.config or Web.config for the service or client.</span></span>  
  
```xml  
<customTextMessageEncoding encoding="utf-8" contentType="text/xml" messageVersion="Soap11Addressing1" />  
```  
  
 <span data-ttu-id="2e4ff-163">本示例使用 ISO-8859-1 编码。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-163">The sample uses the ISO-8859-1 encoding.</span></span>  
  
 <span data-ttu-id="2e4ff-164">若要使用此配置处理程序，它必须使用下面的配置元素注册。</span><span class="sxs-lookup"><span data-stu-id="2e4ff-164">To use this configuration handler it must be registered using the following configuration element.</span></span>  
  
```xml  
<extensions>  
    <bindingElementExtensions>  
        <add name="customTextMessageEncoding" type="   
Microsoft.ServiceModel.Samples.CustomTextMessageEncodingBindingSection,   
                  CustomTextMessageEncoder" />  
    </bindingElementExtensions>  
</extensions>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e4ff-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e4ff-165">See Also</span></span>
