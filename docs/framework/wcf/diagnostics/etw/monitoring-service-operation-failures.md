---
title: 对服务操作失败进行监视
ms.date: 03/30/2017
ms.assetid: 59472ba3-8ebf-4479-bd7b-f440d5e636cb
ms.openlocfilehash: 3d708b537789c8d0decf75df780300c1e185c4c8
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803762"
---
# <a name="monitoring-service-operation-failures"></a><span data-ttu-id="ffdc3-102">对服务操作失败进行监视</span><span class="sxs-lookup"><span data-stu-id="ffdc3-102">Monitoring Service Operation Failures</span></span>
<span data-ttu-id="ffdc3-103">如果为应用程序启用了分析跟踪，则可以在事件查看器中轻松地监视服务失败。</span><span class="sxs-lookup"><span data-stu-id="ffdc3-103">If analytic tracing is enabled for an application, service failures can easily be monitored in the event viewer.</span></span>  <span data-ttu-id="ffdc3-104">本主题演示如何确定服务操作失败的时间，以及如何确定失败的原因。</span><span class="sxs-lookup"><span data-stu-id="ffdc3-104">This topic demonstrates how to determine when a service operation fails, and how to determine what caused the failure.</span></span>  
  
### <a name="determining-service-operation-failure-information"></a><span data-ttu-id="ffdc3-105">确定服务操作失败信息</span><span class="sxs-lookup"><span data-stu-id="ffdc3-105">Determining service operation failure information</span></span>  
  
1.  <span data-ttu-id="ffdc3-106">通过单击打开事件查看器**启动**，**运行**，并输入`eventvwr.exe`。</span><span class="sxs-lookup"><span data-stu-id="ffdc3-106">Open Event Viewer by clicking **Start**, **Run**, and entering `eventvwr.exe`.</span></span>  
  
2.  <span data-ttu-id="ffdc3-107">如果尚未启用分析跟踪，则展开**Applications and Services Logs**， **Microsoft**， **Windows**，**应用程序服务器-应用程序**.</span><span class="sxs-lookup"><span data-stu-id="ffdc3-107">If you haven’t enabled analytic tracing, expand **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="ffdc3-108">选择**视图**，**显示分析和调试日志**。</span><span class="sxs-lookup"><span data-stu-id="ffdc3-108">Select **View**, **Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="ffdc3-109">右键单击**分析**和选择**启用日志**。</span><span class="sxs-lookup"><span data-stu-id="ffdc3-109">Right-click **Analytic** and select **Enable Log**.</span></span> <span data-ttu-id="ffdc3-110">保持事件查看器打开，以便在服务操作失败后可以查看跟踪。</span><span class="sxs-lookup"><span data-stu-id="ffdc3-110">Leave Event Viewer open so that traces can be viewed after the service operation fails.</span></span>  
  
3.  <span data-ttu-id="ffdc3-111">接下来，打开在中创建的示例[入门教程](../../../../../docs/framework/wcf/getting-started-tutorial.md)中[!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)]请注意，必须运行[!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)]以管理员身份，以便可以创建服务。</span><span class="sxs-lookup"><span data-stu-id="ffdc3-111">Next, open the sample created in the [Getting Started Tutorial](../../../../../docs/framework/wcf/getting-started-tutorial.md) in [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] Note that you must run [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] as an administrator so that the service can be created.</span></span> <span data-ttu-id="ffdc3-112">如果您有安装 WCF 示例，你可以打开[入门](../../../../../docs/framework/wcf/samples/getting-started-sample.md)，其中包含已完成本教程中创建的项目。</span><span class="sxs-lookup"><span data-stu-id="ffdc3-112">If you have the WCF samples installed, you can open the [Getting Started](../../../../../docs/framework/wcf/samples/getting-started-sample.md), which contains the completed project created in the tutorial.</span></span>  
  
4.  <span data-ttu-id="ffdc3-113">在服务器项目的 Program.cs 文件中，将以下代码行添加到 `Divide` 类中 `CalculatorService` 方法的开头：</span><span class="sxs-lookup"><span data-stu-id="ffdc3-113">In the Program.cs file in the Server project, add the following line of code to the start of the `Divide` method in the `CalculatorService` class:</span></span>  
  
    ```  
    if (n2 == 0) throw new DivideByZeroException();  
    ```  
  
5.  <span data-ttu-id="ffdc3-114">在客户端项目的 Program.cs 文件中，将分配给 value2 的值更改为零：</span><span class="sxs-lookup"><span data-stu-id="ffdc3-114">In the Program.cs file in the Client project, change the value assigned to value2 to zero:</span></span>  
  
    ```  
    //Call the Divide service operation  
    value1 = 22.00D;  
    value2 = 0.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0}, {1}) = {2}", value1, value2, result);  
    ```  
  
6.  <span data-ttu-id="ffdc3-115">执行服务器应用程序而不进行调试按**Ctrl + F5**。</span><span class="sxs-lookup"><span data-stu-id="ffdc3-115">Execute the server application without debugging by pressing **Ctrl+F5**.</span></span>  
  
7.  <span data-ttu-id="ffdc3-116">打开 Visual Studio 命令提示。</span><span class="sxs-lookup"><span data-stu-id="ffdc3-116">Open a Visual Studio command prompt.</span></span>  <span data-ttu-id="ffdc3-117">定位到客户端目录，然后从命令行执行该客户端。</span><span class="sxs-lookup"><span data-stu-id="ffdc3-117">Navigate to the client directory and execute the client from the command line.</span></span>  
  
8.  <span data-ttu-id="ffdc3-118">在事件查看器中，禁用并刷新分析日志，然后按事件 ID 对事件排序。</span><span class="sxs-lookup"><span data-stu-id="ffdc3-118">In Event Viewer, disable and refresh the Analytic log and sort the events by Event ID.</span></span>  <span data-ttu-id="ffdc3-119">查找具有事件 ID 的事件[219-ServiceException](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md)，用于描述服务失败。</span><span class="sxs-lookup"><span data-stu-id="ffdc3-119">Look for an event with Event ID [219 - ServiceException](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md), which describes the service failure.</span></span>  
  
    ```Output  
    There was an unhandled exception of type 'System.DivideByZeroException' during message processing.  Full Exception ToString: System.DivideByZeroException: Attempted to divide by zero.  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="ffdc3-120">事件在发送到事件查看器时将被缓冲；可能不会立即显示失败事件。</span><span class="sxs-lookup"><span data-stu-id="ffdc3-120">Events are buffered when being sent to the event viewer; the failure event may not appear right away.</span></span>
