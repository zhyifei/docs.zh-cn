# <a name="using-dotnet-svcutilxmlserializer-on-net-core"></a>在 .NET Core 上使用 dotnet-svcutil.xmlserializer

## <a name="prerequisites"></a>系统必备

以下是 dotnet-svcutil.xmlserializer 正常运行的必备条件。 

* [.NET Core 2.1 SDK 或更高版本](https://www.microsoft.com/net/download/dotnet-core/sdk-2.1.300)
* [.NET Core 运行时 2.1 或更高版本](https://www.microsoft.com/net/download/dotnet-core/runtime-2.1.0)

可以使用命令 `dotnet --info` 检查已安装哪些版本的 .NET Core SDK 和运行时。

若要在 .NET Core 控制台应用程序中使用 dotnet-svcutil.xmlserializer：

1. 在 .NET Framework 中使用默认模板“WCF 服务应用程序”创建一个名为“MyWCFService”的 WCF 服务。  在服务方法上添加 ```[XmlSerializerFormat]``` 属性，如下所示
    ```c#
    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```
2. 创建一个 NET Core 控制台应用程序作为以 netcoreapp 2.1 为目标的 WCF 客户端应用程序，例如，使用以下命令创建一个名为“MyWCFClient”的应用程序，
    ```
    dotnet new console --name MyWCFClient
    ```
    请确保 csproj 面向 netcoreapp 2.1。 此操作是在 .csproj 文件中使用下面的 XML 元素完成的
    ```xml
    <TargetFramework>netcoreapp2.1</TargetFramework>
    ```
3. 通过运行以下命令向 System.ServiceModel.Http 添加包引用：
   
   ```dotnet add package System.ServiceModel.Http -v 4.5.0```

4. 添加 WCF 客户端代码：
    ```csharp
    using System.ServiceModel;
    
    class Program
    {
        static void Main(string[] args)
        {
            var myBinding = new BasicHttpBinding();
            var myEndpoint = new EndpointAddress("http://localhost:2561/Service1.svc"); //Fill your service url here
            var myChannelFactory = new ChannelFactory<IService1>(myBinding, myEndpoint);
            IService1 client = myChannelFactory.CreateChannel();
            string s = client.GetData(1);
            ((ICommunicationObject)client).Close();
        }
    }

    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```
5. 编辑 .csproj 文件并添加对 dotnet-svcutil.xmlserializer 包的引用。 例如:

    i. 运行命令：`dotnet add package dotnet-svcutil.xmlserializer -v 1.0.0`

    ii. 在 MyWCFClient.csproj 中添加以下行，
    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil.xmlserializer" Version="1.0.0" />
    </ItemGroup>
    ```

6. 通过运行 `dotnet build` 生成应用程序。 如果一切顺利，则会在输出文件夹中生成名为“MyWCFClient.XmlSerializers.dll”的程序集。 如果该工具无法生成程序集，将在生成输出中看到警告。

7. 启动 WCF 服务，例如通过在浏览器中运行 http://localhost:2561/Service1.svc。 然后启动客户端应用程序，它将在运行时自动加载和使用预生成的序列化程序。
