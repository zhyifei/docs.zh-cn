---
title: "如何：使用 WCF REST 编程模型创建接受任意数据的服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e566c15a-b600-4e4a-be3a-4af43e767dae
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 170149f5a6c495b3f22b9fd30f79ecdda87789b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-service-that-accepts-arbitrary-data-using-the-wcf-rest-programming-model"></a><span data-ttu-id="0a9c2-102">如何：使用 WCF REST 编程模型创建接受任意数据的服务</span><span class="sxs-lookup"><span data-stu-id="0a9c2-102">How to: Create a Service That Accepts Arbitrary Data using the WCF REST Programming Model</span></span>
<span data-ttu-id="0a9c2-103">有时，开发人员必须完全控制从服务操作返回数据的方式。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-103">Sometimes developers must have full control of how data is returned from a service operation.</span></span> <span data-ttu-id="0a9c2-104">当服务操作必须以 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不支持的格式返回数据时，就需要这样做。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-104">This is the case when a service operation must return data in a format not supported by[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="0a9c2-105">本主题讨论如何使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] REST 编程模型创建接收任意数据的服务。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-105">This topic discusses using the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] REST Programming Model to create a service that receives arbitrary data.</span></span>  
  
### <a name="to-implement-the-service-contract"></a><span data-ttu-id="0a9c2-106">实现服务协定</span><span class="sxs-lookup"><span data-stu-id="0a9c2-106">To implement the service contract</span></span>  
  
1.  <span data-ttu-id="0a9c2-107">定义服务协定。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-107">Define the service contract.</span></span> <span data-ttu-id="0a9c2-108">接收任意数据的操作必须具有一个类型为 <xref:System.IO.Stream> 的参数。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-108">The operation that receives the arbitrary data must have a parameter of type <xref:System.IO.Stream>.</span></span> <span data-ttu-id="0a9c2-109">此外，此参数必须为传入请求正文的唯一参数。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-109">In addition, this parameter must be the only parameter passed in the body of the request.</span></span> <span data-ttu-id="0a9c2-110">本示例中介绍的操作还采用一个文件名参数。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-110">The operation described in this example also takes a filename parameter.</span></span> <span data-ttu-id="0a9c2-111">此参数在请求的 URL 中传递。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-111">This parameter is passed within the URL of the request.</span></span> <span data-ttu-id="0a9c2-112">通过在 <xref:System.UriTemplate> 中指定 <xref:System.ServiceModel.Web.WebInvokeAttribute> 可以指定在 URL 中传递参数。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-112">You can specify that a parameter is passed within the URL by specifying a <xref:System.UriTemplate> in the <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span></span> <span data-ttu-id="0a9c2-113">在此情况下，使用 URI 来调用此方法以"UploadFile/Some-filename"结尾。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-113">In this case the URI used to call this method ends in "UploadFile/Some-Filename".</span></span> <span data-ttu-id="0a9c2-114">URI 模板的"{filename}"部分指定操作的文件名参数用于调用操作的 URI 中传递。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-114">The "{filename}" portion of the URI template specifies that the filename parameter for the operation is passed within the URI used to call the operation.</span></span>  
  
    ```csharp  
     [ServiceContract]  
    public interface IReceiveData  
    {  
        [WebInvoke(UriTemplate = "UploadFile/{fileName}")]  
        void UploadFile(string fileName, Stream fileContents);  
    }  
    ```  
  
2.  <span data-ttu-id="0a9c2-115">实现服务协定。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-115">Implement the service contract.</span></span> <span data-ttu-id="0a9c2-116">该协定只有一个方法 `UploadFile`，该方法以流的形式接收包含任意数据的文件。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-116">The contract has only one method, `UploadFile` that receives a file of arbitrary data in a stream.</span></span> <span data-ttu-id="0a9c2-117">操作读取该数据流，同时对所读字节数进行计数，然后显示文件名和所读字节数。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-117">The operation reads the stream counting the number of bytes read and then displays the filename and the number of bytes read.</span></span>  
  
    ```csharp  
    public class RawDataService : IReceiveData  
    {  
        public void UploadFile(string fileName, Stream fileContents)  
        {  
            byte[] buffer = new byte[10000];  
            int bytesRead, totalBytesRead = 0;  
            do  
            {  
                bytesRead = fileContents.Read(buffer, 0, buffer.Length);  
                totalBytesRead += bytesRead;  
            } while (bytesRead > 0);  
            Console.WriteLine("Service: Received file {0} with {1} bytes", fileName, totalBytesRead);  
        }  
    }  
    ```  
  
### <a name="to-host-the-service"></a><span data-ttu-id="0a9c2-118">承载服务</span><span class="sxs-lookup"><span data-stu-id="0a9c2-118">To host the service</span></span>  
  
1.  <span data-ttu-id="0a9c2-119">创建用于承载服务的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-119">Create a console application to host the service.</span></span>  
  
    ```csharp  
    class Program  
    {  
       static void Main(string[] args)  
       {  
       }  
    }  
    ```  
  
2.  <span data-ttu-id="0a9c2-120">在 `Main` 方法中创建一个变量以保存服务的基址。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-120">Create a variable to hold the base address for the service within the `Main` method.</span></span>  
  
    ```csharp  
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3.  <span data-ttu-id="0a9c2-121">创建服务的一个 <xref:System.ServiceModel.ServiceHost> 实例，该实例指定服务类和基址。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-121">Create a <xref:System.ServiceModel.ServiceHost> instance for the service that specifies the service class and the base address.</span></span>  
  
    ```csharp  
    ServiceHost host = new ServiceHost(typeof(RawDataService), new Uri(baseAddress));  
    ```  
  
4.  <span data-ttu-id="0a9c2-122">添加一个指定协定、<xref:System.ServiceModel.WebHttpBinding> 和 <xref:System.ServiceModel.Description.WebHttpBehavior> 的终结点。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-122">Add an endpoint that specifies the contract, <xref:System.ServiceModel.WebHttpBinding>, and <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>  
  
    ```csharp  
    host.AddServiceEndpoint(typeof(IReceiveData), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5.  <span data-ttu-id="0a9c2-123">打开服务主机。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-123">Open the service host.</span></span> <span data-ttu-id="0a9c2-124">现在服务已准备好接收请求。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-124">The service is now ready to receive requests.</span></span>  
  
    ```csharp  
    host.Open();  
    Console.WriteLine("Host opened");  
    ```  
  
### <a name="to-call-the-service-programmatically"></a><span data-ttu-id="0a9c2-125">以编程方式调用服务</span><span class="sxs-lookup"><span data-stu-id="0a9c2-125">To call the service programmatically</span></span>  
  
1.  <span data-ttu-id="0a9c2-126">使用用于调用服务的 URI 创建一个 <xref:System.Net.HttpWebRequest>。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-126">Create a <xref:System.Net.HttpWebRequest> with the URI used to call the service.</span></span> <span data-ttu-id="0a9c2-127">在此代码中，基址与 `"/UploadFile/Text"` 组合在一起。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-127">In this code, the base address is combined with `"/UploadFile/Text"`.</span></span> <span data-ttu-id="0a9c2-128">URI 的 `"UploadFile"` 部分指定要调用的操作。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-128">The `"UploadFile"` portion of the URI specifies the operation to call.</span></span> <span data-ttu-id="0a9c2-129">URI 的 `"Test.txt"` 部分指定要传递给 `UploadFile` 操作的文件名参数。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-129">The `"Test.txt"` portion of the URI specifies the filename parameter to pass to the `UploadFile` operation.</span></span> <span data-ttu-id="0a9c2-130">这两项都映射到应用于操作协定的 <xref:System.UriTemplate>。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-130">Both of these items map to the <xref:System.UriTemplate> applied to the operation contract.</span></span>  
  
    ```csharp  
    HttpWebRequest req = (HttpWebRequest)HttpWebRequest.Create(baseAddress + "/UploadFile/Test.txt");  
    ```  
  
2.  <span data-ttu-id="0a9c2-131">将 <xref:System.Net.HttpWebRequest.Method%2A> 的 <xref:System.Net.HttpWebRequest> 属性设置为 `POST`，并将 <xref:System.Net.HttpWebRequest.ContentType%2A> 属性设置为 `"text/plain"`。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-131">Set the <xref:System.Net.HttpWebRequest.Method%2A> property of the <xref:System.Net.HttpWebRequest> to `POST` and the <xref:System.Net.HttpWebRequest.ContentType%2A> property to `"text/plain"`.</span></span> <span data-ttu-id="0a9c2-132">这会告知服务代码正在发送数据，且数据的格式为纯文本。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-132">This tells the service that the code is sending data and that data is in plain text.</span></span>  
  
    ```csharp  
    req.Method = "POST";  
    req.ContentType = "text/plain";  
    ```  
  
3.  <span data-ttu-id="0a9c2-133">调用 <xref:System.Net.HttpWebRequest.GetRequestStream%2A> 以获取请求流，创建要发送的数据，将该数据写入请求流，然后关闭请求流。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-133">Call <xref:System.Net.HttpWebRequest.GetRequestStream%2A> to get the request stream, create the data to send, write that data to the request stream, and close the stream.</span></span>  
  
    ```csharp  
    Stream reqStream = req.GetRequestStream();  
    byte[] fileToSend = new byte[12345];  
    for (int i = 0; i < fileToSend.Length; i++)  
       {  
           fileToSend[i] = (byte)('a' + (i % 26));  
       }  
    reqStream.Write(fileToSend, 0, fileToSend.Length);  
    reqStream.Close();  
    ```  
  
4.  <span data-ttu-id="0a9c2-134">通过调用 <xref:System.Net.HttpWebRequest.GetResponse%2A> 从服务获取响应，然后向控制台显示响应数据。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-134">Get the response from the service by calling <xref:System.Net.HttpWebRequest.GetResponse%2A> and display the response data to the console.</span></span>  
  
    ```csharp  
    HttpWebResponse resp = (HttpWebResponse)req.GetResponse();  
    Console.WriteLine("Client: Receive Response HTTP/{0} {1} {2}", resp.ProtocolVersion, (int)resp.StatusCode, resp.StatusDescription);  
    ```  
  
5.  <span data-ttu-id="0a9c2-135">关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-135">Close the service host.</span></span>  
  
    ```csharp  
    host.Close();  
    ```  
  
## <a name="example"></a><span data-ttu-id="0a9c2-136">示例</span><span class="sxs-lookup"><span data-stu-id="0a9c2-136">Example</span></span>  
 <span data-ttu-id="0a9c2-137">下面列出了此示例的完整代码。</span><span class="sxs-lookup"><span data-stu-id="0a9c2-137">The following is a complete listing of the code for this example.</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.ServiceModel;  
using System.ServiceModel.Web;  
using System.ServiceModel.Description;  
using System.IO;  
using System.Net;  
  
namespace ReceiveRawData  
{  
    [ServiceContract]  
    public interface IReceiveData  
    {  
        [WebInvoke(UriTemplate = "UploadFile/{fileName}")]  
        void UploadFile(string fileName, Stream fileContents);  
    }  
    public class RawDataService : IReceiveData  
    {  
        public void UploadFile(string fileName, Stream fileContents)  
        {  
            byte[] buffer = new byte[10000];  
            int bytesRead, totalBytesRead = 0;  
            do  
            {  
                bytesRead = fileContents.Read(buffer, 0, buffer.Length);  
                totalBytesRead += bytesRead;  
            } while (bytesRead > 0);  
            Console.WriteLine("Service: Received file {0} with {1} bytes", fileName, totalBytesRead);  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
            ServiceHost host = new ServiceHost(typeof(RawDataService), new Uri(baseAddress));  
            host.AddServiceEndpoint(typeof(IReceiveData), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
            host.Open();  
            Console.WriteLine("Host opened");  
  
            HttpWebRequest req = (HttpWebRequest)HttpWebRequest.Create(baseAddress + "/UploadFile/Test.txt");  
            req.Method = "POST";  
            req.ContentType = "text/plain";  
            Stream reqStream = req.GetRequestStream();  
            byte[] fileToSend = new byte[12345];  
            for (int i = 0; i < fileToSend.Length; i++)  
            {  
                fileToSend[i] = (byte)('a' + (i % 26));  
            }  
            reqStream.Write(fileToSend, 0, fileToSend.Length);  
            reqStream.Close();  
            HttpWebResponse resp = (HttpWebResponse)req.GetResponse();  
            Console.WriteLine("Client: Receive Response HTTP/{0} {1} {2}", resp.ProtocolVersion, (int)resp.StatusCode, resp.StatusDescription);  
            host.Close();  
  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0a9c2-138">编译代码</span><span class="sxs-lookup"><span data-stu-id="0a9c2-138">Compiling the Code</span></span>  
  
-   <span data-ttu-id="0a9c2-139">编译该代码时，请引用 System.ServiceModel.dll 和 System.ServiceModel.Web.dll</span><span class="sxs-lookup"><span data-stu-id="0a9c2-139">When compiling the code reference System.ServiceModel.dll and System.ServiceModel.Web.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a9c2-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a9c2-140">See Also</span></span>  
 [<span data-ttu-id="0a9c2-141">UriTemplate 和 UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="0a9c2-141">UriTemplate and UriTemplateTable</span></span>](../../../../docs/framework/wcf/feature-details/uritemplate-and-uritemplatetable.md)  
 [<span data-ttu-id="0a9c2-142">WCF Web HTTP 编程模型</span><span class="sxs-lookup"><span data-stu-id="0a9c2-142">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="0a9c2-143">WCF Web HTTP 编程模型概述</span><span class="sxs-lookup"><span data-stu-id="0a9c2-143">WCF Web HTTP Programming Model Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)
