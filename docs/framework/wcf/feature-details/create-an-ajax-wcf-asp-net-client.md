---
title: 在 Visual Studio 中创建启用了 AJAX 的 WCF 服务和 ASP.NET 客户端
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 954ee0409f370c3fa28814a70d51334fd75f7b79
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46528835"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a><span data-ttu-id="7cdcb-102">如何：创建支持 AJAX 的 WCF 服务和访问该服务的 ASP.NET 客户端</span><span class="sxs-lookup"><span data-stu-id="7cdcb-102">How to: Create an AJAX-Enabled WCF Service and an ASP.NET Client that Accesses the Service</span></span>

<span data-ttu-id="7cdcb-103">本主题演示如何使用 Visual Studio 来创建启用了 AJAX 的 Windows Communication Foundation (WCF) 服务和 ASP.NET 客户端访问该服务。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-103">This topic shows how to use Visual Studio to create an AJAX-enabled Windows Communication Foundation (WCF) service and an ASP.NET client that accesses the service.</span></span>

## <a name="create-an-aspnet-web-app"></a><span data-ttu-id="7cdcb-104">创建 ASP.NET Web 应用</span><span class="sxs-lookup"><span data-stu-id="7cdcb-104">Create an ASP.NET web app</span></span>

1. <span data-ttu-id="7cdcb-105">打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-105">Open Visual Studio.</span></span>

1. <span data-ttu-id="7cdcb-106">从**文件**菜单中，选择**新建** > **项目**</span><span class="sxs-lookup"><span data-stu-id="7cdcb-106">From the **File** menu, select **New** > **Project**</span></span>

1. <span data-ttu-id="7cdcb-107">在中**新的项目**对话框中，展开**已安装** > **Visual C#** > **Web**类别，然后选择**ASP.NET Web 应用程序 (.NET Framework)**。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-107">In the **New Project** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select **ASP.NET Web Application (.NET Framework)**.</span></span>

1. <span data-ttu-id="7cdcb-108">将项目命名**SandwichServices**然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-108">Name the Project **SandwichServices** and click **OK**.</span></span>

1. <span data-ttu-id="7cdcb-109">在中**新的 ASP.NET Web 应用程序**对话框中，选择**空**，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-109">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

   ![Visual Studio 中的 ASP.NET web 应用程序类型对话框](media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a><span data-ttu-id="7cdcb-111">添加 web 窗体</span><span class="sxs-lookup"><span data-stu-id="7cdcb-111">Add a web form</span></span>

1. <span data-ttu-id="7cdcb-112">右键单击 SandwichServices 项目中的**解决方案资源管理器**，然后选择**添加** > **新项**。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-112">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="7cdcb-113">在中**添加新项**对话框中，展开**已安装** > **Visual C#** > **Web**类别，然后选择**Web 窗体**模板。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-113">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **Web Form** template.</span></span>

1. <span data-ttu-id="7cdcb-114">接受默认名称 (**WebForm1**)，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-114">Accept the default name (**WebForm1**), and then select **Add**.</span></span>

   <span data-ttu-id="7cdcb-115">*WebForm1.aspx*中打开**源**视图。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-115">*WebForm1.aspx* opens in **Source** view.</span></span>

1. <span data-ttu-id="7cdcb-116">添加以下标记内的**\<正文 >** 标记：</span><span class="sxs-lookup"><span data-stu-id="7cdcb-116">Add the following markup inside the **\<body>** tags:</span></span>

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a><span data-ttu-id="7cdcb-117">创建启用了 AJAX 的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="7cdcb-117">Create an AJAX-enabled WCF service</span></span>

1. <span data-ttu-id="7cdcb-118">右键单击 SandwichServices 项目中的**解决方案资源管理器**，然后选择**添加** > **新项**。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-118">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="7cdcb-119">在中**添加新项**对话框中，展开**已安装** > **Visual C#** > **Web**类别，然后选择**WCF 服务 (ajax)** 模板。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-119">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **WCF Service (AJAX-enabled)** template.</span></span>

   ![在 Visual Studio 中的 WCF 服务 (ajax) 项模板](media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. <span data-ttu-id="7cdcb-121">将服务命名**CostService** ，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-121">Name the service **CostService** and then select **Add**.</span></span>

   <span data-ttu-id="7cdcb-122">*CostService.svc.cs*在编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-122">*CostService.svc.cs* opens in the editor.</span></span>

1. <span data-ttu-id="7cdcb-123">在服务中实现该操作。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-123">Implement the operation in the service.</span></span> <span data-ttu-id="7cdcb-124">将以下方法添加到 CostService 类，以计算量的三明治的成本：</span><span class="sxs-lookup"><span data-stu-id="7cdcb-124">Add the following method to the CostService class to calculate the cost of a quantity of sandwiches:</span></span>

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a><span data-ttu-id="7cdcb-125">配置客户端访问服务</span><span class="sxs-lookup"><span data-stu-id="7cdcb-125">Configure the client to access the service</span></span>

1. <span data-ttu-id="7cdcb-126">打开*WebForm1.aspx*文件，然后选择**设计**视图。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-126">Open the *WebForm1.aspx* file and select the **Design** view.</span></span>

2. <span data-ttu-id="7cdcb-127">从**视图**菜单中，选择**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-127">From the **View** menu, select **Toolbox**.</span></span>

3. <span data-ttu-id="7cdcb-128">展开**AJAX Extensions**节点和拖放**ScriptManager**拖到窗体。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-128">Expand the **AJAX Extensions** node and drag and drop a **ScriptManager** onto the form.</span></span>

4. <span data-ttu-id="7cdcb-129">回到**源**视图中，添加以下代码之间 **\<ScriptManager >** 标记，以指定 WCF 服务的路径：</span><span class="sxs-lookup"><span data-stu-id="7cdcb-129">Back in the **Source** view, add the following code between the **\<ScriptManager>** tags to specify the path to the WCF service:</span></span>

    ```html
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

1. <span data-ttu-id="7cdcb-130">添加 Javascript 函数的代码`Calculate()`。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-130">Add the code for the Javascript function `Calculate()`.</span></span> <span data-ttu-id="7cdcb-131">将以下代码中的放置**head** web 窗体的部分：</span><span class="sxs-lookup"><span data-stu-id="7cdcb-131">Place the following code in the **head** section of the web form:</span></span>

    ```javascript
    <script type="text/javascript">

        function Calculate() {
            CostService.CostOfSandwiches(3, onSuccess);
        }

        function onSuccess(result) {
            var myres = $get("additionResult");
            myres.innerHTML = result;
        }

    </script>
    ```

   <span data-ttu-id="7cdcb-132">此代码调用 CostService 来计算三个三明治的价格的方法，并在调用的范围显示结果**additionResult**。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-132">This code calls the method of CostService to calculate the price for three sandwiches, and then displays the result in the span called **additionResult**.</span></span>

## <a name="run-the-program"></a><span data-ttu-id="7cdcb-133">运行程序</span><span class="sxs-lookup"><span data-stu-id="7cdcb-133">Run the program</span></span>

<span data-ttu-id="7cdcb-134">请确保*WebForm1.aspx*具有焦点，，然后按**启动**按钮以启动 web 客户端。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-134">Make sure that *WebForm1.aspx* has focus, and then press **Start** button to launch the web client.</span></span> <span data-ttu-id="7cdcb-135">按钮有一个绿色三角形和内容类似于**IIS Express (Microsoft Edge)**。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-135">The button has a green triangle and says something like **IIS Express (Microsoft Edge)**.</span></span> <span data-ttu-id="7cdcb-136">或者，可以按**F5**。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-136">Or, you can press **F5**.</span></span> <span data-ttu-id="7cdcb-137">单击**3 三明治的价格**按钮以生成预期的输出为"3.75"。</span><span class="sxs-lookup"><span data-stu-id="7cdcb-137">Click the **Price of 3 sandwiches** button to generate the expected output of "3.75".</span></span>

## <a name="example-code"></a><span data-ttu-id="7cdcb-138">示例代码</span><span class="sxs-lookup"><span data-stu-id="7cdcb-138">Example code</span></span>

<span data-ttu-id="7cdcb-139">以下是中的完整代码*CostService.svc.cs*文件：</span><span class="sxs-lookup"><span data-stu-id="7cdcb-139">Following is the full code in the *CostService.svc.cs* file :</span></span>

```csharp
using System.ServiceModel;
using System.ServiceModel.Activation;

namespace SandwichServices
{
    [ServiceContract(Namespace = "")]
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class CostService
    {
        [OperationContract]
        public double CostOfSandwiches(int quantity)
        {
            return 1.25 * quantity;
        }
    }
}
```

<span data-ttu-id="7cdcb-140">下面是完整的内容*WebForm1.aspx*页：</span><span class="sxs-lookup"><span data-stu-id="7cdcb-140">Following is the full contents of the *WebForm1.aspx* page:</span></span>

```aspx-csharp
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="WebForm1.aspx.cs" Inherits="SandwichServices.WebForm1" %>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title></title>
    <script type="text/javascript">

        function Calculate() {
            CostService.CostOfSandwiches(3, onSuccess);
        }

        function onSuccess(result) {
            var myres = $get("additionResult");
            myres.innerHTML = result;
        }

    </script>
</head>
<body>
    <form id="form1" runat="server">
        <div>
        </div>
        <asp:ScriptManager ID="ScriptManager1" runat="server">
            <Services>
                <asp:ServiceReference Path="~/CostService.svc" />
            </Services>
        </asp:ScriptManager>

        <input type="button" value="Price of 3 sandwiches" onclick="Calculate()" />
        <br />
        <span id="additionResult"></span>
    </form>
</body>
</html>
```
