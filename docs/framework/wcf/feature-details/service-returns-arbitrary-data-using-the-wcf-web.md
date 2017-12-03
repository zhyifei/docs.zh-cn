---
title: "如何：使用 WCF Web HTTP 编程模型创建返回任意数据的服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0283955a-b4ae-458d-ad9e-6fbb6f529e3d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8e1d808d4daf91b5ff89b05cab8359c90090f293
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-service-that-returns-arbitrary-data-using-the-wcf-web-http-programming-model"></a>如何：使用 WCF Web HTTP 编程模型创建返回任意数据的服务
有时，开发人员必须完全控制从服务操作返回数据的方式。 这是这种情况，服务操作必须在不支持的格式返回数据时[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]。 本主题讨论使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WEB HTTP 编程模型来创建此类服务。 此服务具有一个返回流的操作。  
  
### <a name="to-implement-the-service-contract"></a>实现服务协定  
  
1.  定义服务协定。 该协定名为 `IImageServer`，具有一个名为 `GetImage` 的方法，该方法返回 <xref:System.IO.Stream>。  
  
    ```  
    [ServiceContract]  
        public interface IImageServer  
        {  
            [WebGet]  
            Stream GetImage(int width, int height);  
        }  
    ```  
  
     由于该方法返回 <xref:System.IO.Stream>，因此 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 假定服务操作返回的字节由该操作完全控制，自己无需对返回的数据应用任何格式设置。  
  
2.  实现服务协定。 该协定只有一个操作：`GetImage`。 此方法生成一个位图，再以 .jpg 格式将其保存到 <xref:System.IO.MemoryStream>。 随后，操作将该流返回给调用方。  
  
    ```  
    public class Service : IImageServer  
       {  
           public Stream GetImage(int width, int height)  
           {  
               Bitmap bitmap = new Bitmap(width, height);  
               for (int i = 0; i < bitmap.Width; i++)  
               {  
                   for (int j = 0; j < bitmap.Height; j++)  
                   {  
                       bitmap.SetPixel(i, j, (Math.Abs(i - j) < 2) ? Color.Blue : Color.Yellow);  
                   }  
               }  
               MemoryStream ms = new MemoryStream();  
               bitmap.Save(ms, System.Drawing.Imaging.ImageFormat.Jpeg);  
               ms.Position = 0;  
               WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";  
               return ms;  
           }  
       }  
    ```  
  
     请注意代码的倒数第二行：`WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";`  
  
     这将内容类型标头设置为`"image/jpeg"`。 虽然此示例演示如何返回 .jpg 文件，但可以对其进行修改，以任意格式返回所需的任意类型的数据。 该操作必须检索或生成数据，然后将它写入流。  
  
### <a name="to-host-the-service"></a>承载服务  
  
1.  创建用于承载服务的控制台应用程序。  
  
    ```  
    class Program  
    {  
        static void Main(string[] args)  
        {  
        }   
    }  
    ```  
  
2.  在 `Main` 方法中创建一个变量以保存服务的基址。  
  
    ```  
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3.  为服务创建一个 <xref:System.ServiceModel.ServiceHost> 实例，指定服务类和基址。  
  
    ```  
    ServiceHost host = new ServiceHost(typeof(Service), new Uri(baseAddress));  
    ```  
  
4.  使用 <xref:System.ServiceModel.WebHttpBinding> 和 <xref:System.ServiceModel.Description.WebHttpBehavior> 添加一个终结点。  
  
    ```  
    host.AddServiceEndpoint(typeof(IImageServer), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5.  打开服务主机。  
  
    ```  
    host.Open()  
    ```  
  
6.  等待用户按 Enter 终止服务。  
  
    ```  
    Console.WriteLine("Service is running");  
    Console.Write("Press ENTER to close the host");  
    Console.ReadLine();  
    host.Close();  
    ```  
  
### <a name="to-call-the-raw-service-using-internet-explorer"></a>使用 Internet Explorer 调用原始服务  
  
1.  运行该服务，您应看到来自它的以下输出。 `Service is running Press ENTER to close the host`  
  
2.  打开 Internet Explorer 并键入 `http://localhost:8000/Service/GetImage?width=50&height=40`，您应看到一个黄色矩形，有蓝色对角线穿过其中心。  
  
## <a name="example"></a>示例  
 下面列出了此主题的完整代码。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.ServiceModel;  
using System.ServiceModel.Web;  
using System.ServiceModel.Description;  
using System.IO;  
using System.Drawing;  
  
namespace RawImageService  
{  
    // Define the service contract  
    [ServiceContract]  
    public interface IImageServer  
    {  
        [WebGet]  
        Stream GetImage(int width, int height);  
    }  
  
    // implement the service contract  
    public class Service : IImageServer  
    {  
        public Stream GetImage(int width, int height)  
        {  
            // Although this method returns a jpeg, it can be  
            // modified to return any data you want within the stream  
            Bitmap bitmap = new Bitmap(width, height);  
            for (int i = 0; i < bitmap.Width; i++)  
            {  
                for (int j = 0; j < bitmap.Height; j++)  
                {  
                    bitmap.SetPixel(i, j, (Math.Abs(i - j) < 2) ? Color.Blue : Color.Yellow);  
                }  
            }  
            MemoryStream ms = new MemoryStream();  
            bitmap.Save(ms, System.Drawing.Imaging.ImageFormat.Jpeg);  
            ms.Position = 0;  
            WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";  
            return ms;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
            ServiceHost host = new ServiceHost(typeof(Service), new Uri(baseAddress));  
            host.AddServiceEndpoint(typeof(IImageServer), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
            host.Open();  
            Console.WriteLine("Service is running");  
            Console.Write("Press ENTER to close the host");  
            Console.ReadLine();  
            host.Close();  
  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a>编译代码  
  
-   编译示例代码时，请引用 System.ServiceModel.dll 和 System.ServiceModel.Web.dll。  
  
## <a name="see-also"></a>另请参阅  
 [WCF Web HTTP 编程模型](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
