---
title: 如何：为 WCF Web 服务应用程序启用 WIF
ms.date: 03/30/2017
ms.assetid: bfc64b3d-64e9-4093-a6a4-72e933917af7
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 71897299d68c2f0e43def8e70730ea456d6e9e24
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2018
ms.locfileid: "44699197"
---
# <a name="how-to-enable-wif-for-a-wcf-web-service-application"></a><span data-ttu-id="da3bf-102">如何：为 WCF Web 服务应用程序启用 WIF</span><span class="sxs-lookup"><span data-stu-id="da3bf-102">How To: Enable WIF for a WCF Web Service Application</span></span>
## <a name="applies-to"></a><span data-ttu-id="da3bf-103">适用于</span><span class="sxs-lookup"><span data-stu-id="da3bf-103">Applies To</span></span>  
  
-   <span data-ttu-id="da3bf-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="da3bf-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="da3bf-105">Microsoft® Windows® Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="da3bf-105">Microsoft® Windows® Communication Foundation (WCF)</span></span>  
  
## <a name="summary"></a><span data-ttu-id="da3bf-106">总结</span><span class="sxs-lookup"><span data-stu-id="da3bf-106">Summary</span></span>  
 <span data-ttu-id="da3bf-107">此“如何”主题提供了详细的分步过程，用于说明如何在 WCF 服务中启用 WIF。</span><span class="sxs-lookup"><span data-stu-id="da3bf-107">This How-To provides detailed step-by-step procedures for enabling WIF in a WCF web service.</span></span> <span data-ttu-id="da3bf-108">它还提供关于如何测试应用程序的说明，以便验证 Web 服务在应用程序运行时正确呈现声明。</span><span class="sxs-lookup"><span data-stu-id="da3bf-108">It also provides instructions for how to test the application to verify that the web service is correctly presenting claims when the application is run.</span></span> <span data-ttu-id="da3bf-109">此“如何”主题未详细介绍如何创建安全令牌服务 (STS)，而是使用随标识和访问工具提供的开发 STS。</span><span class="sxs-lookup"><span data-stu-id="da3bf-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and instead uses the Development STS that comes with the Identity and Access tool.</span></span> <span data-ttu-id="da3bf-110">开发 STS 不执行实际的身份验证操作，只是用来进行测试。</span><span class="sxs-lookup"><span data-stu-id="da3bf-110">The Development STS does not perform real authentication and is intended for testing purposes only.</span></span> <span data-ttu-id="da3bf-111">你将需要安装标识和访问工具才能完成此“如何”主题。</span><span class="sxs-lookup"><span data-stu-id="da3bf-111">You will need to install the Identity and Access tool to complete this How-To.</span></span> <span data-ttu-id="da3bf-112">此工具可以从下列位置下载：[标识和访问工具](https://go.microsoft.com/fwlink/?LinkID=245849)</span><span class="sxs-lookup"><span data-stu-id="da3bf-112">It can be downloaded from the following location: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span></span>  
  
## <a name="contents"></a><span data-ttu-id="da3bf-113">内容</span><span class="sxs-lookup"><span data-stu-id="da3bf-113">Contents</span></span>  
  
-   <span data-ttu-id="da3bf-114">目标</span><span class="sxs-lookup"><span data-stu-id="da3bf-114">Objectives</span></span>  
  
-   <span data-ttu-id="da3bf-115">概述</span><span class="sxs-lookup"><span data-stu-id="da3bf-115">Overview</span></span>  
  
-   <span data-ttu-id="da3bf-116">步骤摘要</span><span class="sxs-lookup"><span data-stu-id="da3bf-116">Summary of Steps</span></span>  
  
-   <span data-ttu-id="da3bf-117">步骤 1 – 创建一个简单的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="da3bf-117">Step 1 – Create a Simple WCF Service</span></span>  
  
-   <span data-ttu-id="da3bf-118">步骤 2 - 为 WCF 服务创建一个客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="da3bf-118">Step 2 – Create a Client Application for the WCF Service</span></span>  
  
-   <span data-ttu-id="da3bf-119">步骤 3 - 测试你的解决方案</span><span class="sxs-lookup"><span data-stu-id="da3bf-119">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="da3bf-120">目标</span><span class="sxs-lookup"><span data-stu-id="da3bf-120">Objectives</span></span>  
  
-   <span data-ttu-id="da3bf-121">创建一个需要使用颁发令牌的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="da3bf-121">Create a WCF service that requires issued tokens</span></span>  
  
-   <span data-ttu-id="da3bf-122">创建一个 WCF 客户端，用于从 STS 请求令牌并将其传递给 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="da3bf-122">Create a WCF client that requests a token from an STS and passes it to the WCF service</span></span>  
  
## <a name="overview"></a><span data-ttu-id="da3bf-123">概述</span><span class="sxs-lookup"><span data-stu-id="da3bf-123">Overview</span></span>  
 <span data-ttu-id="da3bf-124">此“如何”主题旨在演示开发人员在开发 WCF 服务时可以如何使用联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="da3bf-124">This How-To is intended to demonstrate how a developer can use federated authentication when developing WCF services.</span></span> <span data-ttu-id="da3bf-125">在 WCF 服务中使用联合方法的部分优势包括：</span><span class="sxs-lookup"><span data-stu-id="da3bf-125">Some of the benefits of using federation in WCF services include:</span></span>  
  
1.  <span data-ttu-id="da3bf-126">将 WCF 服务代码之外的身份验证逻辑纳入在内</span><span class="sxs-lookup"><span data-stu-id="da3bf-126">Factoring authentication logic out of WCF service code</span></span>  
  
2.  <span data-ttu-id="da3bf-127">重复使用现有的标识管理解决方案</span><span class="sxs-lookup"><span data-stu-id="da3bf-127">Re-using existing identity management solutions</span></span>  
  
3.  <span data-ttu-id="da3bf-128">与其他标识解决方案实现互操作</span><span class="sxs-lookup"><span data-stu-id="da3bf-128">Interoperability with other identity solutions</span></span>  
  
4.  <span data-ttu-id="da3bf-129">灵活、弹性地适应未来更改</span><span class="sxs-lookup"><span data-stu-id="da3bf-129">Flexibility and resilience to future changes</span></span>  
  
 <span data-ttu-id="da3bf-130">借助 WIF 和关联的标识和访问工具，可以更轻松地开发和测试采用联合身份验证的 WCF 服务，如下列步骤所示。</span><span class="sxs-lookup"><span data-stu-id="da3bf-130">WIF and the associated Identity and Access tool make it easier to develop and test a WCF service using federated authentication, as the following steps demonstrate.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="da3bf-131">步骤摘要</span><span class="sxs-lookup"><span data-stu-id="da3bf-131">Summary of Steps</span></span>  
  
-   <span data-ttu-id="da3bf-132">步骤 1 – 创建一个简单的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="da3bf-132">Step 1 – Create a Simple WCF Service</span></span>  
  
-   <span data-ttu-id="da3bf-133">步骤 2 - 为 WCF 服务创建一个客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="da3bf-133">Step 2 – Create a Client Application for the WCF Service</span></span>  
  
-   <span data-ttu-id="da3bf-134">步骤 3 - 测试你的解决方案</span><span class="sxs-lookup"><span data-stu-id="da3bf-134">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-wcf-service"></a><span data-ttu-id="da3bf-135">步骤 1 – 创建一个简单的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="da3bf-135">Step 1 – Create a Simple WCF Service</span></span>  
 <span data-ttu-id="da3bf-136">在此步骤中，你将创建一个新的 WCF 服务，此服务使用标识和访问工具中包含的开发 STS。</span><span class="sxs-lookup"><span data-stu-id="da3bf-136">In this step, you will create a new WCF service that uses the Development STS that is included with the Identity and Access tool.</span></span>  
  
#### <a name="to-create-a-simple-wcf-service"></a><span data-ttu-id="da3bf-137">创建一个简单的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="da3bf-137">To create a simple WCF service</span></span>  
  
1.  <span data-ttu-id="da3bf-138">以管理员身份在提升模式下启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="da3bf-138">Start Visual Studio in elevated mode as administrator.</span></span>  
  
2.  <span data-ttu-id="da3bf-139">在 Visual Studio 中，单击“文件”，再单击“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="da3bf-139">In Visual Studio, click **File**, click **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="da3bf-140">在“新建项目”窗口中，单击“WCF 服务应用程序”。</span><span class="sxs-lookup"><span data-stu-id="da3bf-140">In the **New Project** window, click **WCF Service Application**.</span></span>  
  
4.  <span data-ttu-id="da3bf-141">在“名称”中，输入 `TestService`，然后按“确定”。</span><span class="sxs-lookup"><span data-stu-id="da3bf-141">In **Name**, enter `TestService` and press **OK**.</span></span>  
  
5.  <span data-ttu-id="da3bf-142">右键单击“解决方案资源管理器”下的“TestService”项目，然后选择“标识和访问”。</span><span class="sxs-lookup"><span data-stu-id="da3bf-142">Right-click the **TestService** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
6.  <span data-ttu-id="da3bf-143">“标识和访问”窗口随即出现。</span><span class="sxs-lookup"><span data-stu-id="da3bf-143">The **Identity and Access** window appears.</span></span> <span data-ttu-id="da3bf-144">在“提供程序”下，选择“使用本地开发 STS 测试应用程序”，然后单击“应用”。</span><span class="sxs-lookup"><span data-stu-id="da3bf-144">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span> <span data-ttu-id="da3bf-145">标识和访问工具可以向 Web.config 文件添加配置元素，从而将服务配置为使用 WIF，并将身份验证外包给本地开发 STS (LocalSTS) 来执行。</span><span class="sxs-lookup"><span data-stu-id="da3bf-145">The Identity and Access Tool configures the service to use WIF and to outsource authentication to the local development STS (**LocalSTS**) by adding configuration elements to the *Web.config* file.</span></span>  
  
7.  <span data-ttu-id="da3bf-146">在 Service1.svc.cs 文件中，为 System.Security.Claims 命名空间添加一个 `using` 指令，并使用下面的代码替换现有代码，然后保存文件：</span><span class="sxs-lookup"><span data-stu-id="da3bf-146">In the *Service1.svc.cs* file, add a `using` directive for the **System.Security.Claims** namespace and replace the existing code with the following, then save the file:</span></span>  
  
    ```csharp  
    public class Service1 : IService1  
    {  
        public string ComputeResponse(string input)  
        {  
            // Get the caller's identity from ClaimsPrincipal.Current  
            ClaimsPrincipal claimsPrincipal = OperationContext.Current.ClaimsPrincipal;  
  
            // Start generating the output  
            StringBuilder builder = new StringBuilder();  
            builder.AppendLine("Computed by ClaimsAwareWebService");  
            builder.AppendLine("Input received from client:" + input);  
  
            if (claimsPrincipal != null)  
            {  
                // Display the claims from the caller. Do not use this code in a production application.  
                ClaimsIdentity identity = claimsPrincipal.Identity as ClaimsIdentity;  
                builder.AppendLine("Client Name:" + identity.Name);  
                builder.AppendLine("IsAuthenticated:" + identity.IsAuthenticated);  
                builder.AppendLine("The service received the following issued claims of the client:");  
  
                // Iterate over the caller’s claims and append to the output  
                foreach (Claim claim in claimsPrincipal.Claims)  
                {  
                    builder.AppendLine("ClaimType :" + claim.Type + "   ClaimValue:" + claim.Value);  
                }  
            }  
  
            return builder.ToString();  
        }  
    }  
    ```  
  
     <span data-ttu-id="da3bf-147">`ComputeResponse` 方法可以显示由 LocalSTS 发出的各个声明的属性。</span><span class="sxs-lookup"><span data-stu-id="da3bf-147">The `ComputeResponse` method displays the properties of various claims that are issued by **LocalSTS**.</span></span>  
  
8.  <span data-ttu-id="da3bf-148">在 IService1.cs 文件中，使用下面的代码替换现有代码，然后保存文件：</span><span class="sxs-lookup"><span data-stu-id="da3bf-148">In the *IService1.cs* file, replace the existing code with the following, then save the file:</span></span>  
  
    ```csharp  
    [ServiceContract]  
    public interface IService1  
    {  
        [OperationContract]  
        string ComputeResponse(string input);  
    }  
    ```  
  
9. <span data-ttu-id="da3bf-149">生成项目。</span><span class="sxs-lookup"><span data-stu-id="da3bf-149">Build the project.</span></span>  
  
10. <span data-ttu-id="da3bf-150">按“Ctrl-F5”运行服务，而不启动调试器。</span><span class="sxs-lookup"><span data-stu-id="da3bf-150">Press **Ctrl-F5** to run the service without starting the debugger.</span></span> <span data-ttu-id="da3bf-151">此时应该会为此服务打开一个网页，可查看通知区域（系统栏），验证 LocalSTS 是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="da3bf-151">A Web page should open for the service and you can verify that **LocalSTS** is running by looking in the notification area (system tray).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="da3bf-152">当在下一个步骤中向客户端应用程序添加服务引用时，TestService 和 LocalSTS 都必须处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="da3bf-152">Both **TestService** and **LocalSTS** must be running when you add the service reference to the client application in the next step.</span></span>  
  
## <a name="step-2--create-a-client-application-for-the-wcf-service"></a><span data-ttu-id="da3bf-153">步骤 2 - 为 WCF 服务创建一个客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="da3bf-153">Step 2 – Create a Client Application for the WCF Service</span></span>  
 <span data-ttu-id="da3bf-154">在此步骤中，你将创建一个控制台应用程序，此应用程序使用开发 STS 来对上一个步骤中创建的 WCF 服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="da3bf-154">In this step, you will create a console application that uses the Development STS to authenticate with the WCF service you created in the previous step.</span></span>  
  
#### <a name="to-create-a-client-application"></a><span data-ttu-id="da3bf-155">创建客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="da3bf-155">To create a client application</span></span>  
  
1.  <span data-ttu-id="da3bf-156">在 Visual Studio 中，右键单击解决方案，单击“添加”，然后单击“新建项目”。</span><span class="sxs-lookup"><span data-stu-id="da3bf-156">In Visual Studio, right-click on the solution, click **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="da3bf-157">在“添加新项目”窗口中，选择 Visual C# 模板列表中的“控制台应用程序”，输入 `Client`，然后按“确定”。</span><span class="sxs-lookup"><span data-stu-id="da3bf-157">In the **Add New Project** window, select **Console Application** from the **Visual C#** templates list, enter `Client`, and then press **OK**.</span></span> <span data-ttu-id="da3bf-158">系统将在你的解决方案文件夹中创建新项目。</span><span class="sxs-lookup"><span data-stu-id="da3bf-158">The new project will be created in your solution folder.</span></span>  
  
3.  <span data-ttu-id="da3bf-159">右键单击“客户端”项目下的“引用”，然后单击“添加服务引用”。</span><span class="sxs-lookup"><span data-stu-id="da3bf-159">Right-click on **References** under the **Client** project, and then click **Add Service Reference**.</span></span>  
  
4.  <span data-ttu-id="da3bf-160">在“添加服务引用”窗口中，单击“发现”按钮上的下拉箭头，然后单击“解决方案中的服务”。</span><span class="sxs-lookup"><span data-stu-id="da3bf-160">In the **Add Service Reference** window, click the drop-down arrow on the **Discover** button and click **Services in Solution**.</span></span> <span data-ttu-id="da3bf-161">“地址”将自动填充之前创建的 WCF 服务，而“命名空间”将设置为“ServiceReference1”。</span><span class="sxs-lookup"><span data-stu-id="da3bf-161">The **Address** will automatically populate with the WCF service you created earlier, and the **Namespace** will be set to **ServiceReference1**.</span></span> <span data-ttu-id="da3bf-162">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="da3bf-162">Click **OK**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="da3bf-163">向客户端添加服务引用时，TestService 和 LocalSTS 都必须处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="da3bf-163">Both **TestService** and **LocalSTS** must be running when you add the service reference to the client.</span></span>  
  
5.  <span data-ttu-id="da3bf-164">Visual Studio 将生成 WCF 服务的代理类，然后添加所有必要的引用信息。</span><span class="sxs-lookup"><span data-stu-id="da3bf-164">Visual Studio will generate proxy classes for the WCF service, and add all of the necessary reference information.</span></span> <span data-ttu-id="da3bf-165">还将向 App.config 文件添加元素，以便将客户端配置为从 STS 获取令牌，然后对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="da3bf-165">It will also add elements to the *App.config* file to configure the client to get a token from the STS to authenticate with the service.</span></span> <span data-ttu-id="da3bf-166">当此过程完成之后，将打开 Program.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="da3bf-166">When this process is finished, the **Program.cs** file will open.</span></span> <span data-ttu-id="da3bf-167">分别为 System.ServiceModel 和 Client.ServiceReference1 添加一个 `using` 指令，使用下面的代码替换 Main 方法，然后保存文件：</span><span class="sxs-lookup"><span data-stu-id="da3bf-167">Add a `using` directive for **System.ServiceModel** and another for **Client.ServiceReference1**, replace the **Main** method with the following code, then save the file:</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        // Create the client for the service  
        Service1Client client = new Service1Client();  
        Console.WriteLine("-------------WCF Client Application--------------\n");  
  
        while (!ShouldQuitApplication())  
        {  
            try  
            {  
                Console.WriteLine(client.ComputeResponse("Hello World"));  
            }  
            catch (CommunicationException e)  
            {  
                Console.WriteLine(e.Message);  
                Console.WriteLine(e.StackTrace);  
                Exception ex = e.InnerException;  
                while (ex != null)  
                {  
                    Console.WriteLine("===========================");  
                    Console.WriteLine(ex.Message);  
                    Console.WriteLine(ex.StackTrace);  
                    ex = ex.InnerException;  
                }  
            }  
            catch (TimeoutException)  
            {  
                Console.WriteLine("Timed out...");  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("An unexpected exception occurred.");  
                Console.WriteLine(e.StackTrace);  
            }  
        }  
  
        client.Close();  
  
        if (client != null)  
        {  
            client.Abort();  
        }  
    }  
  
    static bool ShouldQuitApplication()  
    {  
        Console.WriteLine("---------------------------------------------------------------------");  
        Console.WriteLine("Press Enter key to invoke service, any other key to quit application:");  
        Console.WriteLine("----------------------------------------------------------------------");  
  
        ConsoleKeyInfo keyInfo = Console.ReadKey();  
        if (keyInfo.Key == ConsoleKey.Enter)  
            return false;  
        return true;  
    }  
    ```  
  
6.  <span data-ttu-id="da3bf-168">打开 App.config 文件并添加下面的 XML，将其作为 `<system.serviceModel>` 元素下的第一个子元素，然后保存文件：</span><span class="sxs-lookup"><span data-stu-id="da3bf-168">Open the *App.config* file and add the following XML as the first child element under the `<system.serviceModel>` element, then save the file:</span></span>  
  
    ```xml  
    <behaviors>  
       <endpointBehaviors>  
         <behavior>  
           <clientCredentials>  
             <serviceCertificate>  
               <authentication certificateValidationMode="None"/>  
             </serviceCertificate>  
           </clientCredentials>  
         </behavior>  
       </endpointBehaviors>  
     </behaviors>  
    ```  
  
     <span data-ttu-id="da3bf-169">这样会禁用证书验证。</span><span class="sxs-lookup"><span data-stu-id="da3bf-169">This disables certificate validation.</span></span>  
  
7.  <span data-ttu-id="da3bf-170">右键单击“TestService”解决方案，然后单击“设置启动项目”。</span><span class="sxs-lookup"><span data-stu-id="da3bf-170">Right-click the **TestService** solution and click on **Set StartUp Projects**.</span></span> <span data-ttu-id="da3bf-171">“启动项目”属性页便随即打开。</span><span class="sxs-lookup"><span data-stu-id="da3bf-171">The **Startup Project** property page opens.</span></span> <span data-ttu-id="da3bf-172">在“启动项目”属性页中，选择“多启动项目”，然后单击每个项目的“操作”字段，并从下拉菜单中选择“启动”。</span><span class="sxs-lookup"><span data-stu-id="da3bf-172">In the **Startup Project** property page, select **Multiple startup projects** then click in the **Action** field for each project and select **Start** from the drop-down menu.</span></span> <span data-ttu-id="da3bf-173">单击“确定”保存这些设置。</span><span class="sxs-lookup"><span data-stu-id="da3bf-173">Click **OK** to save the settings.</span></span>  
  
8.  <span data-ttu-id="da3bf-174">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="da3bf-174">Build the solution.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="da3bf-175">步骤 3 - 测试你的解决方案</span><span class="sxs-lookup"><span data-stu-id="da3bf-175">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="da3bf-176">在此步骤中，你将测试已启用 WIF 的 WCF 应用程序并验证正确呈现声明。</span><span class="sxs-lookup"><span data-stu-id="da3bf-176">In this step you will test your WIF-enabled WCF application and verify that claims are presented.</span></span>  
  
#### <a name="to-test-your-wif-enabled-wcf-application-for-claims"></a><span data-ttu-id="da3bf-177">对已启用 WIF 的 WCF 应用程序进行声明测试</span><span class="sxs-lookup"><span data-stu-id="da3bf-177">To test your WIF-enabled WCF application for claims</span></span>  
  
1.  <span data-ttu-id="da3bf-178">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="da3bf-178">Press **F5** to build and run the application.</span></span> <span data-ttu-id="da3bf-179">应会看到一个控制台窗口，以及以下文本：按“Enter”可调用服务，按其他键可退出应用程序：</span><span class="sxs-lookup"><span data-stu-id="da3bf-179">You should be presented with a console window, and the following text: **Press Enter key to invoke service, any other key to quit application:**</span></span>  
  
2.  <span data-ttu-id="da3bf-180">按“Enter”，然后控制台应会显示以下声明信息：</span><span class="sxs-lookup"><span data-stu-id="da3bf-180">Press **Enter**, and the following claims information should appear in the console:</span></span>  
  
    ```  
    Computed by Service1  
    Input received from client: Hello World  
    Client Name: Terry  
    IsAuthenticated: True  
    The service received the following issued claims of the client:  
    ClaimType :http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name    ClaimValue:Terry  
    ClaimType :http://schema.xmlsoap.org/ws/2005/05/identity/claims/surname    ClaimValue:Adams  
    ClaimType :http://schemas.microsoft.com/ws/2008/06/identity/claims/role    ClaimValue:developer  
    ClaimType :http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress    ClaimValue:terry@contoso.com  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="da3bf-181">在按“Enter”之前，TestService 和 LocalSTS 都必须处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="da3bf-181">Both **TestService** and **LocalSTS** must be running before you press **Enter**.</span></span> <span data-ttu-id="da3bf-182">此时应该会为此服务打开一个网页，可查看通知区域（系统栏），验证 LocalSTS 是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="da3bf-182">A Web page should open for the service and you can verify that **LocalSTS** is running by looking in the notification area (system tray).</span></span>  
  
3.  <span data-ttu-id="da3bf-183">如果这些声明出现在控制台中，表示你已成功通过 STS 身份验证，可以显示 WCF 服务的声明。</span><span class="sxs-lookup"><span data-stu-id="da3bf-183">If these claims appear in the console, you have successfully authenticated with the STS to display claims from the WCF service.</span></span>
