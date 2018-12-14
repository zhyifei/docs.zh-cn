# <a name="using-dotnet-svcutilxmlserializer-on-net-core"></a><span data-ttu-id="eb331-101">在 .NET Core 上使用 dotnet-svcutil.xmlserializer</span><span class="sxs-lookup"><span data-stu-id="eb331-101">Using dotnet-svcutil.xmlserializer on .NET Core</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eb331-102">系统必备</span><span class="sxs-lookup"><span data-stu-id="eb331-102">Prerequisites</span></span>

<span data-ttu-id="eb331-103">以下是 dotnet-svcutil.xmlserializer 正常运行的必备条件。</span><span class="sxs-lookup"><span data-stu-id="eb331-103">The following is required for dotnet-svcutil.xmlserializer to work.</span></span> 

* [<span data-ttu-id="eb331-104">.NET Core 2.1 SDK 或更高版本</span><span class="sxs-lookup"><span data-stu-id="eb331-104">.NET Core 2.1 SDK or later</span></span>](https://www.microsoft.com/net/download/dotnet-core/sdk-2.1.300)
* [<span data-ttu-id="eb331-105">.NET Core 运行时 2.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="eb331-105">.NET Core Runtime 2.1 or later</span></span>](https://www.microsoft.com/net/download/dotnet-core/runtime-2.1.0)

<span data-ttu-id="eb331-106">可以使用命令 `dotnet --info` 检查已安装哪些版本的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="eb331-106">You can use the command `dotnet --info` to check which versions of .NET Core SDK and runtime you already have installed.</span></span>

<span data-ttu-id="eb331-107">若要在 .NET Core 控制台应用程序中使用 dotnet-svcutil.xmlserializer：</span><span class="sxs-lookup"><span data-stu-id="eb331-107">To use dotnet-svcutil.xmlserializer in a .NET Core console application:</span></span>

1. <span data-ttu-id="eb331-108">在 .NET Framework 中使用默认模板“WCF 服务应用程序”创建一个名为“MyWCFService”的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="eb331-108">Create a WCF Service named 'MyWCFService' using the default template 'WCF Service Application' in .NET Framework.</span></span>  <span data-ttu-id="eb331-109">在服务方法上添加 ```[XmlSerializerFormat]``` 属性，如下所示</span><span class="sxs-lookup"><span data-stu-id="eb331-109">Add ```[XmlSerializerFormat]``` attribute on the service method like the following</span></span>
    ```c#
    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```
2. <span data-ttu-id="eb331-110">创建一个 NET Core 控制台应用程序作为以 netcoreapp 2.1 为目标的 WCF 客户端应用程序，例如，使用以下命令创建一个名为“MyWCFClient”的应用程序，</span><span class="sxs-lookup"><span data-stu-id="eb331-110">Create a .NET Core console application as WCF client application that targets at netcoreapp 2.1, e.g. create an app named 'MyWCFClient' with the command,</span></span>
    ```
    dotnet new console --name MyWCFClient
    ```
    <span data-ttu-id="eb331-111">请确保 csproj 面向 netcoreapp 2.1。</span><span class="sxs-lookup"><span data-stu-id="eb331-111">Make sure your csproj targets a netcoreapp 2.1.</span></span> <span data-ttu-id="eb331-112">此操作是在 .csproj 文件中使用下面的 XML 元素完成的</span><span class="sxs-lookup"><span data-stu-id="eb331-112">This is done using the following XML element in your .csproj file</span></span>
    ```xml
    <TargetFramework>netcoreapp2.1</TargetFramework>
    ```
3. <span data-ttu-id="eb331-113">通过运行以下命令向 System.ServiceModel.Http 添加包引用：</span><span class="sxs-lookup"><span data-stu-id="eb331-113">Add a package reference to System.ServiceModel.Http by running the following command:</span></span>
   
   ```dotnet add package System.ServiceModel.Http -v 4.5.0```

4. <span data-ttu-id="eb331-114">添加 WCF 客户端代码：</span><span class="sxs-lookup"><span data-stu-id="eb331-114">Add the WCF Client code:</span></span>
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
5. <span data-ttu-id="eb331-115">编辑 .csproj 文件并添加对 dotnet-svcutil.xmlserializer 包的引用。</span><span class="sxs-lookup"><span data-stu-id="eb331-115">Edit the .csproj file and add a reference to the dotnet-svcutil.xmlserializer package.</span></span> <span data-ttu-id="eb331-116">例如:</span><span class="sxs-lookup"><span data-stu-id="eb331-116">For example:</span></span>

    <span data-ttu-id="eb331-117">i.</span><span class="sxs-lookup"><span data-stu-id="eb331-117">i.</span></span> <span data-ttu-id="eb331-118">运行命令：`dotnet add package dotnet-svcutil.xmlserializer -v 1.0.0`</span><span class="sxs-lookup"><span data-stu-id="eb331-118">Run command: `dotnet add package dotnet-svcutil.xmlserializer -v 1.0.0`</span></span>

    <span data-ttu-id="eb331-119">ii.</span><span class="sxs-lookup"><span data-stu-id="eb331-119">ii.</span></span> <span data-ttu-id="eb331-120">在 MyWCFClient.csproj 中添加以下行，</span><span class="sxs-lookup"><span data-stu-id="eb331-120">Add the following lines in MyWCFClient.csproj,</span></span>
    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil.xmlserializer" Version="1.0.0" />
    </ItemGroup>
    ```

6. <span data-ttu-id="eb331-121">通过运行 `dotnet build` 生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="eb331-121">Build the application by running `dotnet build`.</span></span> <span data-ttu-id="eb331-122">如果一切顺利，则会在输出文件夹中生成名为“MyWCFClient.XmlSerializers.dll”的程序集。</span><span class="sxs-lookup"><span data-stu-id="eb331-122">If everything succeeds, an assembly named MyWCFClient.XmlSerializers.dll will be generated in the output folder.</span></span> <span data-ttu-id="eb331-123">如果该工具无法生成程序集，将在生成输出中看到警告。</span><span class="sxs-lookup"><span data-stu-id="eb331-123">You will see warnings in the build output if the tool failed to generate the assembly.</span></span>

7. <span data-ttu-id="eb331-124">启动 WCF 服务，例如通过在浏览器中运行 http://localhost:2561/Service1.svc。</span><span class="sxs-lookup"><span data-stu-id="eb331-124">Start the WCF service e.g. by running http://localhost:2561/Service1.svc in the browser.</span></span> <span data-ttu-id="eb331-125">然后启动客户端应用程序，它将在运行时自动加载和使用预生成的序列化程序。</span><span class="sxs-lookup"><span data-stu-id="eb331-125">Then start the client application, and it will automatically load and use the pre-generated serializers at runtime.</span></span>
